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

+ **csr_matrix((data, (row_ind, col_ind)), [shape=(M, N)])**：为矩阵里的每个非零元素，提供坐标。**高效的算术运算**。
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

