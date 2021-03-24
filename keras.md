# Keras 

[keras中文文档](https://keras.io/zh/)

## 快速上手

如果你在以下情况下需要深度学习库，请使用 Keras：

+ 允许简单而快速的原型设计（由于用户友好，高度模块化，可扩展性）。
+ 同时支持卷积神经网络和循环神经网络，以及两者的组合。
+ 在 CPU 和 GPU 上无缝运行。

Keras 是一个用 Python 编写的高级神经网络 API，它能够以 [TensorFlow](https://github.com/tensorflow/tensorflow), [CNTK](https://github.com/Microsoft/cntk), 或者 [Theano](https://github.com/Theano/Theano) 作为后端运行。默认情况下，Keras 将使用 TensorFlow 作为其张量操作库。请[跟随这些指引](https://keras.io/zh/backend/)来配置其他 Keras 后端。

你也可以考虑安装以下**可选依赖**：

- [cuDNN](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/) (如果你计划在 GPU 上运行 Keras，建议安装)。
- HDF5 和 [h5py](http://docs.h5py.org/en/latest/build.html) (如果你需要将 Keras 模型保存到磁盘，则需要这些)。
- [graphviz](https://graphviz.gitlab.io/download/) 和 [pydot](https://github.com/erocarrera/pydot) (用于[可视化工具](https://keras.io/zh/visualization/)绘制模型图)。

-------

Keras 的核心数据结构是 **model**，一种组织网络层的方式。最简单的模型是 [Sequential 顺序模型](https://keras.io/getting-started/sequential-model-guide)，它由多个网络层线性堆叠。对于更复杂的结构，你应该使用 [Keras 函数式 API](https://keras.io/getting-started/functional-api-guide)，它允许构建任意的神经网络图。

```python
from keras.models import Sequential
model = Sequential()

#可以简单地使用 `.add()` 来堆叠模型
model.add(Dense(units=64, activation='relu', input_dim=100)) # 第一层需要指定输入数据的尺寸

#在完成了模型的构建后, 可以使用 .compile() 来配置学习过程：
model.compile(loss='categorical_crossentropy',    #模型编译
              optimizer='sgd',
              metrics=['accuracy'])

#然后批量地在训练数据上进行迭代了：
model.fit(x_train, y_train, epochs=5, batch_size=32) #模型训练  x_train 和 y_train 是 Numpy 数组 
#手动地将批次的数据提供给模型：
model.train_on_batch(x_batch, y_batch)

#评估模型性能：
loss_and_metrics = model.evaluate(x_test, y_test, batch_size=128) #返回的是 损失值和你选定的指标值
#对新的数据生成预测：
classes = model.predict(x_test, batch_size=128)
```

有关 Keras 更深入的教程，请查看：

- [开始使用 Sequential 模型](https://keras.io/zh/getting-started/sequential-model-guide/)
- [开始使用函数式 API](https://keras.io/zh/getting-started/functional-api-guide/)

在 [examples 目录](https://github.com/keras-team/keras/tree/master/examples) 中，你可以找到真实数据集的示例模型：

- CIFAR10 小图片分类：具有实时数据增强的卷积神经网络 (CNN)
- IMDB 电影评论情感分类：基于词序列的 LSTM
- Reuters 新闻主题分类：多层感知器 (MLP)
- MNIST 手写数字分类：MLP & CNN
- 基于 LSTM 的字符级文本生成

## 使用 Keras 函数式 API

利用函数式 API，可以轻易地重用训练好的模型：可以将任何模型看作是一个层，然后通过传递一个张量来调用它。注意，在调用模型时，您不仅重用模型的*结构*，还重用了它的权重。

+ 共享网络层、多输入多输出模型

```python
from keras.layers import Input, Dense
from keras.models import Model

# 这部分返回一个张量
inputs = Input(shape=(784,))

# 层的实例是可调用的，它以张量为参数，并且返回一个张量
x = Dense(64, activation='relu')(inputs)
x = Dense(64, activation='relu')(x)
predictions = Dense(10, activation='softmax')(x)

# 这部分创建了一个包含输入层和三个全连接层的模型
model = Model(inputs=inputs, outputs=predictions)
model.compile(optimizer='rmsprop',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
model.fit(data, labels)  # 开始训练
```

## [常见问题解答](https://keras.io/zh/getting-started/faq/)

### 在多 GPU 上运行 Keras 模型

```python
# 数据并行
from keras.utils import multi_gpu_model
# 将 `model` 复制到 8 个 GPU 上。
# 假定你的机器有 8 个可用的 GPU。
parallel_model = multi_gpu_model(model, gpus=8)
parallel_model.compile(loss='categorical_crossentropy',
                       optimizer='rmsprop')
# 这个 `fit` 调用将分布在 8 个 GPU 上。
# 由于 batch size 为 256，每个 GPU 将处理 32 个样本。
parallel_model.fit(x, y, epochs=20, batch_size=256)

# 设备并行性：包括在不同设备上运行同一模型的不同部分。对于具有并行体系结构的模型，例如有两个分支的模型，这种方式很合适。
# 模型中共享的 LSTM 用于并行编码两个不同的序列
input_a = keras.Input(shape=(140, 256))
input_b = keras.Input(shape=(140, 256))
shared_lstm = keras.layers.LSTM(64)
# 在一个 GPU 上处理第一个序列
with tf.device_scope('/gpu:0'):
    encoded_a = shared_lstm(tweet_a)
# 在另一个 GPU上 处理下一个序列
with tf.device_scope('/gpu:1'):
    encoded_b = shared_lstm(tweet_b)
# 在 CPU 上连接结果
with tf.device_scope('/cpu:0'):
    merged_vector = keras.layers.concatenate([encoded_a, encoded_b], axis=-1)
```

### 获取中间层的输出

```python
#一个简单的方法是创建一个新的 Model 来输出你所感兴趣的层：
from keras.models import Model
model = ...  # 创建原始模型
layer_name = 'my_layer'
intermediate_layer_model = Model(inputs=model.input,
                                 outputs=model.get_layer(layer_name).output)
intermediate_output = intermediate_layer_model.predict(data)
#也可以构建一个 Keras 函数，该函数将在给定输入的情况下返回某个层的输出，例如：
from keras import backend as K
# 以 Sequential 模型为例
get_3rd_layer_output = K.function([model.layers[0].input],
                                  [model.layers[3].output])
layer_output = get_3rd_layer_output([x])[0]
```

### 如何用 Keras 处理超过内存的数据集

+ 可以使用 `model.train_on_batch(x，y)` 和 `model.test_on_batch(x，y)` 进行批量训练与测试。请参阅 [模型文档](https://keras.io/models/sequential)。
+ 或者编写一个生成批处理训练数据的生成器，然后使用 `model.fit_generator(data_generator，steps_per_epoch，epochs)` 方法。可以在 [CIFAR10 example](https://github.com/keras-team/keras/blob/master/examples/cifar10_cnn.py) 中找到实践代码。

## Model 类继承

```python
import keras

class SimpleMLP(keras.Model):

    def __init__(self, use_bn=False, use_dp=False, num_classes=10):
        super(SimpleMLP, self).__init__(name='mlp')
        self.use_bn = use_bn
        self.use_dp = use_dp
        self.num_classes = num_classes

        self.dense1 = keras.layers.Dense(32, activation='relu')
        self.dense2 = keras.layers.Dense(num_classes, activation='softmax')
        if self.use_dp:
            self.dp = keras.layers.Dropout(0.5)
        if self.use_bn:
            self.bn = keras.layers.BatchNormalization(axis=-1)

    def call(self, inputs):
        x = self.dense1(inputs)
        if self.use_dp:
            x = self.dp(x)
        if self.use_bn:
            x = self.bn(x)
        return self.dense2(x)

model = SimpleMLP()
model.compile(...)
model.fit(...)
```

## 编写你自己的 Keras 层

这是一个 **Keras2.0** 中，Keras 层的骨架（如果你用的是旧的版本，请更新到新版）。你只需要实现三个方法即可:

- `build(input_shape)`: 这是你定义权重的地方。这个方法必须设 `self.built = True`，可以通过调用 `super([Layer], self).build()` 完成。
- `call(x)`: 这里是编写层的功能逻辑的地方。你只需要关注传入 `call` 的第一个参数：输入张量，除非你希望你的层支持masking。
- `compute_output_shape(input_shape)`: 如果你的层更改了输入张量的形状，你应该在这里定义形状变化的逻辑，这让Keras能够自动推断各层的形状。

```python
from keras import backend as K
from keras.engine.topology import Layer

class MyLayer(Layer):

    def __init__(self, output_dim, **kwargs):
        self.output_dim = output_dim
        super(MyLayer, self).__init__(**kwargs)

    def build(self, input_shape):
        # 为该层创建一个可训练的权重
        self.kernel = self.add_weight(name='kernel', 
                                      shape=(input_shape[1], self.output_dim),
                                      initializer='uniform',
                                      trainable=True)
        super(MyLayer, self).build(input_shape)  # 一定要在最后调用它

    def call(self, x):
        return K.dot(x, self.kernel)

    def compute_output_shape(self, input_shape):
        return (input_shape[0], self.output_dim)
```

