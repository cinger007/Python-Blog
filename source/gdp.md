
## 顾客已离开会考虑回旅馆
1. 还回家回家看看
2. 苦苦解决了


```python
import matplotlib.pyplot as plt
import pandas as pd

#为了正确显示汉字
from pylab import mpl
mpl.rcParams['font.sans-serif'] = ['KaiTi']
mpl.rcParams['font.serif'] = ['KaiTi']

#读取数据
df = pd.read_csv('e:/gdpallyear_color.csv',header=None)  
#print(df)

#画图
plt.figure()
for year in range(1960,2018):
    plt.cla()#清空屏幕
    data = df[df[4]==year].head(10)[::-1]#截取数据
    ax = data[3].plot(kind='barh',color=data[5]) #绘制
    ax.set_yticklabels(data[1])#设置标签
    ax.set_title(str(year))#设置标题
    plt.pause(0.5)#暂停，出现动画效果
```


```python

```
