# 基础

[官方文档](https://docs.python.org/zh-cn/3/)

## 解析器

安装的python可执行文件，`python filename`。`-c`命令行模式，`-m`模块 

> 命令行参数：解释器把脚本名与其他参数转化为字符串列表存到 `sys` 模块的 `argv` 变量里。
>
> 声明文件的编码，文件的 **第一** 行要写成特殊注释。格式`# -*- coding: encoding -*-`
>
> 拼接行：用不在字符串或注释内的反斜杠（`\`）拼接为一个逻辑行。
>
> 以空白符分隔的**多个相邻字符串或字节串字面值**，可用不同引号标注，等同于合并操作。
>
> ![image-20210406153745918](img/image-20210406153745918.png)



## 模块

```python
import model
from model import name as n
model.__name__
```

**模块**：以 `.py`结尾的文件，文件名即为模块名，通过全局变量 `__name__` 可以获取模块名（即字符串）。

> 为了保证运行效率，每次解释器会话只导入一次模块。如果更改了模块内容，必须重启解释器；
>
> 脚本方式执行模块时，会把`__name__` 赋值为 `"__main__"`，所以可以将模块中`if __name__=="__main__"`的部分用作测试。
>
> 为了快速加载模块，Python 把模块的编译版缓存在 `__pycache__` 目录中。Python 对比编译版本与源码的修改日期，查看它是否已过期，是否要重新编译，此过程完全自动化。
>
> 内置函数 [`dir(model)`](https://docs.python.org/zh-cn/3/library/functions.html#dir) 用于查找模块定义的名称。没有参数时，[`dir()`](https://docs.python.org/zh-cn/3/library/functions.html#dir) 列出当前定义的名称：

**包**：Python 只把含 `__init__.py` 文件的目录当成包。

> 如果包的 `__init__.py` 代码定义了列表 `__all__`，运行 `from package import *` 时，会导入`__all__`里面的内容。

### 模块搜索路径

1. 解释器首先查找名为 model 的**内置模块**。
2. 解释器再从 [`sys.path`](https://docs.python.org/zh-cn/3/library/sys.html#sys.path) 变量中的目录列表里查找 `model.py` 文件。





## 内置函数

[参考](https://www.runoob.com/python/python-built-in-functions.html)

| 函数       | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| `eval()`   | 函数用来执行一个字符串表达式，并返回表达式的值。可以用来将字符串变为数值。 |
| `zip()`    | 将可迭代的对象作为参数，将对象中对应的元素打包成一个个元组，然后返回由这些元组组成的列表。 |
| `filter()` | 用于过滤序列，过滤掉不符合条件的元素，返回由符合条件元素组成的新列表。 |
| `super()`  | 调用父类(超类)的一个方法。super(Class, self).xxx             |



# 包

## scipy.sparse

[参考文档](https://docs.scipy.org/doc/scipy/reference/sparse.html)

+ **bsr_matrix((data,indice,indptr),shape=(m,n))**：**块**的坐标，适合稀疏矩阵局部为密集子矩阵的情况，支持**高效运算**。

data为大小相等的块组成的数组，indice每个块在矩阵中的列位置，indptr表示在indice中那几个块（indptr[i:i+1]）属于当前行i。

```shell
#[[A0 A1 A2],[B0,B1,B2],[C0,C1,C2]]为相同大小的块组成的矩阵。
data=[A,B,C,D];#表示有四个块，需要填入矩阵。
indice=[1,0,0,2];#表示A,B,C,D分别放在列为1,0,0,2的位置
indptr=[0,1,2,4];#表示indice中第[0,1)个矩阵A放在第0行，[1,2)个矩阵B放在第1行,[2,4)个矩阵放在第2行。
#[[A0,A,A2],[B,B1,B2],[C,C1,D]]
```

<img src="img/image-20210325162821349.png" alt="image-20210325162821349" />

+ **csr_matrix((data, (row_ind, col_ind)), [shape=(M, N)])**：为矩阵里的每个非零元素，提供坐标。**高效的算术运算**。如果有重复的坐标，则矩阵里值为该位置上的值的和。
+ **coo_matrix((data, (i, j)), [shape=(M, N)])**：in COOrdinate format，不支持矩阵运算，**一般用来构造稀疏矩阵**，然后再转为其他格式的矩阵，进行矩阵运算。
+ **csc_matrix((M, N), [dtype])**：支持**高效的列切片**column slicing。
+ **dia_matrix((data, offsets), shape=(M, N))**：**对角矩阵**，offsets和data的维度一样，表示**在对角线上往上下**移动的offset[k]的位置上的值为data[k]。

```python
data = np.array([[1, 2, 3, 4]]).repeat(3, axis=0)  #第一维和offset的维度大小一样，第二维与矩阵的大小一样。
offsets = np.array([0, -1, 2])
dia_matrix((data, offsets), shape=(4, 4)).toarray()
```

![image-20210326180629561](img/image-20210326180629561.png)

+ **dok_matrix((M,N), [dtype])**：Dictionary Of Keys based sparse matrix.支持高效地**访问单个元素**。
+ **lil_matrix((M, N), [dtype])**：Row-based list of lists sparse matrix，支持灵活的切片slicing，高效地**修改**。运算效率低。

+ 函数：
  + `.to*()`将矩阵转为其他格式。
  + `.issp*()`是否为某种格式。
  + `eye()`对角全为1的对角矩阵，`hstack([block])`将块水平（v垂直）堆叠。

