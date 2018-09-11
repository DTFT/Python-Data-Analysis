# pyplot 基础图表函数



![1536650840081](C:\Users\DR2016~1\AppData\Local\Temp\1536650840081.png)



![1536650900597](C:\Users\DR2016~1\AppData\Local\Temp\1536650900597.png)



![1536650922253](C:\Users\DR2016~1\AppData\Local\Temp\1536650922253.png)



## 饼图绘制

```python
import matplotlib.pyplot as plt

labels = 'Frogs', 'Hogs', 'Dogs', 'Logs'
sizes = [15,30,45,10]
explode = (0,0.1,0,0)

plt.pie(sizes, explode=explode, labels=labels, autopct='%1.1f%%',
        shadow=False, startangle=90)

# x y 方向尺寸相当
plt.axis('equal')
plt.show()
```

![1536651299370](C:\Users\DR2016~1\AppData\Local\Temp\1536651299370.png)



## 直方图绘制



```python
import matplotlib.pyplot as plt
import numpy as np

np.random.seed(0)
mu, sigma = 100, 20  #均值和标准差
a = np.random.normal(mu, sigma, size=100)

# 第二个参数 bin 直方图的个数
# 第三个参数 normed 元素个数归一化为概率， 置0为元素个数
# alpha 透明度
plt.hist(a, 20, normed=1, histtype='stepfilled', facecolor='b', alpha=0.75)
plt.title('Histogram')

plt.show()
```

![1536652211852](C:\Users\DR2016~1\AppData\Local\Temp\1536652211852.png)



## 极坐标图



```python
import matplotlib.pyplot as plt
import numpy as np

N = 20
theta = np.linspace(0.0, 2 * np.pi, N, endpoint=False)

radii = 10 * np.random.rand(N)   # 0-1之间随机数
width = np.pi / 4* np.random.rand(N)

ax = plt.subplot(111, projection='polar')
bars = ax.bar(theta, radii, width=width,bottom=0.0)

for r, bar in zip(radii, bars):
    bar.set_facecolor(plt.cm.viridis(r / 10.))
    bar.set_alpha(0.5)

plt.show()
```

![1536653444609](C:\Users\DR2016~1\AppData\Local\Temp\1536653444609.png)



## 散点图



