# 机器学习 线性回归实验二

Location: China University of Petroleum   Weather: Sunny

今天是机器学习的上机的第一课，首先从Python中的pandas库的开始学习

## 一、Pandas库的使用

```python
path =  'data/ex1data1.txt'
data = pd.read_csv(path, header=None, names=['Population', 'Profit'])
data.head()
data.describe()
```

1. Dataframe.head(`number`)  提取出Dataframe的前几个
2. Dataframe.describe() 

![1558427863613](mdfile/test1/timg.jpg)

​	count: 计数

​	mean：计算平均值

​	std：计算标准差

​	min：计算最小值

​	max：计算最大值

​	25%，50%，75%：则是返回第25%个

3.Dataframe.shape 返回的是一个tuple

​	获取行数使用 rows = Dataframe.shape[0]

​	获取列数使用 cols = Dataframe.shape[1]

4.DataFrame.insert(*loc*, *column*, *value*, *allow_duplicates=False*)

​	插入一列数据，loc指插入的位置，column指插入的列的列名，value为需要插入的值

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

## 三、单变量线性回归

![1558574062135](mdfile/test1/0b76b95d4c45fbfcac7959f0eceed687.jpg)

通过本图我们可以发现在学习率为0.02的情况下带来的代价函数的下降效果是最佳的。



源代码：

```python
import sklearn.tree
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt


def computeCost(X, y, theta):
    j = np.power(((X * theta.T) - y), 2)
    J = np.sum(j) / (2 * len(y))
    return J


def gradientDescent(X, y, theta, alpha, iters):
    rows, cols, theta_compute = theta.shape[0], theta.shape[1], np.matrix(np.zeros(theta.shape), dtype=float)
    costs = []
    for i in range(iters):
        error = (X * theta.T) - y
        for row in range(rows):
            for col in range(cols):
                term = np.multiply(error, X[:, col])
                theta_compute[row, col] = theta[row, col] - np.sum(term) * alpha / len(X)
            costs.append(computeCost(X, y, theta_compute))
            theta = theta_compute
    return theta, costs


path = 'data/ex1data1.txt'
data = pd.read_csv(path, header=None, names=['Population', 'Profit'])
data.insert(0, 'Ones', 1)
cols = data.shape[1]  # 获取列数
X = data.iloc[:, 0:cols - 1]
y = data.iloc[:, cols - 1:cols]
X = np.matrix(X.values)
y = np.matrix(y.values)
theta = np.matrix(np.array([0, 0]), dtype=float)  # 初始化theta为一个1*2空矩阵
# cost = computeCost(X, y, theta)
# alpha, iters = 0.015, 10000
# theta_compute, costs = gradientDescent(X, y, theta, alpha, iters)

alpha_list, iters_list = [0.01, 0.015, 0.02], [1000, 2000]
colors = ['b', 'g', 'r', 'c', 'm', 'y', 'k', 'w', 'gold', 'goldenrod', 'b', 'g', 'r', 'c', 'm']
# x = np.linspace(data.Population.min(), data.Population.max(), 100)
# f = theta_compute[0, 0] + (theta_compute[0, 1] * x)
# fig, ax = plt.subplots(figsize=(12, 8))
# ax.plot(x, f, 'r', label='Prediction')
# ax.scatter(data.Population, data.Profit, label='Traning Data')
# ax.legend(loc=2)
# plt.show()
# print(theta_compute, costs)

fig, ax = plt.subplots(figsize=(12, 8))
color_index = 0
for alpha in alpha_list:
    for iters in iters_list:
        theta_compute, costs = gradientDescent(X, y, theta, alpha, iters)
        ax.plot(np.arange(iters), costs, label='a= '+str(alpha)+' '+'iters= ' + str(iters))
        print(theta_compute, costs)
ax.set_xlabel('Iterations')
ax.set_ylabel('Costs')
plt.legend()
plt.show()
```

