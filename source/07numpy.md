# 第七章  Numpy基础

作者：李昕

单位：中国石油大学（华东）

本章重点难点：ndarray的使用，矩阵运算

## 1. 科学数据的表示方法

讲解向量、矩阵的基本表示方法。

## 2. 矩阵运算

矩阵的基本算术运算，以及筛选、连接等复杂操作。

## 3. 数据广播

如何进行不对等维度之间的算术操作。



## 二、Numpy 的使用

1. X = np.array([0,0]) 作用为将括号中的内容转换程数组

2. X = np.matrix(X) 作用为将X转化成矩阵

   `X = np.matrix(np.array([0,0]))`

   上面的代码运行后的结果为 `[[0,0]]`

3. 矩阵的转置

   X = X.transcope() 或者 X = X.T

4. 矩阵的对应元素相乘

   X = multiply(mat1,mat2)

5. 矩阵的点乘

   X = A * B

6. 利用矩阵访问元素

   值得注意的是，numpy 访问矩阵的方法与python中利用下标访问数组的方式不一样，不能够通过`X[row][col]`来访问，访问方式与matlab一致，使用 X[row,col]来访问矩阵

7. 矩阵类型

   在Numpy中，矩阵中的元素也具有数据类型，与python的数据类型不同，其有int16,float64等等，这样有时会存在 a[0,1] = 0.1 赋值不上的问题，因为其被强制转换成了int型再进行赋值。

   （1）dtype = float 

   ​	`m = np.matrix([[0,0]], dtype=float)`

   （2）astype 进行矩阵类型的转换

   ​	`m.astype(np.float64)`

8. .flatten()方法和.ravel()方法

   二者的效果一致，都是将一个二维矩阵扁平化成一维矩阵

   `from numpy import *`

   `a = arange(12).reshape(3,4)`
   `print(a)`

   `#[[ 0  1  2  3]`

   `#[ 4  5  6  7]`

   `#[ 8  9 10 11]]`

   `print(a.ravel())`

   `#[ 0  1  2  3  4  5  6  7  8  9 10 11]`

   `print(a.flatten())`

   `#[ 0  1  2  3  4  5  6  7  8  9 10 11]`