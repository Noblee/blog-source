---
title: Java刷题错题以及收集的Java零碎知识。
tags:
  - 语言
  - 基础
  - Java
  - 笔记
originContent: >-
  # 错题

  1. 关于以下application,说法正确是什么？


  ```java

  public class Test {
      static int x=10;
      static {x+=5;}
      public static void main(String[] args) //4
          {
          System.out.println("x="+x);
      }
      static{x/=3;};
  }//9

  ```


  > 答案：编译通过，执行结果是：x=5


  解析：

  ```java

  class A{
      static {
          System.out.println("父类静态代码块");
      }
      public A(){
          System.out.println("父类构造方法");
      }
      {
          System.out.println("父类初始化块");
      }
  }

  public class B extends A{
      static{
          System.out.println("子类静态代码块");
      }
      public B(){
          System.out.println("子类构造方法");
      }
      {
          System.out.println("子类初始化块");
      }
      public static void main(String[] args){
          new B();
      }
  }

  ```

  父类静态代码块-->子类静态代码块-->父类普通代码块-->父类构造方法-->子类代码块-->子类构造方法；

  <!-- more -->

  2.下面代码的输出是什么？

  ```java

  public class Base

  {
      private String baseName = "base";
      public Base()
      {
          callName();
      }
   
      public void callName()
      {
          System. out. println(baseName);
      }
   
      static class Sub extends Base
      {
          private String baseName = "sub";
          public void callName()
          {
              System. out. println (baseName) ;
          }
      }
      public static void main(String[] args)
      {
          Base b = new Sub();
      }
  } 

  ```

  答案

  > null


  解析：

  >new Sub();在创造派生类的过程中首先创建基类对象，然后才能创建派生类。

  创建基类即默认调用Base()方法，在方法中调用callName()方法，由于派生类中存在此方法，则被调用的callName（）方法是派生类中的方法，此时派生类还未构造，所以变量baseName的值为null.


  3. Java语言中，如果"xyz"没有被创建过，String s = new String(“xyz”);创建了几个string对象？


  > 答案：2个


  > 解析:

  **相关知识点**：

  类加载对一个类只会进行一次。

  "xyz" 在类加载时就已经创建并驻留了（如果该类被加载之前已经有 "xyz" 字符串被驻留过则不需要重复创建用于驻留的"xyz"实例>）。


  > 驻留的字符串是放在全局共享的字符串常量池中的。


  > 在 HotSpot VM 里实现的 string pool 功能的是一个 StringTable
  类，它是一个哈希表，里面存的是驻留字符串(也就是我们常说的用双引号括起来的)的引用（而不是驻留字符串实例本身）

  也就是说在堆中的某些字符串实例被这个 StringTable 引用之后就等同被赋予了”驻留字符串”的身份。

  这个 StringTable 在每个 HotSpot VM 的实例只有一份，被所有的类共享。


  > 在这段代码后续被运行的时候，"xyz" 字面量对应的 String 实例已经固定了(前面的类加载过程)，不会再被重复创建。


  > 所以这段代码将常量池中的对象复制一份放到 heap 中，并且把 heap 中的这个对象的引用交给 s1 持有。


  > **简单理解**：

  对于这句代码，可分为两个过程：

  jvm 首先在字符串常量池内里面看看找不找到字符串"xyz"；找到，进入第二步；否则，创建新的 String 对象，并“放到”字符串常量池里面。

  然后由于遇到了 new，还会在堆创建 String 对象，其实是拷贝的常量池的那个，拷贝比创建大概快吧...最后将其返回给 s1。

  将 new String("xyz") 拆分为 new String() 和 "xyz"

  如果写在类方法里，请参考前面的类加载，就是相比之下提前驻留了吧。

  4. 下面哪段程序能够正确的实现了GBK编码字节流到UTF-8编码字节流的转换： 

  byte[] src,dst;

  > 答案：

  dst=new String (src,”GBK”).getbytes(“UTF-8”)


  5. 在使用super和this关键字时，以下描述正确的是（）

  > 答案

  在子类构造方法中使用super（）显示调用父类的构造方法，super（）必须写在子类构造方法的第一行，否则编译不通过


  > 解析

  使用super()或者this()方法是必须放在构造函数的第一行

  由于this(%)代表的构造函数默认有super()方法，所以规定this()和super()不能同时出现在一个构造函数中。

  因为static方法或者语句块没有实例时可以使用，而此时不需要构造实例，所以不能用this()和super().


  6. 关于 访问权限说法正确 的是 ？ ()

  > 答案:

  内部类前面可以修饰public,protected和private


  > 解析

  对于外部类来说，只有两种修饰，public和默认（default），因为外部类放在包中，只有两种可能，包可见和包不可见。

  对于内部类来说，可以有所有的修饰，因为内部类放在外部类中，与成员变量的地位一致，所以有四种可能。


  7. 以下代码的输出结果是？

  ```java

  public class B

  {
      public static B t1 = new B();
      public static B t2 = new B();
      {
          System.out.println("构造块");
      }
      static
      {
          System.out.println("静态块");
      }
      public static void main(String[] args)
      {
          B t = new B();
      }
  }

  ```

  > 答案：

  构造块 构造块 静态块 构造块


  > 解析：

  并不是静态块最先初始化,而是静态域.

  而静态域中包含静态变量、静态块和静态方法,其中需要初始化的是静态变量和静态块.而他们两个的初始化顺序是靠他们俩的位置决定的!


  8.class A {}

  class B extends A {}

  class C extends A {}

  class D extends B {}

  Which four statements are true ?


  > 答案：


  The type List<A> is assignable to List.

  The type List<Object> is assignable to List\<?\>.

  The type List<D> is assignable to List<?extends B>.

  The type List<?extends B> is assignable to List<?extends A>.


  > 解析

  ```

  1. 只看尖括号里边的！！明确点和范围两个概念

  2. 如果尖括号里的是一个类，那么尖括号里的就是一个点，比如List\<A\>,List<B>,List<Object>

  3. 如果尖括号里面带有问号，那么代表一个范围，<? extends A> 代表小于等于A的范围，<? super
  A>代表大于等于A的范围，<?>代表全部范围

  4. 尖括号里的所有点之间互相赋值都是错，除非是俩相同的点

  5. 尖括号小范围赋值给大范围，对，大范围赋值给小范围，错。如果某点包含在某个范围里，那么可以赋值，否则，不能赋值

  6. List<?>和List 是相等的，都代表最大范围

  7.List既是点也是范围，当表示范围时，表示最大范围

  ```


  ---

  # 零碎知识

  1. 接口中的变量默认是public static final 的，方法默认是public abstract 的。

  2. 2.
  在hashmap中，key值是不可能重复的，由hashCode和equals方法共同判断key值是否相等。即使两个对象的hashCode相同相等，也不能说他们的key值相等。

  3. // 数据类型[][] 数组名;

  int [][] table = new int[2][2];

  int [][] table = new int[2][];

  int [] table [] = new int[2][2];

  int [] table [] = new int[2][];

  都是正确的 new int[2][];若未确定每行的长度 打印出来为空。

  4. 

  ![image.png](http://uploadfiles.nowcoder.com/images/20151010/214250_1444467985224_6A144C1382BBEF1BE30E9B91BC2973C8)

  > 1. 粉红色的是受检查的异常(checked exceptions),其必须被
  try{}catch语句块所捕获,或者在方法签名里通过throws子句声明.受检查的异常必须在编译时被捕捉处理,命名为 Checked Exception
  是因为Java编译器要进行检查,Java虚拟机也要进行检查,以确保这个规则得到遵守.

  > 2. 绿色的异常是运行时异常(runtime exceptions),需要程序员自己分析代码决定是否捕获和处理,比如 空指针,被0除...

  > 3.
  而声明为Error的，则属于严重错误，如系统崩溃、虚拟机错误、动态链接失败等，这些错误无法恢复或者不可能捕捉，将导致应用程序中断，Error不需要捕捉。


  5. final只是指向不变，但是指向的值有可能变，所以依然不是线程安全

  6.
  局部变量是指类&成员方法中的变量，必须初始化。局部变量运行时被分配在栈中，量大，生命周期短，如果虚拟机给每个局部变量都初始化一下，是一笔很大的开销，但变量不初始化为默认值就使用是不安全的。出于速度和安全性两个方面的综合考虑，解决方案就是虚拟机不初始化，但要求编写者一定要在使用前给变量赋值。
categories:
  - Java
toc: true
date: 2019-01-22 21:49:57
---

# 错题
1. 关于以下application,说法正确是什么？

```java
public class Test {
    static int x=10;
    static {x+=5;}
    public static void main(String[] args) //4
        {
        System.out.println("x="+x);
    }
    static{x/=3;};
}//9
```

> 答案：编译通过，执行结果是：x=5

解析：
```java
class A{
    static {
        System.out.println("父类静态代码块");
    }
    public A(){
        System.out.println("父类构造方法");
    }
    {
        System.out.println("父类初始化块");
    }
}
public class B extends A{
    static{
        System.out.println("子类静态代码块");
    }
    public B(){
        System.out.println("子类构造方法");
    }
    {
        System.out.println("子类初始化块");
    }
    public static void main(String[] args){
        new B();
    }
}
```
父类静态代码块-->子类静态代码块-->父类普通代码块-->父类构造方法-->子类代码块-->子类构造方法；
<!-- more -->
2.下面代码的输出是什么？
```java
public class Base
{
    private String baseName = "base";
    public Base()
    {
        callName();
    }
 
    public void callName()
    {
        System. out. println(baseName);
    }
 
    static class Sub extends Base
    {
        private String baseName = "sub";
        public void callName()
        {
            System. out. println (baseName) ;
        }
    }
    public static void main(String[] args)
    {
        Base b = new Sub();
    }
} 
```
答案
> null

解析：
>new Sub();在创造派生类的过程中首先创建基类对象，然后才能创建派生类。
创建基类即默认调用Base()方法，在方法中调用callName()方法，由于派生类中存在此方法，则被调用的callName（）方法是派生类中的方法，此时派生类还未构造，所以变量baseName的值为null.

3. Java语言中，如果"xyz"没有被创建过，String s = new String(“xyz”);创建了几个string对象？

> 答案：2个

> 解析:
**相关知识点**：
类加载对一个类只会进行一次。
"xyz" 在类加载时就已经创建并驻留了（如果该类被加载之前已经有 "xyz" 字符串被驻留过则不需要重复创建用于驻留的"xyz"实例>）。

> 驻留的字符串是放在全局共享的字符串常量池中的。

> 在 HotSpot VM 里实现的 string pool 功能的是一个 StringTable 类，它是一个哈希表，里面存的是驻留字符串(也就是我们常说的用双引号括起来的)的引用（而不是驻留字符串实例本身）
也就是说在堆中的某些字符串实例被这个 StringTable 引用之后就等同被赋予了”驻留字符串”的身份。
这个 StringTable 在每个 HotSpot VM 的实例只有一份，被所有的类共享。

> 在这段代码后续被运行的时候，"xyz" 字面量对应的 String 实例已经固定了(前面的类加载过程)，不会再被重复创建。

> 所以这段代码将常量池中的对象复制一份放到 heap 中，并且把 heap 中的这个对象的引用交给 s1 持有。

> **简单理解**：
对于这句代码，可分为两个过程：
jvm 首先在字符串常量池内里面看看找不找到字符串"xyz"；找到，进入第二步；否则，创建新的 String 对象，并“放到”字符串常量池里面。
然后由于遇到了 new，还会在堆创建 String 对象，其实是拷贝的常量池的那个，拷贝比创建大概快吧...最后将其返回给 s1。
将 new String("xyz") 拆分为 new String() 和 "xyz"
如果写在类方法里，请参考前面的类加载，就是相比之下提前驻留了吧。
4. 下面哪段程序能够正确的实现了GBK编码字节流到UTF-8编码字节流的转换： 
byte[] src,dst;
> 答案：
dst=new String (src,”GBK”).getbytes(“UTF-8”)

5. 在使用super和this关键字时，以下描述正确的是（）
> 答案
在子类构造方法中使用super（）显示调用父类的构造方法，super（）必须写在子类构造方法的第一行，否则编译不通过

> 解析
使用super()或者this()方法是必须放在构造函数的第一行
由于this(%)代表的构造函数默认有super()方法，所以规定this()和super()不能同时出现在一个构造函数中。
因为static方法或者语句块没有实例时可以使用，而此时不需要构造实例，所以不能用this()和super().

6. 关于 访问权限说法正确 的是 ？ ()
> 答案:
内部类前面可以修饰public,protected和private

> 解析
对于外部类来说，只有两种修饰，public和默认（default），因为外部类放在包中，只有两种可能，包可见和包不可见。
对于内部类来说，可以有所有的修饰，因为内部类放在外部类中，与成员变量的地位一致，所以有四种可能。

7. 以下代码的输出结果是？
```java
public class B
{
    public static B t1 = new B();
    public static B t2 = new B();
    {
        System.out.println("构造块");
    }
    static
    {
        System.out.println("静态块");
    }
    public static void main(String[] args)
    {
        B t = new B();
    }
}
```
> 答案：
构造块 构造块 静态块 构造块

> 解析：
并不是静态块最先初始化,而是静态域.
而静态域中包含静态变量、静态块和静态方法,其中需要初始化的是静态变量和静态块.而他们两个的初始化顺序是靠他们俩的位置决定的!

8.class A {}
class B extends A {}
class C extends A {}
class D extends B {}
Which four statements are true ?

> 答案：

The type List<A> is assignable to List.
The type List<Object> is assignable to List\<?\>.
The type List<D> is assignable to List<?extends B>.
The type List<?extends B> is assignable to List<?extends A>.

> 解析
```
1. 只看尖括号里边的！！明确点和范围两个概念
2. 如果尖括号里的是一个类，那么尖括号里的就是一个点，比如List\<A\>,List<B>,List<Object>
3. 如果尖括号里面带有问号，那么代表一个范围，<? extends A> 代表小于等于A的范围，<? super A>代表大于等于A的范围，<?>代表全部范围
4. 尖括号里的所有点之间互相赋值都是错，除非是俩相同的点
5. 尖括号小范围赋值给大范围，对，大范围赋值给小范围，错。如果某点包含在某个范围里，那么可以赋值，否则，不能赋值
6. List<?>和List 是相等的，都代表最大范围
7.List既是点也是范围，当表示范围时，表示最大范围
```
9. 在开发中使用泛型取代非泛型的数据类型（比如用ArrayList<String>取代ArrayList），程序的运行时性能会变得更好。（）
 
> 解析
泛型仅仅是java的语法糖，它不会影响java虚拟机生成的汇编代码，在编译阶段，虚拟机就会把泛型的类型擦除，还原成没有泛型的代码，顶多编译速度稍微慢一些，执行速度是完全没有什么区别的.

---
# 零碎知识
1. 接口中的变量默认是public static final 的，方法默认是public abstract 的。
2. 2. 在hashmap中，key值是不可能重复的，由hashCode和equals方法共同判断key值是否相等。即使两个对象的hashCode相同相等，也不能说他们的key值相等。
3. // 数据类型[][] 数组名;
int [][] table = new int[2][2];
int [][] table = new int[2][];
int [] table [] = new int[2][2];
int [] table [] = new int[2][];
都是正确的 new int[2][];若未确定每行的长度 打印出来为空。
4. 
![image.png](http://uploadfiles.nowcoder.com/images/20151010/214250_1444467985224_6A144C1382BBEF1BE30E9B91BC2973C8)
> 1. 粉红色的是受检查的异常(checked exceptions),其必须被 try{}catch语句块所捕获,或者在方法签名里通过throws子句声明.受检查的异常必须在编译时被捕捉处理,命名为 Checked Exception 是因为Java编译器要进行检查,Java虚拟机也要进行检查,以确保这个规则得到遵守.
> 2. 绿色的异常是运行时异常(runtime exceptions),需要程序员自己分析代码决定是否捕获和处理,比如 空指针,被0除...
> 3. 而声明为Error的，则属于严重错误，如系统崩溃、虚拟机错误、动态链接失败等，这些错误无法恢复或者不可能捕捉，将导致应用程序中断，Error不需要捕捉。

5. final只是指向不变，但是指向的值有可能变，所以依然不是线程安全
6. 局部变量是指类&成员方法中的变量，必须初始化。局部变量运行时被分配在栈中，量大，生命周期短，如果虚拟机给每个局部变量都初始化一下，是一笔很大的开销，但变量不初始化为默认值就使用是不安全的。出于速度和安全性两个方面的综合考虑，解决方案就是虚拟机不初始化，但要求编写者一定要在使用前给变量赋值。
7. java三大注解

**Override 注解**
指明被注解的方法需要覆写超类中的方法.
如果某个方法使用了该注解,却没有覆写超类中的方法(比如大小写写错了,或者参数错了,或者是子类自己定义的方法),编译器就会生成一个错误.

**Deprecated 注解**
可以修饰类、方法、变量，在java源码中被@Deprecated修饰的类、方法、变量等表示不建议使用的，可能会出现错误的，可能以后会被删除的类、方法等，如果现在使用，则在以后使用了这些类、方法的程序在更新新的JDK、jar包等就会出错，不再提供支持。     个人程序中的类、方法、变量用@Deprecated修饰同样是不希望自己和别人在以后的时间再次使用此类、方法。  当编译器编译时遇到了使用@Deprecated修饰的类、方法、变量时会提示相应的警告信息。

**Suppresswarnings 注解**
可以达到抑制编译器编译时产生警告的目的，但是很不建议使用@SuppressWarnings注解，使用此注解，编码人员看不到编译时编译器提示的相应的警告，不能选择更好、更新的类、方法或者不能编写更规范的编码。同时后期更新JDK、jar包等源码时，使用@SuppressWarnings注解的代码可能受新的JDK、jar包代码的支持，出现错误，仍然需要修改。

8. 两同两小一大原则
方法名相同，参数类型相同
子类返回类型小于等于父类方法返回类型， 
子类抛出异常小于等于父类方法抛出异常， 
子类访问权限大于等于父类方法访问权限。





