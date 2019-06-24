# 第八章  pandas入门

作者：李昕

单位：中国石油大学（华东）

本章重点难点：pandas基本功能，汇总与统计，处理数据缺失

## 1. pandas的数据结构介绍
## 2. 基本功能
## 3. 汇总和计算描述统计
## 4. 处理缺失数据
## 5. 层次化索引

## 一、Pandas库的使用

1. Dataframe.head(`number`)  提取出Dataframe的前几个
2. Dataframe.describe() 

![1558427863613]()

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