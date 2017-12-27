# JVM 调优总结

## 调优参数

### 堆内存相关

- 初始堆内存大小
 ```-Xms1024m```

- 最大堆内存大小
 ```-Xmx1024m```
 
- 年轻代大小(Eden + 2 survivor)
 ```-Xmn512m```

- 持久代初始大小
 ```-XX:PermSize=300m```
 
- 持久代最大大小
 ```-XX:MaxPermSize=300M```

- 线程堆栈大小
 ```-Xss256k```

### 堆外内存相关

- 最大堆外内存, 默认取Runtime.getRuntime().maxMemory(), 该值通常为最大堆内存的80% ~ 90%左右, 可能因环境而异
 ```-XX:MaxDirectMemorySize=512m```