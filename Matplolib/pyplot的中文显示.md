# pyplot的中文显示



![1536630840635](C:\Users\DR2016~1\AppData\Local\Temp\1536630840635.png)



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





![1536630963657](C:\Users\DR2016~1\AppData\Local\Temp\1536630963657.png)



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





![1536631408825](C:\Users\DR2016~1\AppData\Local\Temp\1536631408825.png)



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

