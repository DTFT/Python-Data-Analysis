# Matplolib.pyplot

![1536627988564](C:\Users\DR2016~1\AppData\Local\Temp\1536627988564.png)



```python
import matplotlib.pyplot as plt

plt.plot([0,2,4,6,8],[3,1,4,5,2])
plt.ylabel("grade")
# 设定横纵坐标尺度,x -1,10  y 0, 6 
plt.axis([-1,10,0,6])
# 将输出图像存储为文件
plt.savefig('test', dpi=600) #png文件
plt.show()

```



![1536629026693](C:\Users\DR2016~1\AppData\Local\Temp\1536629026693.png)



```python
import matplotlib.pyplot as plt
import numpy as np 

def f(t):
    return np.exp(-t) * np.cos(2*np.pi*t)

a = np.arange(0.0, 5.0, 0.02)

plt.subplot(211)
plt.plot(a, f(a))

plt.subplot(2,1,2)
plt.plot(a, np.cos(2*np.pi*a), 'r--')
plt.show()
```

![1536629372274](C:\Users\DR2016~1\AppData\Local\Temp\1536629372274.png)





