# pyplot的文本显示



![1536648159774](C:\Users\DR2016~1\AppData\Local\Temp\1536648159774.png)



```python
import matplotlib.pyplot as plt
import numpy as np 

a = np.arange(0.0, 5.0, 0.02)
plt.plot(a, np.cos(2*np.pi*a),'r--')

# $  $  Latex语法
plt.xlabel('横轴：时间', fontproperties='SimHei',fontsize=15, color='green')
plt.ylabel('纵轴：振幅', fontproperties='SimHei',fontsize=15)
plt.title(r'正弦波实例 $y=cos(2\pi x)$', fontproperties='SimHei', fontsize=25)
plt.text(2, 1, r'$\mu=100$', fontsize=25)

plt.axis([-1, 6, -2, 2])
# 网格曲线
plt.grid(True)
plt.show()
```



![1536648687674](C:\Users\DR2016~1\AppData\Local\Temp\1536648687674.png)





```python
import matplotlib.pyplot as plt
import numpy as np 

a = np.arange(0.0, 5.0, 0.02)
plt.plot(a, np.cos(2*np.pi*a),'r--')

# $  $  Latex语法
plt.xlabel('横轴：时间', fontproperties='SimHei',fontsize=15, color='green')
plt.ylabel('纵轴：振幅', fontproperties='SimHei',fontsize=15)
# r''防止转义
plt.title(r'正弦波实例 $y=cos(2\pi x)$', fontproperties='SimHei', fontsize=25)

# 注释
plt.annotate(r'$\mu=100$', xy=(2,1), xytext=(3,1.5),
             arrowprops=dict(facecolor='black', shrink=0.1, width=2))

plt.axis([-1, 6, -2, 2])
# 显示网格线
plt.grid(True)
plt.show()
```





![1536649218343](C:\Users\DR2016~1\AppData\Local\Temp\1536649218343.png)