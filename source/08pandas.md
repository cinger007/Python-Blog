# 第八章  pandas入门

作者：李昕

单位：中国石油大学（华东）

本章重点难点：pandas基本功能，汇总与统计，处理数据缺失

## 1. pandas的数据结构介绍

#### 1.1 Series

#### 1.2 DataFrame

#### 1.3 索引对象

## 2. 基本功能

本节功能围绕dataframe展开

#### 2.1 重新索引

#### 2.2 丢弃指定轴上的项

#### 2.3 索引、选取和过滤

#### 2.4 算术运算和数据对齐

#### 2.5  函数应用和映射

#### 2.6 排序和排名

扑克牌抽取，《利用python进行数据分析》P284

## 3. 汇总和计算描述统计

#### 3.1 通用统计函数

#### 3.2 唯一值、值计算、成员资格

## 4. 处理缺失数据

#### 4.1 滤除缺失数据

#### 4.2 填充缺失数据

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