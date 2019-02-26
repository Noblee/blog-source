---
title: 深入了解HotSpot虚拟机
tags:
  - 语言
  - Java
  - 笔记
  - 进阶
originContent: >-
  <!DOCTYPE html>

  <html>

  <head>

  <title>深入了解HotSpot虚拟机 - 幕布</title>

  <meta charset="utf-8"/>

  <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />

  <meta name="renderer" content="webkit"/>

  <meta name="author" content="mubu.com"/>

  </head>

  <body style="margin: 50px 20px;color: #333;font-family: 'Helvetica
  Neue','Hiragino Sans GB','WenQuanYi Micro Hei','Microsoft Yahei',sans-serif;">

  <div class="export-wrapper"><div style="font-size: 24px; padding: 20px 15px
  0;"><div style="padding-bottom: 10px">深入了解HotSpot虚拟机</div><div
  style="background: #e5e6e8; height: 1px; margin-bottom: 20px;"></div></div><ul
  style="list-style: disc outside;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">Java内存区域简析</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">运行时数据区域</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">线程私有</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;">PC</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">指向正在运行的虚拟机字节码，执行Native程序时设置为空。</span></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">没有<span class="bold" style="font-weight:
  bold;">OutOfMemoryError</span>异常</span></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">Java虚拟机栈</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">栈帧</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">局部变量表</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">包括各种局部变量（基本类型和引用类型以及<span
  class="bold" style="font-weight: bold;">returnAddress</span>类型）</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">何为Slot</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">局部变量空间</span></li></ul></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">重要特点：编译时即可决定。</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">此区域可能出现的异常</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">Stack Overflow</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">线程请求栈深度大于JVM允许深度。</span></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;"><span class="bold" style="font-weight:
  bold;">OutOfMemoryError</span>异常</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">动态扩展后内存不够</span></li></ul></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">操作数栈</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">动态链接</span></li><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align:
  top;">方法出口</span></li></ul></li></ul></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;"><span
  class="italic" style="font-style:
  italic;">本地方法栈</span></span></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">Java进程私有</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">Java堆</span></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">方法区</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;"><span
  class="italic" style="font-style:
  italic;">运行时常量区</span></span></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node"
  images="%5B%7B%22id%22%3A%223521691fa117260c9-2391178%22%2C%22uri%22%3A%22document_image%2F08ccf9bb-8585-4859-b0c5-65c03af88dea-2391178.jpg%22%2C%22ow%22%3A675%2C%22oh%22%3A350%2C%22w%22%3A750%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img
  src="https://img.mubu.com/document_image/08ccf9bb-8585-4859-b0c5-65c03af88dea-2391178.jpg"
  style="max-width: 720px; width: 750px;"
  class="attach-img"></div></li></ul></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;">对象的创建</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">1. 虚拟机视角</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;">分配内存</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">如何保证对象创建时内存分配的原子性（不会被其他线程打断）</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">CAS（Compare and Switch）</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">不同线程存储空间不同</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">数据结构：TLAB（Thread Local Allocation
  Buffer）</span></li></ul></li></ul></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">内存空间初试化（全部设为0）</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">设置对象头</span></li></ul></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;">2.
  Java程序视角</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align:
  top;">&lt;init&gt;</span></li></ul></li><li style="line-height: 22px;"><span
  class="content mubu-node"
  images="%5B%7B%22id%22%3A%2295169258b17b614-2391178%22%2C%22uri%22%3A%22document_image%2F1214eb2f-6a4b-4048-922a-14743baf5987-2391178.jpg%22%2C%22ow%22%3A729%2C%22oh%22%3A909%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img
  src="https://img.mubu.com/document_image/1214eb2f-6a4b-4048-922a-14743baf5987-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li></ul></li><li
  class="collapsed" style="line-height: 22px;"><span class="content mubu-node
  collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">对象的内存布局</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">对象头（32bit or 64 bit）</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node"
  images="%5B%7B%22id%22%3A%22c6169258da2b1073%22%2C%22uri%22%3A%22document_image%2Fca019504-e6af-4a99-8f5e-ec7763710962-2391178.jpg%22%2C%22ow%22%3A720%2C%22oh%22%3A250%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img
  src="https://img.mubu.com/document_image/ca019504-e6af-4a99-8f5e-ec7763710962-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node"
  images="%5B%7B%22id%22%3A%22201692594aa2c059-2391178%22%2C%22uri%22%3A%22document_image%2F64661f1b-b05b-481b-87a5-108a2a8bc271-2391178.jpg%22%2C%22ow%22%3A1066%2C%22oh%22%3A176%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img
  src="https://img.mubu.com/document_image/64661f1b-b05b-481b-87a5-108a2a8bc271-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">对象的访问定位</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">有两中方式如图所示（HotSpot采用第二种方式）</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node"
  images="%5B%7B%22id%22%3A%2226c16928c1297f0ea-2391178%22%2C%22uri%22%3A%22document_image%2Fb327a8ae-0008-4527-b014-e923a00bd276-2391178.jpg%22%2C%22ow%22%3A729%2C%22oh%22%3A363%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align:
  top;">好处：实例区域的对象被移动时reference指针不需要改变，只改变句柄池里的内容</span><div style="padding: 3px
  0"><img
  src="https://img.mubu.com/document_image/b327a8ae-0008-4527-b014-e923a00bd276-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li><li
  style="line-height: 22px;"><span class="content mubu-node"
  images="%5B%7B%22id%22%3A%221da16928c189ad118-2391178%22%2C%22uri%22%3A%22document_image%2F02b827d8-0979-45ed-ae3a-18051b5f0105-2391178.jpg%22%2C%22ow%22%3A765%2C%22oh%22%3A373%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;">速度更快</span><div style="padding: 3px
  0"><img
  src="https://img.mubu.com/document_image/02b827d8-0979-45ed-ae3a-18051b5f0105-2391178.jpg"
  style="max-width: 720px;"
  class="attach-img"></div></li></ul></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">垃圾回收器</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">回收位置：Java堆和方法区</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">对象生死？（如何标记对象）</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;">计数引用法</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">问题：难以解决对象循环引用问题</span></li></ul></li><li
  style="line-height: 28px;"><span class="content mubu-node" color="#dc2d1e"
  heading="2" style="color: rgb(220, 45, 30); line-height: 28px; min-height:
  28px; font-size: 21px; display: inline-block; vertical-align:
  top;">可达性分析算法</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px;
  min-height: 22px; font-size: 14px; display: inline-block; vertical-align:
  top;">GC roots</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px;
  min-height: 22px; font-size: 14px; display: inline-block; vertical-align:
  top;">本地变量表的reference</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51);
  line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">方法区静态属性引用的对象</span></li><li style="line-height:
  22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51,
  51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;">方法区中常量引用的对象</span></li><li
  style="line-height: 22px;"><span class="content mubu-node" color="#333333"
  style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size:
  14px; display: inline-block; vertical-align: top;"><span class="italic"
  style="font-style:
  italic;">本地方法栈中Native方法所引用的对象</span></span></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" color="#333333"
  style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size:
  14px; display: inline-block; vertical-align: top;">实际情况：可达性分析+引用辅助类</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" color="#333333"
  style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size:
  14px; display: inline-block; vertical-align: top;">强引用（普通引用）</span></li><li
  style="line-height: 22px;"><span class="content mubu-node" color="#333333"
  style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size:
  14px; display: inline-block; vertical-align:
  top;">软引用（SoftReference）</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51);
  line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">在内存溢出之前会把其列入回收范围。</span></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" color="#333333"
  style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size:
  14px; display: inline-block; vertical-align: top;">弱引用</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" color="#333333"
  style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size:
  14px; display: inline-block; vertical-align:
  top;">被弱引用关联的对象只能生存到下一次垃圾收集发生之前</span></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51,
  51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;">虚引用</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51,
  51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align:
  top;">为一个对象设置虚引用关联的唯一目的就是能在这个对象被收集器回收时收到一个系统通知。</span></li></ul></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">生存还是死亡</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">方法区回收(方法区如何标记)</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align: top;">回收废弃常量</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">此常量已经“实在”没有用了</span></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">无用的类</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">同时满足以下三点为无用的类</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">堆中不存在任何任何这个类的实例了</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">加载该类的Classloader已经被回收</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">该类的Class对象没有在任何地方被引用（防止反射使用）</span></li><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">在大量使用反射、动态代理、CGLib 等ByteCode 框架、动态生成JSP 以及OSGi 这类频繁自定义ClassLoader
  的场景都需要虚拟机具备类卸载的功能，以保证永生代不会溢出。</span></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">垃圾-收集算法</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li class="collapsed" style="line-height:
  22px;"><span class="content mubu-node collapsed" style="line-height: 22px;
  min-height: 22px; font-size: 14px; display: inline-block; vertical-align:
  top;">标记清除算法 Mark-Sweep</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node"
  images="%5B%7B%22id%22%3A%22a01692963eadf064-2391178%22%2C%22uri%22%3A%22document_image%2F00d3f18a-e32b-4424-98bd-d4063846898a-2391178.jpg%22%2C%22ow%22%3A621%2C%22oh%22%3A332%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;">缺点：碎片太多</span><div style="padding: 3px
  0"><img
  src="https://img.mubu.com/document_image/00d3f18a-e32b-4424-98bd-d4063846898a-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li></ul></li><li
  class="collapsed" style="line-height: 22px;"><span class="content mubu-node
  collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">复制算法(copying)</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align:
  top;">首先将内存分为大小相等的两部分（假设A、B两部分），每次呢只使用其中的一部分（这里我们假设为A区），等这部分用完了，这时候就将这里面还能活下来的对象复制到另一部分内存（这里设为B区）中，然后把A区中的剩下部分全部清理掉。这样一来每次清理都要对一半的内存进行回收操作，这样内存碎片的问题就解决了。</span></li><li
  style="line-height: 22px;"><span class="content mubu-node"
  images="%5B%7B%22id%22%3A%2217e1692968653817e-2391178%22%2C%22uri%22%3A%22document_image%2Fc25a98cb-db1c-493d-8c30-042c09fc2174-2391178.jpg%22%2C%22ow%22%3A603%2C%22oh%22%3A364%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;">HotSpot实现的原型</span><div style="padding:
  3px 0"><img
  src="https://img.mubu.com/document_image/c25a98cb-db1c-493d-8c30-042c09fc2174-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li></ul></li><li
  class="collapsed" style="line-height: 22px;"><span class="content mubu-node
  collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">标记整理（mark compact）</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node"
  images="%5B%7B%22id%22%3A%221841692969246415e-2391178%22%2C%22uri%22%3A%22document_image%2F2b323958-3753-4bd1-a081-0e5178d68f82-2391178.jpg%22%2C%22ow%22%3A606%2C%22oh%22%3A372%7D%5D"
  style="line-height: 22px; min-height: 22px; font-size: 14px; display:
  inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img
  src="https://img.mubu.com/document_image/2b323958-3753-4bd1-a081-0e5178d68f82-2391178.jpg"
  style="max-width: 720px;" class="attach-img"></div></li></ul></li><li
  class="collapsed" style="line-height: 22px;"><span class="content mubu-node
  collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">分代收集算法</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">将对象根据存活周期分为几块，在不同的代使用不同的算法。</span></li></ul></li></ul></li><li
  class="collapsed" style="line-height: 22px;"><span class="content mubu-node
  collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">HotSpot如何何时发起GC</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">枚举根节点</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">问题：枚举全局节点和执行上下文进行标记所需时间太长，并且会导致STW&nbsp;。</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">使用准确形式的GC，不需要一个不漏的检查所有上下文和全局的引用位置。虚拟机通过维护某些数据结构（例如：Java中是使用OopMap，在类加载完成的时候，
  HotSpot 就把对象内什么偏移量上是什么类型的数据计算出来，在JIT 编译过程中，也会在特定的位置记录下楼和寄存器中哪些位置是引用。这样， GC
  在扫描时就可以直接得知这些信息了。</span></li><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">问题：如果为每一条指令都生成对应的OopMap ，那将会需要大量的额外空间，这样GC 的空间成本将会变得很高。</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  class="collapsed" style="line-height: 22px;"><span class="content mubu-node
  collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align: top;">安全点</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">即程序执行时并非在所有地方都能停顿下来开始GC ，只有在到达安全点时才能暂停</span></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">如何保证各个线程都达到安全点并开始GC</span><ul class="children"
  style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align:
  top;">主动式中断</span><ul class="children" style="list-style: disc outside;
  padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content
  mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px;
  display: inline-block; vertical-align:
  top;">设置flag在每个安全点轮询一下。</span></li></ul></li><li style="line-height:
  22px;"><span class="content mubu-node" style="line-height: 22px; min-height:
  22px; font-size: 14px; display: inline-block; vertical-align: top;"><span
  class="italic" style="font-style:
  italic;">强先式中断（没有实际使用过）</span></span></li></ul></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align:
  top;">问题：如果有进程处于Sleep状态或者Blocked状态，不能达到安全点，从而不知道此时有什么对象引用。</span><ul
  class="children" style="list-style: disc outside; padding-bottom: 4px;"><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">安全区域</span><ul class="children" style="list-style: disc
  outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;">安全区域是指在一段代码片段之中，引用关系不会发生变化。在这个区域中的任意地方开始GC 都是安全的。在线程执行到Safe Region
  中的代码时， 首先标识自己巳经进入了Safe Re部on, 那样， 当在这段时间里NM要发起GC 时， 就不用管标识自已为Safe Region
  状态的线程了。在线程要离开Safe Region 时， 它要检查系统是否已经完成了根节点枚举（或者是整个GC 过程）， 如果完成了， 那线程就继续执行，
  否则它就必须等待直到收到可以安全离开Safe Region
  的信号为止。</span></li></ul></li></ul></li></ul></li></ul></li></ul></li><li
  style="line-height: 22px;"><span class="content mubu-node" style="line-height:
  22px; min-height: 22px; font-size: 14px; display: inline-block;
  vertical-align: top;">垃圾收集器3.5</span><ul class="children" style="list-style:
  disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span
  class="content mubu-node" style="line-height: 22px; min-height: 22px;
  font-size: 14px; display: inline-block; vertical-align:
  top;"></span></li></ul></li></ul></li></ul></div>


  </body>

  </html>
categories:
  - Java
toc: false
date: 2019-02-26 20:01:49
---

<!DOCTYPE html>
<html>
<head>
<title>深入了解HotSpot虚拟机 - 幕布</title>
<meta charset="utf-8"/>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<meta name="renderer" content="webkit"/>
<meta name="author" content="mubu.com"/>
</head>
<body style="margin: 50px 20px;color: #333;font-family: 'Helvetica Neue','Hiragino Sans GB','WenQuanYi Micro Hei','Microsoft Yahei',sans-serif;">
<div class="export-wrapper"><div style="font-size: 24px; padding: 20px 15px 0;"><div style="padding-bottom: 10px">深入了解HotSpot虚拟机</div><div style="background: #e5e6e8; height: 1px; margin-bottom: 20px;"></div></div><ul style="list-style: disc outside;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Java内存区域简析</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">运行时数据区域</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">线程私有</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">PC</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">指向正在运行的虚拟机字节码，执行Native程序时设置为空。</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">没有<span class="bold" style="font-weight: bold;">OutOfMemoryError</span>异常</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Java虚拟机栈</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">栈帧</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">局部变量表</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">包括各种局部变量（基本类型和引用类型以及<span class="bold" style="font-weight: bold;">returnAddress</span>类型）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">何为Slot</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">局部变量空间</span></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">重要特点：编译时即可决定。</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">此区域可能出现的异常</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Stack Overflow</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">线程请求栈深度大于JVM允许深度。</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"><span class="bold" style="font-weight: bold;">OutOfMemoryError</span>异常</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">动态扩展后内存不够</span></li></ul></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">操作数栈</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">动态链接</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">方法出口</span></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"><span class="italic" style="font-style: italic;">本地方法栈</span></span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Java进程私有</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">Java堆</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">方法区</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"><span class="italic" style="font-style: italic;">运行时常量区</span></span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%223521691fa117260c9-2391178%22%2C%22uri%22%3A%22document_image%2F08ccf9bb-8585-4859-b0c5-65c03af88dea-2391178.jpg%22%2C%22ow%22%3A675%2C%22oh%22%3A350%2C%22w%22%3A750%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/08ccf9bb-8585-4859-b0c5-65c03af88dea-2391178.jpg" style="max-width: 720px; width: 750px;" class="attach-img"></div></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对象的创建</span>
<!-- more -->
<ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">1. 虚拟机视角</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">分配内存</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">如何保证对象创建时内存分配的原子性（不会被其他线程打断）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">CAS（Compare and Switch）</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">不同线程存储空间不同</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">数据结构：TLAB（Thread Local Allocation Buffer）</span></li></ul></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">内存空间初试化（全部设为0）</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">设置对象头</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">2. Java程序视角</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">&lt;init&gt;</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%2295169258b17b614-2391178%22%2C%22uri%22%3A%22document_image%2F1214eb2f-6a4b-4048-922a-14743baf5987-2391178.jpg%22%2C%22ow%22%3A729%2C%22oh%22%3A909%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/1214eb2f-6a4b-4048-922a-14743baf5987-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对象的内存布局</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对象头（32bit or 64 bit）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%22c6169258da2b1073%22%2C%22uri%22%3A%22document_image%2Fca019504-e6af-4a99-8f5e-ec7763710962-2391178.jpg%22%2C%22ow%22%3A720%2C%22oh%22%3A250%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/ca019504-e6af-4a99-8f5e-ec7763710962-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%22201692594aa2c059-2391178%22%2C%22uri%22%3A%22document_image%2F64661f1b-b05b-481b-87a5-108a2a8bc271-2391178.jpg%22%2C%22ow%22%3A1066%2C%22oh%22%3A176%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/64661f1b-b05b-481b-87a5-108a2a8bc271-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对象的访问定位</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">有两中方式如图所示（HotSpot采用第二种方式）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%2226c16928c1297f0ea-2391178%22%2C%22uri%22%3A%22document_image%2Fb327a8ae-0008-4527-b014-e923a00bd276-2391178.jpg%22%2C%22ow%22%3A729%2C%22oh%22%3A363%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">好处：实例区域的对象被移动时reference指针不需要改变，只改变句柄池里的内容</span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/b327a8ae-0008-4527-b014-e923a00bd276-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%221da16928c189ad118-2391178%22%2C%22uri%22%3A%22document_image%2F02b827d8-0979-45ed-ae3a-18051b5f0105-2391178.jpg%22%2C%22ow%22%3A765%2C%22oh%22%3A373%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">速度更快</span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/02b827d8-0979-45ed-ae3a-18051b5f0105-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">垃圾回收器</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">回收位置：Java堆和方法区</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">对象生死？（如何标记对象）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">计数引用法</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">问题：难以解决对象循环引用问题</span></li></ul></li><li style="line-height: 28px;"><span class="content mubu-node" color="#dc2d1e" heading="2" style="color: rgb(220, 45, 30); line-height: 28px; min-height: 28px; font-size: 21px; display: inline-block; vertical-align: top;">可达性分析算法</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">GC roots</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">本地变量表的reference</span></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">方法区静态属性引用的对象</span></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">方法区中常量引用的对象</span></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"><span class="italic" style="font-style: italic;">本地方法栈中Native方法所引用的对象</span></span></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">实际情况：可达性分析+引用辅助类</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">强引用（普通引用）</span></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">软引用（SoftReference）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在内存溢出之前会把其列入回收范围。</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">弱引用</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">被弱引用关联的对象只能生存到下一次垃圾收集发生之前</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">虚引用</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" color="#333333" style="color: rgb(51, 51, 51); line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">为一个对象设置虚引用关联的唯一目的就是能在这个对象被收集器回收时收到一个系统通知。</span></li></ul></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">生存还是死亡</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">方法区回收(方法区如何标记)</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">回收废弃常量</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">此常量已经“实在”没有用了</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">无用的类</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">同时满足以下三点为无用的类</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">堆中不存在任何任何这个类的实例了</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">加载该类的Classloader已经被回收</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">该类的Class对象没有在任何地方被引用（防止反射使用）</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">在大量使用反射、动态代理、CGLib 等ByteCode 框架、动态生成JSP 以及OSGi 这类频繁自定义ClassLoader 的场景都需要虚拟机具备类卸载的功能，以保证永生代不会溢出。</span></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">垃圾-收集算法</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">标记清除算法 Mark-Sweep</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%22a01692963eadf064-2391178%22%2C%22uri%22%3A%22document_image%2F00d3f18a-e32b-4424-98bd-d4063846898a-2391178.jpg%22%2C%22ow%22%3A621%2C%22oh%22%3A332%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">缺点：碎片太多</span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/00d3f18a-e32b-4424-98bd-d4063846898a-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">复制算法(copying)</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">首先将内存分为大小相等的两部分（假设A、B两部分），每次呢只使用其中的一部分（这里我们假设为A区），等这部分用完了，这时候就将这里面还能活下来的对象复制到另一部分内存（这里设为B区）中，然后把A区中的剩下部分全部清理掉。这样一来每次清理都要对一半的内存进行回收操作，这样内存碎片的问题就解决了。</span></li><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%2217e1692968653817e-2391178%22%2C%22uri%22%3A%22document_image%2Fc25a98cb-db1c-493d-8c30-042c09fc2174-2391178.jpg%22%2C%22ow%22%3A603%2C%22oh%22%3A364%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">HotSpot实现的原型</span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/c25a98cb-db1c-493d-8c30-042c09fc2174-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">标记整理（mark compact）</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" images="%5B%7B%22id%22%3A%221841692969246415e-2391178%22%2C%22uri%22%3A%22document_image%2F2b323958-3753-4bd1-a081-0e5178d68f82-2391178.jpg%22%2C%22ow%22%3A606%2C%22oh%22%3A372%7D%5D" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span><div style="padding: 3px 0"><img src="https://img.mubu.com/document_image/2b323958-3753-4bd1-a081-0e5178d68f82-2391178.jpg" style="max-width: 720px;" class="attach-img"></div></li></ul></li><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">分代收集算法</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">将对象根据存活周期分为几块，在不同的代使用不同的算法。</span></li></ul></li></ul></li><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">HotSpot如何何时发起GC</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">枚举根节点</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">问题：枚举全局节点和执行上下文进行标记所需时间太长，并且会导致STW&nbsp;。</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">使用准确形式的GC，不需要一个不漏的检查所有上下文和全局的引用位置。虚拟机通过维护某些数据结构（例如：Java中是使用OopMap，在类加载完成的时候， HotSpot 就把对象内什么偏移量上是什么类型的数据计算出来，在JIT 编译过程中，也会在特定的位置记录下楼和寄存器中哪些位置是引用。这样， GC 在扫描时就可以直接得知这些信息了。</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">问题：如果为每一条指令都生成对应的OopMap ，那将会需要大量的额外空间，这样GC 的空间成本将会变得很高。</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li class="collapsed" style="line-height: 22px;"><span class="content mubu-node collapsed" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">安全点</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">即程序执行时并非在所有地方都能停顿下来开始GC ，只有在到达安全点时才能暂停</span></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">如何保证各个线程都达到安全点并开始GC</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">主动式中断</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">设置flag在每个安全点轮询一下。</span></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"><span class="italic" style="font-style: italic;">强先式中断（没有实际使用过）</span></span></li></ul></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">问题：如果有进程处于Sleep状态或者Blocked状态，不能达到安全点，从而不知道此时有什么对象引用。</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">安全区域</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">安全区域是指在一段代码片段之中，引用关系不会发生变化。在这个区域中的任意地方开始GC 都是安全的。在线程执行到Safe Region 中的代码时， 首先标识自己巳经进入了Safe Re部on, 那样， 当在这段时间里NM要发起GC 时， 就不用管标识自已为Safe Region 状态的线程了。在线程要离开Safe Region 时， 它要检查系统是否已经完成了根节点枚举（或者是整个GC 过程）， 如果完成了， 那线程就继续执行， 否则它就必须等待直到收到可以安全离开Safe Region 的信号为止。</span></li></ul></li></ul></li></ul></li></ul></li></ul></li><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;">垃圾收集器3.5</span><ul class="children" style="list-style: disc outside; padding-bottom: 4px;"><li style="line-height: 22px;"><span class="content mubu-node" style="line-height: 22px; min-height: 22px; font-size: 14px; display: inline-block; vertical-align: top;"></span></li></ul></li></ul></li></ul></div>

</body>
</html>