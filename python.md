## 一般函数

`eval()` 函数用来执行一个字符串表达式，并返回表达式的值。可以用来将字符串变为数值。



# 包

## scipy.sparse

[参考文档](https://docs.scipy.org/doc/scipy/reference/sparse.html)

+ **bsr_matrix((data,indice,indptr),shape=(m,n))**

data为大小相等的块组成的数组，indice每个块在矩阵中的列位置，indptr表示在indice中那几个块（indptr[i:i+1]）属于当前行i。

```shell
#[[A0 A1 A2],[B0,B1,B2],[C0,C1,C2]]为相同大小的块组成的矩阵。
data=[A,B,C,D];#表示有四个块，需要填入矩阵。
indice=[1,0,0,2];#表示A,B,C,D分别放在列为1,0,0,2的位置
indptr=[0,1,2,4];#表示indice中第[0,1)个矩阵A放在第0行，[1,2)个矩阵B放在第1行,[2,4)个矩阵放在第2行。
#[[A0,A,A2],[B,B1,B2],[C,C1,D]]
```

![image-20210325162821349](img/image-20210325162821349.png)

+ **csr_matrix((data, (row_ind, col_ind)), [shape=(M, N)])**

`.tolil()`将矩阵转为列表的列表形式

`.todok()`将lil转为dok形式

`.tocoo()`转为坐标形式，(data,col,row)

