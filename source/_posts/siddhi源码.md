---
title: siddhi源码
tags: []
originContent: ''
categories: []
toc: false
date: 2019-10-02 10:12:52
---



1. 不同的App互相不可见，那么我们的程序有多个App作用在同一个流该如何解决?
> The stream processing constructs, such as streams and queries, defined within a Siddhi App is not visible even to the other Siddhi Apps running in the same JVM.

2. 相同的流处理逻辑放在一个App中，通过内存接收器和内存源配置 
> It is also recommended to move the repeated steam processing logics that exist in multiple Siddhi Applications, such as message retrieval and preprocessing, to a common Siddhi Application, whereby reducing code duplication and improving maintainability.
In this case, to pass the events from one Siddhi App to another, users can configure common topic using **In-Memory Sink** and **In-Memory Source** in order to communicate between them.
3. **In-Memory Sink**
4.playback是啥
把数据上的时间戳当成current_time 时间流逝以时间戳为准，不以真实时间为准（存疑，参数问题）
5. QueryCallback和StreamCallback区别？？
todo
6. 如果不并发数据直接进入streamJunction 
7. Metrics:一款监控指标的度量类库
8. receivers个数取决于？
9. 异步情况下数据发送到dis
![image.png](https://i.loli.net/2019/10/02/x95JpfEXqyDnecQ.png)
![image.png](https://i.loli.net/2019/10/02/hNrOVY2XzUkt9DQ.png)