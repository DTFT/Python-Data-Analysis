# pyplot的中文显示



**Python 并不默认支持中文显示，需要rcParams修改字体实现，SimHei 是黑体**

```python
import matplotlib.pyplot as plt
import numpy as np 
import matplotlib

# 修改字体
matplotlib.rcParams['font.family']='SimHei'
plt.plot([3, 1, 4, 5, 2])
plt.ylabel("纵轴（值）")
plt.savefig('test', dpi=600)
plt.show()

```

![1536630896669](C:\Users\DR2016~1\AppData\Local\Temp\1536630896669.png)



|     属性      |                   说明                   |
| :-----------: | :--------------------------------------: |
| 'font.family' |              显示字体的名字              |
| 'font.style'  |  字体风格，正常'normal'或 斜体'italic'   |
|  'font.size'  | 字体大小，整数字号或者'large'、'x-small' |





![1536630974670](C:\Users\DR2016~1\AppData\Local\Temp\1536630974670.png)



```python
import matplotlib.pyplot as plt
import numpy as np 
import matplotlib

# 修改字体, 会改变全局字体
matplotlib.rcParams['font.family']='STSong'
matplotlib.rcParams['font.size']=20

a = np.arange(0.0, 5.0, 0.02)

plt.xlabel('横轴：时间')
plt.ylabel('纵轴：振幅')
plt.plot(a, np.cos(2*np.pi*a), 'r--')

plt.show()
```



![1536631197736](C:\Users\DR2016~1\AppData\Local\Temp\1536631197736.png)





Pyplot的中文显示：第二种方法

在有中文输出的地方，增加一个属性**fontproperties**

```python
import matplotlib.pyplot as plt
import numpy as np 

a = np.arange(0.0, 5.0, 0.02)

# 修改字体,不修改全局字体
plt.xlabel('横轴：时间', fontproperties='SimHei',fontsize=20)
plt.ylabel('纵轴：振幅', fontproperties='SimHei',fontsize=20)
plt.plot(a, np.cos(2*np.pi*a), 'r--')

plt.show()
```

