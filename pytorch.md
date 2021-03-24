# 深度学习框架PyTorch：入门与实践

项目地址：https://github.com/chenyuntc/pytorch-book

## 2 快速入门

### 2.2 PyTorch 入门第一步

+ `Tensor`是PyTorch中重要的数据结构，可以是一个数（标量）、一维数组（向量）、二维数组（矩阵）以及更高维的数组。

+ `autograd`：自动微分，autograd.Variable是Autograd中的核心类，它简单封装了Tensor，并支持几乎所有Tensor有的操作。Tensor在被封装为Variable之后，可以调用它的.backward实现反向传播，自动计算所有梯度，Variable主要包含三个属性。 

  - data：保存Variable所包含的Tensor 
  - grad：保存data对应的梯度，grad也是个Variable，而不是Tensor，它和data的形状一样。 在反向传播过程中是累加的，这意味着每一次运行反向传播，梯度都会累加之前的梯度，所以反向传播之前需把梯度清零。
  - grad_fn：指向一个Function对象，这个Function用来反向传播计算输入的梯度。

+ 小试牛刀：CIFAR-10分类

  ```python
  import torch as t
  import torchvision as tv
  import torchvision.transforms as transforms
  from torchvision.transforms import ToPILImage
  import torch.nn as nn
  import torch.nn.functional as F
  from torch import optim
  #模型
  class Net(nn.Module):
      # 把网络中具有可学习参数的层放在构造函数__init__中。如果某一层(如ReLU)不具有可学习的参数，
      # 则既可以放在构造函数中，也可以不放，但建议不放在其中，而在forward中使用nn.functional代替。
      def __init__(self):
          super(Net, self).__init__()
          self.conv1 = nn.Conv2d(3, 6, 5) 
          self.conv2 = nn.Conv2d(6, 16, 5)  
          self.fc1   = nn.Linear(16*5*5, 120)  
          self.fc2   = nn.Linear(120, 84)
          self.fc3   = nn.Linear(84, 10)
      # 只要在nn.Module的子类中定义了forward函数，backward函数就会自动被实现(利用autograd)。
      # 在forward 函数中可使用任何tensor支持的函数，还可以使用if、for循环、print、log等Python语法，
      # 写法和标准的Python写法一致。
      def forward(self, x): 
          x = F.max_pool2d(F.relu(self.conv1(x)), (2, 2)) 
          x = F.max_pool2d(F.relu(self.conv2(x)), 2) 
          x = x.view(x.size()[0], -1) 
          x = F.relu(self.fc1(x))
          x = F.relu(self.fc2(x))
          x = self.fc3(x)        
          return x
      # 网络的可学习参数通过net.parameters()返回，net.named_parameters可同时返回可学习的参数及名称。
  # 训练    
  def train(trainloader,net):
      # 交叉熵损失函数
      criterion = nn.CrossEntropyLoss() 
      # 在反向传播计算完所有参数的梯度后，还需要使用优化方法来更新网络的权重和参数，
      optimizer = optim.SGD(net.parameters(), lr=0.001, momentum=0.9)
  
      t.set_num_threads(8)  #设置线程
      for epoch in range(2):      
          running_loss = 0.0
          for i, data in enumerate(trainloader, 0): #0表示从0开始
              inputs, labels = data # 输入数据
  
              optimizer.zero_grad() # 梯度清零
              outputs = net(inputs)            
              loss = criterion(outputs, labels) # 计算损失
              loss.backward()   #反向传播
              optimizer.step()  # 更新参数 
  
              running_loss += loss.item() # loss 是一个scalar,需要使用loss.item()来获取数值，不能使用loss[0]
              if i % 2000 == 1999: # 每2000个batch打印一下训练状态
                  print('[%d, %5d] loss: %.3f' % (epoch+1, i+1, running_loss / 2000))
                  running_loss = 0.0
      print('Finished Training')
  
  # 测试    
  def test(testloader,net):
      correct,total = 0,0
      # 由于测试的时候不需要求导，可以暂时关闭autograd，提高速度，节约内存
      with t.no_grad():
          for data in testloader:
              images, labels = data
              outputs = net(images)
              _, predicted = t.max(outputs, 1)
              total += labels.size(0)
              correct += (predicted == labels).sum()
  
      print('10000张测试集中的准确率为: %d %%' % (100 * correct / total))    
      
  def main():
      #数据加载
      transform = transforms.Compose([  # 定义对数据的预处理
              transforms.ToTensor(), # 转为Tensor
              transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5)),]) # 归一化
      # 训练集
      trainset = tv.datasets.CIFAR10(root='./',train=True, download=True,transform=transform)
      trainloader = t.utils.data.DataLoader(trainset, batch_size=4,shuffle=True, num_workers=2)
      # 测试集
      testset = tv.datasets.CIFAR10('./',train=False, download=True, transform=transform)
      testloader = t.utils.data.DataLoader(testset,batch_size=4, shuffle=False, num_workers=2)
      
      net=Net()    
      train(trainloader,net)
      test(testloader,net)
  ```



## 3 Tensor and Autograd

### 3.1 tensor

+ 从接口的角度来讲，对tensor的操作可分为两类：

  + torch.function，如torch.save等。
  + tensor.function，如tensor.view等

+ 函数名以`_`结尾的都是inplace方式, 即会修改调用者自己的数据，在实际应用中需加以区分。

+ Numpy和Tensor共享内存，当numpy的数据类型和Tensor的类型不一样的时候，数据会被复制，不会共享内存。

+ 小试牛刀：线性回归

  ```python
  import torch as t
  from matplotlib import pyplot as plt
  
  device = t.device('cpu') #如果你想用gpu，改成t.device('cuda:0')
  
  def get_fake_data(batch_size=8):
      ''' 产生随机数据：y=x*2+3，加上了一些噪声'''
      global device
      x = t.rand(batch_size, 1, device=device) * 5
      y = x * 2 + 3 +  t.randn(batch_size, 1, device=device)
      return x, y
  
  def main():
      global device
      t.manual_seed(1000) # 设置随机数种子，保证在不同电脑上运行时下面的输出一致
      w = t.rand(1, 1).to(device) # 随机初始化参数
      b = t.zeros(1, 1).to(device)
      lr =0.02  # 学习率
      for ii in range(50):
          x, y = get_fake_data(batch_size=4)
          # forward：计算loss
          y_pred = x.mm(w) + b.expand_as(y) # x@W等价于x.mm(w);for python3 only
          loss = 0.5 * (y_pred - y) ** 2 # 均方误差
          loss = loss.mean()
          # backward：手动计算梯度
          dloss = 1
          dy_pred = dloss * (y_pred - y)
          dw = x.t().mm(dy_pred)
          db = dy_pred.sum()
          # 更新参数
          w.sub_(lr * dw)
          b.sub_(lr * db)
          # 可视化
          plt.ion() # 打开交互模式
          if ii%10 ==0:
              plt.cla() #清除原有图像
              x = t.arange(0, 6).view(-1, 1)
              y = x.float().mm(w) + b.expand_as(x)
              x2, y2 = get_fake_data(batch_size=32) 
              # 画图
              plt.plot(x.cpu().numpy(), y.cpu().numpy()) # 预测线
              plt.scatter(x2.numpy(), y2.numpy()) # 真实散点图，与训练的不是一批数据
              plt.xlim(0, 5)
              plt.ylim(0, 13)
              plt.pause(0.5)
      print('w: ', w.item(), 'b: ', b.item())
  ```

### 3.2 autograd

+ torch.autograd就是为方便用户使用，而专门开发的一套自动求导引擎，它能够根据输入和前向传播过程自动构建计算图，并执行反向传播。计算图(Computation Graph)是现代深度学习框架如PyTorch和TensorFlow等的核心，其为高效自动求导算法——反向传播(Back Propogation)提供了理论支持。

+ 可以认为需要求导(requires_grad)的tensor即Variable。autograd记录对tensor的操作记录用来构建计算图。Variable提供了大部分tensor支持的函数，但其不支持部分inplace函数，因这些函数会修改tensor自身，而在反向传播中，variable需要缓存原来的tensor来计算反向传播梯度。如果想要计算各个Variable的梯度，只需调用根节点variable的backward方法，autograd会自动沿着计算图反向传播，计算每一个叶子节点的梯度。`variable.backward(gradient=None, retain_graph=None, create_graph=None)`

+ 如果想要修改tensor的数值，但是又不希望被autograd记录，那么我么可以对tensor.data进行操作

+ 扩展autograd：写一个Function，实现它的前向传播和反向传播代码，Function对应于计算图中的矩形， 它接收参数，计算并返回结果。

+ 小试牛刀: 用Variable实现线性回归

  ```python
  import torch as t
  from matplotlib import pyplot as plt
  import numpy as np
  …… 
  def main():
      ……
      # 随机初始化参数
      w = t.rand(1,1, requires_grad=True)
      b = t.zeros(1,1, requires_grad=True)
      losses = np.zeros(500)
      lr =0.02 # 学习率
      for ii in range(500):
          ……
          losses[ii] = loss.item()
          # backward：手动计算梯度
          loss.backward()
          # 更新参数
          w.data.sub_(lr * w.grad.data) # w.data
          b.data.sub_(lr * b.grad.data)
          # 梯度清零
          w.grad.data.zero_()
          b.grad.data.zero_()
          ……
      plt.cla() 
      plt.ioff() # 关闭交互模式
      plt.plot(losses)
      plt.show()
  ```

## 4 神经网络工具箱nn

+ torch.nn的核心数据结构是Module，它是一个抽象概念，既可以表示神经网络中的某个层（layer），也可以表示一个包含很多层的神经网络。在实际使用中，最常见的做法是继承nn.Module，撰写自己的网络/层。

  + 自定义层必须继承nn.Module，并且在其构造函数中需调用nn.Module的构造函数，`super(Linear, self).__init__()`
  + 在构造函数`__init__`中必须自己定义可学习的参数，并封装成Parameter之类的，
  + `forward`函数实现前向传播过程。

+ PyTorch实现了神经网络中绝大多数的layer，这些layer都继承于nn.Module，封装了可学习参数parameter，并实现了forward函数，且很多都专门针对GPU运算进行了CuDNN优化，其速度和性能都十分优异。**注意**：输入的不是单个数据，而是一个batch。输入只有一个数据，则必须调用tensor.unsqueeze(0) 或 tensor[None]将数据伪装成batch_size=1的batch

+ 将每一层的输出直接作为下一层的输入，这种网络称为前馈传播网络（feedforward neural network）。对于此类网络如果每次都写复杂的forward函数会有些麻烦，在此就有两种简化方式，ModuleList和Sequential。其中Sequential是一个特殊的module，它包含几个子Module，前向传播时会将输入一层接一层的传递下去。ModuleList也是一个特殊的module，可以包含几个子module，可以像用list一样使用它，但不能直接把输入传给ModuleList，当在Module中使用它的时候，就能自动识别为子module。

+ 小试牛刀：搭建ResNet

  ```python
  from torch import  nn
  import torch as t
  from torch.nn import  functional as F
  
  class ResidualBlock(nn.Module):
      '''
      实现子module: Residual Block
      '''
      def __init__(self, inchannel, outchannel, stride=1, shortcut=None):
          super(ResidualBlock, self).__init__()
          self.left = nn.Sequential(
                  nn.Conv2d(inchannel,outchannel,3,stride, 1,bias=False),
                  nn.BatchNorm2d(outchannel),
                  nn.ReLU(inplace=True),
                  nn.Conv2d(outchannel,outchannel,3,1,1,bias=False),
                  nn.BatchNorm2d(outchannel) )
          self.right = shortcut
  
      def forward(self, x):
          out = self.left(x)
          residual = x if self.right is None else self.right(x)
          out += residual
          return F.relu(out)
  
  class ResNet(nn.Module):
      '''
      实现主module：ResNet34
      ResNet34 包含多个layer，每个layer又包含多个residual block
      用子module来实现residual block，用_make_layer函数来实现layer
      '''
      def __init__(self, num_classes=1000):
          super(ResNet, self).__init__()
          # 前几层图像转换
          self.pre = nn.Sequential(
                  nn.Conv2d(3, 64, 7, 2, 3, bias=False),
                  nn.BatchNorm2d(64),
                  nn.ReLU(inplace=True),
                  nn.MaxPool2d(3, 2, 1))
          
          # 重复的layer，分别有3，4，6，3个residual block
          self.layer1 = self._make_layer( 64, 64, 3)
          self.layer2 = self._make_layer( 64, 128, 4, stride=2)
          self.layer3 = self._make_layer( 128, 256, 6, stride=2)
          self.layer4 = self._make_layer( 256, 512, 3, stride=2)
  
          #分类用的全连接
          self.fc = nn.Linear(512, num_classes)
      
      def _make_layer(self,  inchannel, outchannel, block_num, stride=1):
          '''
          构建layer,包含多个residual block
          '''
          shortcut = nn.Sequential(
                  nn.Conv2d(inchannel,outchannel,1,stride, bias=False),
                  nn.BatchNorm2d(outchannel))
          
          layers = []
          layers.append(ResidualBlock(inchannel, outchannel, stride, shortcut))
          
          for i in range(1, block_num):
              layers.append(ResidualBlock(outchannel, outchannel))
          return nn.Sequential(*layers)
          
      def forward(self, x):
          x = self.pre(x)
          
          x = self.layer1(x)
          x = self.layer2(x)
          x = self.layer3(x)
          x = self.layer4(x)
  
          x = F.avg_pool2d(x, 7)
          x = x.view(x.size(0), -1)
          return self.fc(x)
  ```

  

##  5. PyTorch常用工具模块

`from torch.utils import data` ，`from torchvision import transforms as T`

+ 加载数据：自定义的数据集对象需要继承Dataset。实现两个方法：`__getitem__`：返回一条数据，或一个样本。`obj[index]`等价于`obj.__getitem__(index)`；`__len__`：返回样本的数量。`len(obj)`等价于`obj.__len__()`。如果所有的文件按文件夹保存，每个文件夹下存储同一个类别的图片，文件夹名为类名，可用`ImageFolder(root, transform=None, target_transform=None, loader=default_loader)`；label是按照文件夹名顺序排序后存成字典，即{类名:类序号(从0开始)}。
  + 批处理： `DataLoader(dataset, batch_size=1, shuffle=False, sampler=None, num_workers=0, collate_fn=default_collate, pin_memory=False, drop_last=False)`
+ 数据处理：`transform = T.Compose()`
  + 计算机视觉工具包torchvision：models、datasets、transforms
  + 转GPU，`.cuda()`

## 6.文件组织结构

```
- `checkpoints/`： 用于保存训练好的模型，可使程序在异常退出后仍能重新载入模型，恢复训练
- `data/`：数据相关操作，包括数据预处理、dataset实现等
- `models/`：模型定义，可以有多个模型，例如上面的AlexNet和ResNet34，一个模型对应一个文件
- `utils/`：可能用到的工具函数，在本次实验中主要是封装了可视化工具
- `config.py`：配置文件，所有可配置的变量都集中在此，并提供默认值
- `main.py`：主文件，训练和测试程序的入口，可通过不同的命令来指定不同的操作和参数
- `requirements.txt`：程序依赖的第三方库
- `README.md`：提供程序的必要说明
```



