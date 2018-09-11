# pyplot 的plot() 函数

![1536629895339](C:\Users\DR2016~1\AppData\Local\Temp\1536629895339.png)



```python
import matplotlib.pyplot as plt
import numpy as np 

a = np.arange(10)
plt.plot(a, a*1.5, a, a*2.5, a, a*3.5, a, a*4.5)
plt.show()
```

![1536630051563](C:\Users\DR2016~1\AppData\Local\Temp\1536630051563.png)

![1536630120472](C:\Users\DR2016~1\AppData\Local\Temp\1536630120472.png)

![1536630135925](C:\Users\DR2016~1\AppData\Local\Temp\1536630135925.png)



![1536630317640](C:\Users\DR2016~1\AppData\Local\Temp\1536630317640.png)



```python
import matplotlib.pyplot as plt
import numpy as np 

a = np.arange(10)
plt.plot(a, a*1.5, 'go-', a, a*2.5, 'rx', a, a*3.5, '*', a, a*4.5, 'b-.')
plt.show()
```

![1536630448906](C:\Users\DR2016~1\AppData\Local\Temp\1536630448906.png)



![1536630543940](C:\Users\DR2016~1\AppData\Local\Temp\1536630543940.png)

