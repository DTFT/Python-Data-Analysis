# Series 类型

Panda是Python的第三方库，提供高性能易用数据类型和分析工具

```python
import pandas as pd
```

|       Numpy        |       Pandas       |
| :----------------: | :----------------: |
|    基础数据类型    |    扩展数据类型    |
| 关注数据的结构表达 | 关注数据的应用表达 |
|  维度：数据见关系  |   数据与索引关系   |



两个数据类型 ： **Series**，**DataFrame**

------

## Series

Series类型是由一组数据及与之相关的数据索引组成

Series 是一维带“标签”数组

### Series创建

```python
import pandas as pd

# 从Python列表 
a = pd.Series([9,8,7,6])

a
Out[7]: 
0    9
1    8
2    7
3    6
dtype: int64
 
# 自定义索引
a = pd.Series([9,8,7,6],index=['a','b','c','d'])

a
Out[9]: 
a    9
b    8
c    7
d    6
dtype: int64
```

```python
In [1]: import pandas as pd

# 标量值创建
In [2]: s = pd.Series(25, index=['a','b','c'])

In [3]: s
Out[3]:
a    25
b    25
c    25
dtype: int64
    
# 从字典类型创建
In [4]: d = pd.Series({'a':9,'b':8,'c':7})

In [5]: d
Out[5]:
a    9
b    8
c    7
dtype: int64

In [6]: e = pd.Series({'a':9,'b':8,'c':7},index=['c','a','b','d'])

In [7]: e
Out[7]:
c    7.0
a    9.0
b    8.0
d    NaN
dtype: float64
    
# 从 ndarray类型创建
In [8]: import numpy as np

In [9]: n = pd.Series(np.arange(5))

In [10]: n
Out[10]:
0    0
1    1
2    2
3    3
4    4
dtype: int32
    
In [12]: m = pd.Series(np.arange(5),index=np.arange(9,4,-1))

In [13]: m
Out[13]:
9    0
8    1
7    2
6    3
5    4
dtype: int32

```



### Series 类型基本操作

```python
In [14]: b = pd.Series([9,8,7,6],['a','b','c','d'])

In [15]: b
Out[15]:
a    9
b    8
c    7
d    6
dtype: int64

In [16]: b.index
Out[16]: Index(['a', 'b', 'c', 'd'], dtype='object')

In [17]: b.values
Out[17]: array([9, 8, 7, 6], dtype=int64)

In [18]: b['b']
Out[18]: 8

In [19]: b[1]
Out[19]: 8

# 自动索引和自定义索引不能混合使用
In [20]: b[['c','d',0]]
Out[20]:
c    7.0
d    6.0
0    NaN
dtype: float64

In [21]: b[['c','d','a']]
Out[21]:
c    7
d    6
a    9
dtype: int64
    
In [22]: b[ :3]
Out[22]:
a    9
b    8
c    7
dtype: int64

In [23]: b[b > b.median()]
Out[23]:
a    9
b    8
dtype: int64

In [24]: np.exp(b)
Out[24]:
a    8103.083928
b    2980.957987
c    1096.633158
d     403.428793
dtype: float64
    
In [25]: 'c' in b
Out[25]: True

In [26]: 0 in b
Out[26]: False
# 提取 索引f对应的值，不存在返回100
In [27]: b.get('f',100)
Out[27]: 100
    
# 对齐操作    
In [30]: a = pd.Series([1,2,3],['c','d','e'])

In [31]: a+ b
Out[31]:
a    NaN
b    NaN
c    8.0
d    8.0
e    NaN
dtype: float64

# name 属性
In [33]: b.name = 'Series对象'

In [34]: b.index.name = '索引列'

In [35]: b
Out[35]:
索引列
a    9
b    8
c    7
d    6
Name: Series对象, dtype: int64

# Series 类型可以随时修改并即可生效
In [36]: b['a'] = 15

IIn [37]: b.name = 'Series'

In [38]: b
Out[38]:
索引列
a    15
b     8
c     7
d     6
Name: Series, dtype: int64

In [39]: b.name
Out[39]: 'Series'

In [40]: b['b','c'] = 20

In [41]: b
Out[41]:
索引列
a    15
b    20
c    20
d     6
Name: Series, dtype: int64
```





