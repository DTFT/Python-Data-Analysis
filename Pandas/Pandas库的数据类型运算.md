# Pandas库的数据类型运算
-------------------
## 算数运算法则
- 算数运算根据行列索引，补齐后运算，运算默认产生浮点数
- 补齐是缺项填充NaN（空值）
- 二维和一维、一维和零维间为广播运算
- 采用 + - * /符号运行的二元运算产生新的对象

```python
In [2]: import numpy as np

In [3]: import pandas as pd

In [4]: a = pd.DataFrame(np.arange(12).reshape(3,4))

In [5]: a
Out[5]:
   0  1   2   3
0  0  1   2   3
1  4  5   6   7
2  8  9  10  11

In [6]: b = pd.DataFrame(np.arange(20).reshape(4,5))

In [7]: b
Out[7]:
    0   1   2   3   4
0   0   1   2   3   4
1   5   6   7   8   9
2  10  11  12  13  14
3  15  16  17  18  19

In [8]: a + b
Out[8]:
      0     1     2     3   4
0   0.0   2.0   4.0   6.0 NaN
1   9.0  11.0  13.0  15.0 NaN
2  18.0  20.0  22.0  24.0 NaN
3   NaN   NaN   NaN   NaN NaN

In [9]: a * b
Out[9]:
      0     1      2      3   4
0   0.0   1.0    4.0    9.0 NaN
1  20.0  30.0   42.0   56.0 NaN
2  80.0  99.0  120.0  143.0 NaN
3   NaN   NaN    NaN    NaN NaN

# fiil_value 空元素填充
In [10]: b.add(a,fill_value=100)
Out[10]:
       0      1      2      3      4
0    0.0    2.0    4.0    6.0  104.0
1    9.0   11.0   13.0   15.0  109.0
2   18.0   20.0   22.0   24.0  114.0
3  115.0  116.0  117.0  118.0  119.0

In [11]: a.mul(b,fill_value=0)
Out[11]:
      0     1      2      3    4
0   0.0   1.0    4.0    9.0  0.0
1  20.0  30.0   42.0   56.0  0.0
2  80.0  99.0  120.0  143.0  0.0
3   0.0   0.0    0.0    0.0  0.0

In [18]: b = pd.DataFrame(np.arange(20).reshape(4,5))

In [19]: c = pd.Series(np.arange(4))

In [20]: c
Out[20]:
0    0
1    1
2    2
3    3
dtype: int32

# 不同维度间为广播运算，一维Series默认在轴1参与运算
In [21]: c - 10
Out[21]:
0   -10
1    -9
2    -8
3    -7
dtype: int32

# b每一行 - c
In [22]: b - c
Out[22]:
      0     1     2     3   4
0   0.0   0.0   0.0   0.0 NaN
1   5.0   5.0   5.0   5.0 NaN
2  10.0  10.0  10.0  10.0 NaN
3  15.0  15.0  15.0  15.0 NaN

# b每一列 - c
In [23]: b.sub(c,axis=0)
Out[23]:
    0   1   2   3   4
0   0   1   2   3   4
1   4   5   6   7   8
2   8   9  10  11  12
3  12  13  14  15  16

```
----
## 比较运算法则
- 比较运算只能比较相同索引的元素，不进行不去
- 二维和一维、一维和零维间为广播运算
- 采用 > 、< 、>= 、<= 、= 、 == 、 != 等符号进行的二元运算产生布尔对象

```python

In [24]: a
Out[24]:
   0  1   2   3
0  0  1   2   3
1  4  5   6   7
2  8  9  10  11

In [25]: d = pd.DataFrame(np.arange(12,0,-1).reshape(3,4))

In [26]: d
Out[26]:
    0   1   2  3
0  12  11  10  9
1   8   7   6  5
2   4   3   2  1

# 同维度运算，尺寸一致
In [27]: a > d
Out[27]:
       0      1      2      3
0  False  False  False  False
1  False  False  False   True
2   True   True   True   True

In [28]: a == d
Out[28]:
       0      1      2      3
0  False  False  False  False
1  False  False   True  False
2  False  False  False  False

In [30]: c = pd.Series(np.arange(4))

In [31]: c
Out[31]:
0    0
1    1
2    2
3    3
dtype: int32

# 不同维度，广播运算，默认在1轴
In [32]: a > c
Out[32]:
       0      1      2      3
0  False  False  False  False
1   True   True   True   True
2   True   True   True   True

In [33]: c > 0
Out[33]:
0    False
1     True
2     True
3     True
dtype: bool

```
