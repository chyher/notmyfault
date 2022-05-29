## 多线程编程

- 多线程操作
  - pthread_create **线程创建函数**
  - pthread_join **等待线程结束函数**
  - pthread_exit **线程退出函数**
  - pthread_cancel **线程取消函数**
  - pthread_self **获取当前线程ID函数**
  - pthread_detach **分离释放线程函数**
    - detach模式（使线程处于unjoinable状态）可在 **pthread_create** 中设置；也可通过该函数设置某个线程为detach模式；也可在线程创建前使用 **pthread_attr_init** 函数设置。
    - 线程有态joinable和unjoinable两种状态，默认为joinable，即默认线程退出时若不调用 **pthread_join** 函数，线程资源不会释放。反之unjoinable在线程退出时，线程资源会自动释放。
  - *etc =》https://blog.csdn.net/baidu_35692628/article/details/69487525

注：多线程的变量保护基本都会造成开销增大，程序运行会有一些影响，因辩证考虑是否选用

- 多线程变量冲突
  - PV操作

    - wait();  // 使用
    - signal();  // 释放

    

  - 互斥锁

    - mutex

  

  - 原子操作atomic

    - c语言库

      stdatomic.h

    - 实际为单个cpu做的一次独立不可分割的操作，单指令即可视作一次原子操作
      - 加法（实际有先取值后加法，先加法后取值）
      - 减法
      - 与
      - 或
      - 异或
      - 比较并交换（CAS）

  

- 多cpu下多个线程变量冲突

  出现问题根源：

  由于多cpu下，每个cpu有自己的cache缓存，而磁盘区域仅有一块，cpu写入和读取操作可能仅访问cache，导致各个cpu对同一块磁盘内存访问不正确

  - 内存屏障（memory barrier）

