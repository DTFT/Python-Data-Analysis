# DataFrame 类型

DataFrame类型由共用相同索引的一组列组成

DataFrame是一个表格型的数据类型，每列值类型可以不同

DataFrame既有行索引（index），也有列索引（column）

DataFrame常用于表达二维数据，但也可以表达多维数据

DataFrame是二维带“标签”数组

![1536736784131](C:\Users\DR2016~1\AppData\Local\Temp\1536736784131.png)



## DataFrame类型创建

```python
# 由二维ndarray对象创建
In [1]: import pandas as pd

In [2]: import numpy as np

In [3]: d = pd.DataFrame(np.arange(10).reshape(2,5))

In [4]: d
Out[4]:
   0  1  2  3  4
0  0  1  2  3  4
1  5  6  7  8  9

# 从一维ndarray对象字典创建
In [5]: dt = {'one': pd.Series([1,2,3],index=['a','b','c']),
   ...: 'two': pd.Series([9,8,7,6], index=['a','b','c','d'])}

In [6]: d = pd.DataFrame(dt)

In [7]: d
Out[7]:
   one  two
a  1.0    9
b  2.0    8
c  3.0    7
d  NaN    6

In [8]: pd.DataFrame(dt, index=['b','c','d'], columns=['two', 'three'])
Out[8]:
   two three
b    8   NaN
c    7   NaN
d    6   NaN

# 从列表类型的字典创建
In [13]: dl = {'one': [1,2,3,4], 'two': [9,8,7,6]}
    In [15]: d = pd.DataFrame( dl, index = ['a','b','c','d'])

In [16]: d
Out[16]:
   one  two
a    1    9
b    2    8
c    3    7
d    4    6


In [18]: dl ={ '城市':['北京','上海','广州','深圳','沈阳'],
    ...: '环比': [101.5,101.2,101.3,102.0,100.1],
    ...: '同比': [120.7,127.3,119.4,140.9,101.4],
    ...: '定基': [121.4,127.8,120.0,145.5,101.6]}

In [19]: d = pd.DataFrame( dl, index=['c1','c2','c3','c4','c5'])

In [20]: d
Out[20]:
    城市     环比     同比     定基
c1  北京  101.5  120.7  121.4
c2  上海  101.2  127.3  127.8
c3  广州  101.3  119.4  120.0
c4  深圳  102.0  140.9  145.5
c5  沈阳  100.1  101.4  101.6


In [21]: d.index
Out[21]: Index(['c1', 'c2', 'c3', 'c4', 'c5'], dtype='object')

In [22]: d.columns
Out[22]: Index(['城市', '环比', '同比', '定基'], dtype='object')

In [23]: d.values
Out[23]:
array([['北京', 101.5, 120.7, 121.4],
       ['上海', 101.2, 127.3, 127.8],
       ['广州', 101.3, 119.4, 120.0],
       ['深圳', 102.0, 140.9, 145.5],
       ['沈阳', 100.1, 101.4, 101.6]], dtype=object)

In [24]: d['同比']
Out[24]:
c1    120.7
c2    127.3
c3    119.4
c4    140.9
c5    101.4
Name: 同比, dtype: float64
        
In [27]: d.loc['c2']
Out[27]:
城市       上海
环比    101.2
同比    127.3
定基    127.8
Name: c2, dtype: object

In [28]: d['同比']['c2']
Out[28]: 127.3
```

