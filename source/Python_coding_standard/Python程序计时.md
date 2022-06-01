# Python程序计时
20220601  
对于每一个程序，需要他们的运行时间  

```
import time
time_start = time.time()
main()
time_end = time.time()
print('time cost', time_end - time_start, 's')
```