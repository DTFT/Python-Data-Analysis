## numpy的统计函数

![1536285169781](C:\Users\DR2016~1\AppData\Local\Temp\1536285169781.png)



```python
In [1]: import numpy as np

In [2]: a = np.arange(15).reshape(3,5)

In [3]: a
Out[3]:
array([[ 0,  1,  2,  3,  4],
       [ 5,  6,  7,  8,  9],
       [10, 11, 12, 13, 14]])

In [4]: np.sum(a)
Out[4]: 105

In [5]: np.mean(a,axis=1)
Out[5]: array([ 2.,  7., 12.])

In [6]: np.mean(a,axis=0)
Out[6]: array([5., 6., 7., 8., 9.])

In [7]: np.average(a, axis=0 ,weights=[10, 5, 1])
Out[7]: array([2.1875, 3.1875, 4.1875, 5.1875, 6.1875])

In [8]: np.std(a)
Out[8]: 4.320493798938574

In [9]: np.var(a)
Out[9]: 18.666666666666668
```



![1536285737887](C:\Users\DR2016~1\AppData\Local\Temp\1536285737887.png)



```python
In [1]: import numpy as np

In [2]: b = np.arange(15,0,-1).reshape(3,5)

In [3]: b
Out[3]:
array([[15, 14, 13, 12, 11],
       [10,  9,  8,  7,  6],
       [ 5,  4,  3,  2,  1]])

In [4]: np.max(b)
Out[4]: 15

In [5]: np.argmax(b)
Out[5]: 0

In [6]: np.unravel_index(np.argmax(b), b.shape)
Out[6]: (0, 0)

In [7]: np.ptp(b)
Out[7]: 14

In [8]: np.median(b)
Out[8]: 8.0
```

