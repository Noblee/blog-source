---
title: Java核心技术学习笔记
tags:
  - 语言
  - 基础
  - Java
  - 笔记
originContent: >-
  # Java 语言学习笔记

  ## 各种名词含义

  更改器方法与访问器方法 实例域 

  方法参数(基本&引用) 静态域

  不可变类，可变类

  对象包装器

  handler 处理器

  已检查异常，和未检查异常

  实用工具方法 


  ## 零碎知识

  1. main 函数必须是public的

  2. final 定义变量 等于 const（C/C++）

  3. static final 用于一个常量在一个类中多个方法使用.（public static final 其他类类使用）

  4. strictfp关键字

  >可移植性是Java语言的设计目标之一，
  无论在哪个虚拟机上运行，同一运算应该得到同样的结果,对于浮点数的算术运算，实现这样的可移植性是相当困难。double类型使用 64
  位存储一个数值，而有些处理器使用80位浮点寄存器,这些寄存器增加了中间过程的计算精度. 但是，这个结果可能与始终在64位机器上计算的结果不一样。因此，
  Java 虚拟机的最初规范规定所有的中间计算都必须进行截断这种行为遭到了数值计算团体的反对。
  截断计算不仅可能导致溢出，而且由于截断操作需要消耗时间，所以在计算速度上实际上要比精确计算慢。
  为此，Java承认了最优性能与理想结果之间存在的冲突，并给予了改进。在默认情况下，虚拟机设计者允许对中间计算结果采用扩展的精度。但是，对于使用strictfp关键字标记的方法必须使用严格的浮点计算来生成可再生的结果。

  >* 可以把 main 方法标记为 public static strictfp void main(String[]
  args)于是，在main方法中的所有指令都将使用严格的浮点计算。

  >* 如果将一个类标记为 strictfp, 这个类中的所有方法都要使用严格的浮点计算。实际的计算方式将取决于 Intel 处理器的行为。

  >

  > 在默认情况下，中间结果允许使用扩展 的指数， 但不允许使用扩展的尾数(Intel 芯片在截断尾数时并不损失性能)。 因此，这两种
  方式的区别仅仅在于采用默认的方式不会产生溢出，而采用严格的计算有可能产生溢出。


  5. C++ 注释: 不要在 boolean
  类型与任何数值类型之间进行强制类型转换，这样可以防止发生错误。只有极少数的情况才需要将布尔类型转换为数值类型，这时可以使用条件表达式b? 1:0

  6. 不可变字符串：由于不能修改Java字符串中的字符，所以在Java文档中将String 类对象称为不可变字符串，如同数字3永远是数字3—样，字符串“
  Hello”永远包含字符H、e、1、1和o的代 码单元序列，而不能修改其中的任何一个字符。

  7. char 数据类型是一 个采用 UTF-16 编码表示 Unicode 码点的代码单元。 大多数的常用 Unicode 字符使用一个代
  码单元就可以表示， 而辅助字符需要一对代码单元表示。

  8. ![image.png](https://i.loli.net/2019/01/21/5c453af4afdf3.png)

  9. java的cmake？

  > javac Employee*.java

  于是， 所有与通配符匹配的源文件都将被编译成类文件。 或者键人下列命令: 

  javac EmployeeTest.java

  读者可能会感到惊讶， 使用第二种方式， 并没有显式地编译 Employeejava 然而， 当 Java 编 译器发现 EmployeeTestjava
  使用了Employee 类时会查找名为 Employee.class 的文件。 如果没有找 到这个文件， 就会自动地搜索 Employeejava, 然后，
  对它进行编译。更重要的是: 如果 Employee, java 版本较已有的 Employee.dass 文件版本新， Java
  编译器就会自动地重新编译这个文件。

  10. `janes.EmployeeCJames Bond", 250000, 1950, 1, 1) // ERROR`

  11. 所有的 Java 对象都是在堆中构造的。
   ```java
  Employee number007("]anie5 Bond", 100000, 1950, 1, 1);//此种方式是在栈中建立

  // C++, not Java
   ```
  12. 下面总结一下 Java 中方法参数的使用情况:         

  * 一个方法不能修改一个基本数据类型的参数 (即数值型或布尔型)。 

  * 一个方法可以改变一个对象参数的状态。 

  * 一个方法不能让对象参数引用一个新的对象

  13. 如果类中提供了至少一个构造器，但是没有提供无参数的构造器， 则在构造对象时如果 没有提供参数就会被视为不合法。

  14. 初始值不一定是常量值。
   ```java
   class Employee{
      private static int nextld;
      private int id = assignldO;
      private static int assignld{ 
      int r = nextld; nextld++;
      return r;
      }
  }

  ```


  15. java内存结构

  [![](https://i.loli.net/2019/01/02/5c2b9bf995574.png)](https://i.loli.net/2019/01/02/5c2b9bf995574.png)

  16. 对象初始化块（要在实例域后定义）和静态初始化块

  ```java
      (static) class Some{
        private int a;
          {
              a++;
          }
      }
  ```


  17. import 语句不仅可以导入类，还增加了导人`静态方法`和`静态域`的功能。

  18. 标记为 public 的部分可以被任意的类使
  用;标记为private的部分只能被定义它们的类使用。如果没有指定public或private,这个部分(类、方法或变量)可以被同一个包中的所有方法访问。

  19. 类文件存储在文件系统的子目录中。类的路径必须与包名匹配。

  20. 为了使类能够被多个程序共享， 需要做到下面几点:

  > * 把类放到一个目录中 例如 /home/user/classdir 需要注意
  这个目录是包树状结构的基目录。如果希望将com.horstmann.corejava.Employee 类添加到其中， 这个 Employee.class
  类文件就必须位于子目录 /home/user/classdir/com/horstmann/corejava中。

  > * 将 JAR 文件放在一个目录中， 例如:/home/user/archives。

  > * 设置类路径(classpath)。类路径是所有包含类文件的路径的集合。

  * 在 UNIX 环境中， 类路径中的不同项目之间采用冒号 (一) 分隔:
   /home/user/classdir:.: /home/user/archives/archive .jar
  * 在 Windows 环境中， 则以分号(;)分隔:

  c:\classdir;.;c:\archives\ archive.jar


  21. 假定虚拟机要搜寻com.horstmann.corejava.Employee
  类文件。它首先要查看存储在jre/lib和jre/lib/ext目录下的归档文件中所存放的系统类文件。显然,在那里找不到相应的类文件,然后再查看类路径。然后查找以下文件:

  * /home/user/classdir/com/horstmann/corejava/Employee.class

  *  ./com/horstmann/corejava/Employee.class 

  *  com/horstmann/corejava/Employee.class inside
  /home/user/archives/archive.jar


  编译器定位文件要比虚拟机复杂得多。如果引用了一个类，而没有指出这个类所在的包，那么编译器将首先查找包含这个类的包，并询查所有的 import
  指令，确定其中是否包含了被引用的类。 例如， 假定源文件包含指令:

  `import java.util.*;`

  `import com.horstmann.corejava.*;`

  并且源代码引用了 Employee 类。 编译器将试图查找 java.lang.Employee ( 因为 java.lang 包被 默认导入 )、
  java.util.Employee、 com.horstmann.corejava.Employee 和当前包中的 Employee。

  22.
  为什么优先使用不可变类：更改对象的问题在于，如果多个线程试图同时更新一个对象，就会发生并发更改。其结果是不可预料的。如果类是不可变的，就可以安全地在多个线程间共享其对象。

  23. 关键字this有两个用途：一是引用隐式参数，二是调用该类其他的构造器，同样，super关键字也有两个用途:一是调用超类的方法，
  二是调用超类的构造器。

  24.   JAVA多态的问题

  ![image.png](https://i.loli.net/2019/01/21/5c453b3d75180.png)

  25. 方法的名字和参数列表称为方法的签名

  26. 下面归纳一下Java 用于控制可见性的4个访问修饰符


  * 仅对本类可见————private。

  * 对所有类可见————public。

  * 对本包和所有子类可见————protected

  * 对本包可见————默认（很遗憾)，不需要修饰符.


  .

  27. 为了防备name或hireDay可能为null的情况，需要使用Objects.equals 方法。

  28. 关于equals方法

  > 1.
  （默认方法）Object的equals方法检测两个类是否具有相同的引用。(但我们的需求经常是连个类的状态（域）相等即为相等，但这也不绝对，所以对于一个对象怎样算相等应当具体问题具体分析)

  > 2. 两给类的状态相等即为相等这一情况又一般分为两种情况：

  > *
  例如AbstractSet.equals中的equals被定义为final（实际并不是，但后续覆盖的话基本思想不变只是使算法更高效），这是由于TreeSet和HashSet的实例也应当可以相等，只要他们包含的元素一样。一般来讲（上面特例），此时对于该类的所有子类都不允许重载。(对所有的AbstractSet子类都有同样的“语义”)

  > * 严格控制只有实例的class相同才可能相等。

  > 3. 下面给出编写一个完美的equals 方法的建议：

  1 ) 显式参数命名为otherObject, 稍后需要将它转换成另一个叫做other 的变量。

  2 ) 检测this与otherObject 是否引用同一个对象：

  `if (this = otherObject) return true;`

  3 ) 检测otherObject 是否为null .

  `if (otherObject = null ) return false;`

  4 ) 比较this 与otherObject 是否属于同一个类。如果equals 的语义在每个子类中有所改变，就使用getClass 检测：

  `if (getClass() != otherObject.getCIass()) return false;`

  如果所有的子类都拥有统一的语义，就使用instanceof 检测：

  `if (!(otherObject instanceof ClassName)) return false;`

  5 ) 将otherObject 转换为相应的类类型变量：

  `ClassName other = (ClassName) otherObject`

  6 ) 现在开始对所有需要比较的域进行比较了。使用== 比较基本类型域，使用equals比

  较对象域。如果所有的域都匹配，就返回true; 否则返回false。

  `return fieldl == other.field&& Objects.equa1s(fie1d2,`

  `other.field2)`

  **如果在子类中重新定义equals**,就要在其中包含调用super.equals(other)  


  29. 对于数组类型的域，可以使用静态的Arrays.equals方法检测相应的数组元素是否相等。


  30.hashcodeAPI

  `int type.hashcode(type instance);`

  `Objects.hash(name, salary, hireDay) ;`

  `static int java.util.Arrays.hashCode(type[] a)`

  31.Equals 与hashCode 的定义必须一致：如果x.equals(y) 返回true,
  那么x.hashCode()就必须与y.hashCode()具有相同的值。例如，如果用定义的Employee.equals比较雇员的ID，那么hashCode
  方法就需要散列ID，而不是雇员的姓名或存储地址。

  32. 这就是Java 中不尽如人意的参数化类型的限制所带来的结果。鉴于兼容性的考虑，编译器在对类型转换进行检査之后，
  如果没有发现违反规则的现象，就将所有的类型化数组列表转换成原始ArrayList对象。在程序运行时，
  所有的数组列表都是一样的，即没有虚拟机中的类型参数。因此，类型转换（ArrayList ) 和( ArrayList<Employee> )
  将执行相同的运行时检查。

  33. 下面这个调用

  `list.add(3);`

  将自动地变换成

  `list.add(Integer.value0f(3)) ;`

  这种变换被称为**自动装箱（autoboxing)**。

  int n = list.get(i);

  翻译成

  int n = list.get(i).intValue();

  这种变换被称为**自动拆箱（autoboxing)**.

  在算术表达式中也能够自动地装箱和拆箱：

  `Integer n = 3;`

  `n++;`

  自动拆装箱是编译器操作而不是虚拟机操作，编译器在编译时添加适当方法

  34. 注意区分不可变对象和可变对象。

  35. 可以将已经存在且**最后一个**参数是数组的方法重新定义为可变参数的方法，而不会破坏任何已经存在的代码,Object… 参数类型与Object[]
  完全一样, 当然基本类型也是可以，如下面的例子。

  ```java

  public static double max(double... values)

  {
      double largest = Double.NECATIVEJNFINITY;
      for (double v : values) if (v > largest) largest = v;
      return largest;
  }

  ```

  36. 枚举：`public enuni Size { SMALL, MEDIUM, LARGE, EXTRAJARGE };`

  实际上，这个声明定义的类型是一个类， 它刚好有4 个实例， 在此尽量不要构造新对象。

  因此， 在比较两个枚举类型的值时， 永远不需要调用equals, 而直接使用“ = =” 就

  可以了。

  37. 枚举的复杂用法：

  ```java

  public enum Size

  {
      SMALL("S"), MEDIUM("M") , LARGE("L") , EXTRA_LARGE("XL");//只有四个对象
      private String abbreviation;
      private Size(String abbreviation) { this,abbreviation = abbreviation; }
      public String getAbbreviation() { return abbreviation; }
  }

  ```


  `Size s = Enum.valueOf(Size.class, "SMALL");`

  `Size[] Size.values()`

  38. 反射

  > `Class cl = Cl ass.forName(className) ;`

  鉴于历史原getName 方法在应用于数组类型的时候会返回一个很奇怪的名字：

  • Double[] class.getName() 返回“ [Ljava.lang.Double; ’’

  • int[].class.getName()返回“ [I ” ，

  虚拟机为每个类型管理一个Class对象。因此， 可以利用=运算符实现两个类对象比较的操作

  > Class
  类的getDeclareFields、getDeclareMethods和getDeclaredConstructors方法将分别返回类中声明的全部域、方法和构造器，
  其中包括私有和受保护成员，但不包括超类的成员。



  39. Java 数组会记住每个元素的类型， 即创建数组时new 表达式中使用的元素类型。将一个Employee[ ]临时地转换成Object[ ] 数组，
  然后再把它转换回来是可以的，但一从开始就是Objectt ] 的数组却永远不能转换成Employe [] 数组。

  下面是java.util.Arrays.copyof的实现。

  ```java

  public static Object badCopyOf(Object[] a, int newLength) // not useful

  {
      ObjectD newArray = new Object[newlength]:
      System.arraycopy(a, 0, newArray, 0, Math.min(a.length, newLength)) ;
      //注意这个方法
      return newArray;
  }

  public static Object goodCopyOf(Object a, int newLength)

  {
      Class cl = a.getClass()；
      if (！cl.isArray()) return null ;
      Class componentType = cl.getComponentType()；//注意
      int length = Array.getLength(a);
      Object newArray = Array.newlnstance(componentType, newLength) ://注意 java.lang.Array
      System.arraycopy(a, 0, newArray, 0, Math.min(length, newLength)) ;
      return newArray;
  }

  ```

  40. 调用任意方法

  `Object invoke(Object obj, Object... args)` 如果是静态方法obj填null

  41. 虽然在接口中不能包含实例域或**静态方法(java8之前)**，但却可以包含常量.

  42. 目前为止， 通常的做法都是将静态方法放在伴随类中。在标准库中， 你会看到成对出现

  的接口和实用工具类， 如Collection/Collections 或Path/Paths。面来看Paths 类，
  其中只包含两个工厂方法。可以由一个字符串序列构造一个文件或目录的路径， 如Paths.get("jdk1.8.0", "jre", "bin")。在Java
  SE 8中， 可以为Path 接口增加以下方法：

  ```java

  public interface Path{
      public static Path get(String first, String... more) {
      return Fi1eSystems.getDefault().getPath(first, more);
      }
  }

  ```

  这样一来， Paths 类就不再是必要的了。

  43. default关键字：用于接口中方法的声明，意为接口中的实现为默认实现，如果实现接口的类不覆盖则使用这个实现。

  44. 默认方法的一个重要用法是“接口演化” （interface evolution)。

  45.
  我们只讨论了两个接口的命名冲突。现在来考虑另一种情况，一个类扩展了一个超类，同时实现了一个接口，并从超类和接口继承了相同的方法。例如，假设Person
  是一个类，Student 定义为：class Student extends Person implements Named { . . .
  }在这种情况下， 只会考虑超类方法， 接口的所有默认方法都会被忽略。在我们的例子中，
  Student从Person继承了getName方法，Named接口是否为getName提供了默认实现并不会带来什么区别。这正是“ 类优先” 规则。

  46. 尽管LengthComparator对象没有状态，不过还是需要建立这个对象的一个实例。我们需要这个实例来调用compare方法，它不是一个静态方法。

  47.
  通常子对象都是可变的，必须重新定义clone方法来建立一个深拷贝，同时克隆所有子对象。在这个例子中，hireDay域是一个Date,这是可变的，所以它也需要克隆。（出于这个原因，这个例子使用Date类型的域而不是LocalDate来展示克隆过程。如果hireDay是不可变的LocalDate类的一个实例，就无需我们做任何处理了。）

  ![image.png](https://i.loli.net/2019/01/21/5c453bea3e69d.png)

  48. Cloneable 接口是Java提供的一组标记接口(tagging interface) 之一

  标记接口不包含任何方法；它唯一的作用就是允许在类型查询中使用instanceof。即使clone的默认（浅拷贝）实现能够满足要求（实例域全部是不可变时），还是需要实现Cloneable接口，将clone重新定义为public，
  再调用super.clone()。

  49. 如果在一个对象上调用clone,但这个对象的类并没有实现Cloneable接口，Object
  类的clone方法就会拋出一个CloneNotSupportedException当然，Employee和Date类实现了Cloneable
  接口，所以不会抛出这个异常。不过，编译器并不了解这一点，因此，我们声明了这个异常。

  50. 所有数组类型都有一个public的clone 方法，而不是protected,可以用这个方法

  建立一个新数组，包含原数组所有元素的副本。

  51. 对于只有一个抽象方法的接口， 需要这种接口的对象时，就可以提供一个lambda 表达式。这种接口称为函数式接口（ functional
  interface )。

  52. 甚至不能把lambda表达式赋给类型为Object的变量，Object不是一个函数式接口。

  53. 

  ```java

  java.util.function 包中有一个尤其有用的接口Predicate:

  public interface Predicate<T>

  {
      boolean test(T t);
      // Additional default and static methods
  }

  ArrayList 类有一个removelf 方法， 它的参数就是一个Predicate。这个接口专门用来传递

  lambda 表达式。例如，下面的语句将从一个数组列表删除所有null值：

  list.removelf(e -> e == null);

  ```

  54. 方法引用：一种lambda表达式简化方式，根据lamdba表达式所在的函数式接口的位置，确定

  >从这些例子可以看出， 要用::操作符分隔方法名与对象或类名。主要有3 种情况：

  * object::instanceMethod

  * Class::staticMethod

  * Class::instanceMethod

  在前2 种情况中， 方法引用等价于提供方法参数的lambda 表达式。前面已经提到，

  System.out::println 等价于x -> System.out.println(x)。 类似地，Math::pow 等价于（x，y)
  ->Math.pow(x, y)。

  对于第3 种情况， 第1个参数会成为方法的目标。例如，String::compareToIgnoreCase 等同于(x, y) ->
  x.compareToIgnoreCase(y);

  55. lambda 表达式中捕获的变量必须实际上是**最终变量( effectivelyfinal)**。实际上的最终变量是指，
  这个变量初始化之后就不会再为它赋新值。在这里，text 总是指示同一个 String对象，所以捕获这个变量是合法的。不过，i的值会改变，因此不能捕获i。

  56. 内部类既可以访问自身的数据域，也可以访问创建它的外围类对象的数据域.为了能够运行这个程序，内部类的对象总有一个隐式引用，它指向了创建它的外部类对象。

  57. TimePrinter 类声明为私有的。这样一来，只有TalkingClock的方法才能够构造TimePrinter
  对象。只有内部类可以是私有类，而常规类只可以具有包可见性，或公有可见性。

  58. 外围类，内部类。

  59.
  使用静态内部类的原因，使用内部类只是为了把一个类隐藏在另外一个类的内部，并不需要内部类引用外围类对象。为此，可以将内部类声明为static,以便取消产生的引用。

  60. 这种功能只有在编译时无法确定需要实现哪个接口时才有必要使用，对于用程序设计人员来说，遇到这种情况的机会很少。

  61. “ 如果出现RuntimeException 异常， 那么就一定是你的问题” 是一条相当有道理的规则。

  应该通过检测数组下标是否越界来避免ArraylndexOutOfBoundsException
  异常；应该通过在使用变量之前检测是否为null来杜绝NullPointerException异常的发生：

  62.
  前面曾经提到过：如果编写一个覆盖超类的方法，而这个方法又没有抛出异常（如JComponent中的paintComponent),那么这个方法就必须捕获方法代码中出现的每一个受查异常。不许在子类的throws
  说明符中出现超过超类方法所列出的异常类范围。

  63. catch (FileNotFoundException | UnknownHostException e) { . . . }

  64. 同样，也不应该声明从RuntimeException 继承的那些非受查异常.

  ```java 

  class MyAnimation

  {
      void drawlmage(int i) throws ArraylndexOutOfBoundsException // bad style
      {
      }
  }

  ```

  65. 未被任何变量引用的日志记录器可能会被垃圾回收。为了防止这种情况发生，要像上面的例子中一样，用一个静态变量存储日志记录器的一个引用。


  ## JAVA和C++的区别


  | 什么方面 | JAVA | C++ | 备注 |

  | --- | --- | --- | --- |

  | 类中函数 | 方法 | 成员函数 | |

  | 字面数值表示 | 可以加下划线 | 不可以 | |

  | 进制表示 | 可表示二进制（0b或0B） | 不可以 | |

  | 无符号数 | 没有 | 有 | |

  | 逗号运算符 | 没有 | 有 | |

  | 更改器方法与访问器方法 | 无明显区别 | const关键字 | |

  | 方法参数 | 按值（引用也是按值） | 真引用（换个名字） | |
    [2]: https://www.nobler.xyz/wp-content/uploads/2019/01/WX20190106-145446.png
categories:
  - Java
toc: true
date: 2019-01-21 11:30:03
---

# Java 语言学习笔记
## 各种名词含义
更改器方法与访问器方法 实例域 
方法参数(基本&引用) 静态域
不可变类，可变类
对象包装器
handler 处理器
已检查异常，和未检查异常
实用工具方法 

## 零碎知识
1. main 函数必须是public的
2. final 定义变量 等于 const（C/C++）
3. static final 用于一个常量在一个类中多个方法使用.（public static final 其他类类使用）
4. strictfp关键字
>可移植性是Java语言的设计目标之一， 无论在哪个虚拟机上运行，同一运算应该得到同样的结果,对于浮点数的算术运算，实现这样的可移植性是相当困难。double类型使用 64 位存储一个数值，而有些处理器使用80位浮点寄存器,这些寄存器增加了中间过程的计算精度. 但是，这个结果可能与始终在64位机器上计算的结果不一样。因此， Java 虚拟机的最初规范规定所有的中间计算都必须进行截断这种行为遭到了数值计算团体的反对。 截断计算不仅可能导致溢出，而且由于截断操作需要消耗时间，所以在计算速度上实际上要比精确计算慢。 为此，Java承认了最优性能与理想结果之间存在的冲突，并给予了改进。在默认情况下，虚拟机设计者允许对中间计算结果采用扩展的精度。但是，对于使用strictfp关键字标记的方法必须使用严格的浮点计算来生成可再生的结果。
>* 可以把 main 方法标记为 public static strictfp void main(String[] args)于是，在main方法中的所有指令都将使用严格的浮点计算。
>* 如果将一个类标记为 strictfp, 这个类中的所有方法都要使用严格的浮点计算。实际的计算方式将取决于 Intel 处理器的行为。

> 在默认情况下，中间结果允许使用扩展 的指数， 但不允许使用扩展的尾数(Intel 芯片在截断尾数时并不损失性能)。 因此，这两种 方式的区别仅仅在于采用默认的方式不会产生溢出，而采用严格的计算有可能产生溢出。

5. C++ 注释: 不要在 boolean 类型与任何数值类型之间进行强制类型转换，这样可以防止发生错误。只有极少数的情况才需要将布尔类型转换为数值类型，这时可以使用条件表达式b? 1:0
6. 不可变字符串：由于不能修改Java字符串中的字符，所以在Java文档中将String 类对象称为不可变字符串，如同数字3永远是数字3—样，字符串“ Hello”永远包含字符H、e、1、1和o的代 码单元序列，而不能修改其中的任何一个字符。
7. char 数据类型是一 个采用 UTF-16 编码表示 Unicode 码点的代码单元。 大多数的常用 Unicode 字符使用一个代 码单元就可以表示， 而辅助字符需要一对代码单元表示。
8. ![image.png](https://i.loli.net/2019/01/21/5c453af4afdf3.png)
9. java的cmake？
> javac Employee*.java
于是， 所有与通配符匹配的源文件都将被编译成类文件。 或者键人下列命令: 
javac EmployeeTest.java
读者可能会感到惊讶， 使用第二种方式， 并没有显式地编译 Employeejava 然而， 当 Java 编 译器发现 EmployeeTestjava 使用了Employee 类时会查找名为 Employee.class 的文件。 如果没有找 到这个文件， 就会自动地搜索 Employeejava, 然后， 对它进行编译。更重要的是: 如果 Employee, java 版本较已有的 Employee.dass 文件版本新， Java 编译器就会自动地重新编译这个文件。
10. `janes.EmployeeCJames Bond", 250000, 1950, 1, 1) // ERROR`
11. 所有的 Java 对象都是在堆中构造的。
 ```java
Employee number007("]anie5 Bond", 100000, 1950, 1, 1);//此种方式是在栈中建立
// C++, not Java
 ```
12. 下面总结一下 Java 中方法参数的使用情况:         
* 一个方法不能修改一个基本数据类型的参数 (即数值型或布尔型)。 
* 一个方法可以改变一个对象参数的状态。 
* 一个方法不能让对象参数引用一个新的对象
13. 如果类中提供了至少一个构造器，但是没有提供无参数的构造器， 则在构造对象时如果 没有提供参数就会被视为不合法。
14. 初始值不一定是常量值。
 ```java
 class Employee{
    private static int nextld;
    private int id = assignldO;
    private static int assignld{ 
    int r = nextld; nextld++;
    return r;
    }
}
```

15. java内存结构
[![](https://i.loli.net/2019/01/02/5c2b9bf995574.png)](https://i.loli.net/2019/01/02/5c2b9bf995574.png)
16. 对象初始化块（要在实例域后定义）和静态初始化块
```java
    (static) class Some{
      private int a;
        {
            a++;
        }
    }
```

17. import 语句不仅可以导入类，还增加了导人`静态方法`和`静态域`的功能。
18. 标记为 public 的部分可以被任意的类使 用;标记为private的部分只能被定义它们的类使用。如果没有指定public或private,这个部分(类、方法或变量)可以被同一个包中的所有方法访问。
19. 类文件存储在文件系统的子目录中。类的路径必须与包名匹配。
20. 为了使类能够被多个程序共享， 需要做到下面几点:
> * 把类放到一个目录中 例如 /home/user/classdir 需要注意 这个目录是包树状结构的基目录。如果希望将com.horstmann.corejava.Employee 类添加到其中， 这个 Employee.class 类文件就必须位于子目录 /home/user/classdir/com/horstmann/corejava中。
> * 将 JAR 文件放在一个目录中， 例如:/home/user/archives。
> * 设置类路径(classpath)。类路径是所有包含类文件的路径的集合。
* 在 UNIX 环境中， 类路径中的不同项目之间采用冒号 (一) 分隔:
 /home/user/classdir:.: /home/user/archives/archive .jar
* 在 Windows 环境中， 则以分号(;)分隔:
c:\classdir;.;c:\archives\ archive.jar

21. 假定虚拟机要搜寻com.horstmann.corejava.Employee 类文件。它首先要查看存储在jre/lib和jre/lib/ext目录下的归档文件中所存放的系统类文件。显然,在那里找不到相应的类文件,然后再查看类路径。然后查找以下文件:
* /home/user/classdir/com/horstmann/corejava/Employee.class
*  ./com/horstmann/corejava/Employee.class 
*  com/horstmann/corejava/Employee.class inside /home/user/archives/archive.jar

编译器定位文件要比虚拟机复杂得多。如果引用了一个类，而没有指出这个类所在的包，那么编译器将首先查找包含这个类的包，并询查所有的 import 指令，确定其中是否包含了被引用的类。 例如， 假定源文件包含指令:
`import java.util.*;`
`import com.horstmann.corejava.*;`
并且源代码引用了 Employee 类。 编译器将试图查找 java.lang.Employee ( 因为 java.lang 包被 默认导入 )、 java.util.Employee、 com.horstmann.corejava.Employee 和当前包中的 Employee。
22. 为什么优先使用不可变类：更改对象的问题在于，如果多个线程试图同时更新一个对象，就会发生并发更改。其结果是不可预料的。如果类是不可变的，就可以安全地在多个线程间共享其对象。
23. 关键字this有两个用途：一是引用隐式参数，二是调用该类其他的构造器，同样，super关键字也有两个用途:一是调用超类的方法， 二是调用超类的构造器。
24.   JAVA多态的问题
![image.png](https://i.loli.net/2019/01/21/5c453b3d75180.png)
25. 方法的名字和参数列表称为方法的签名
26. 下面归纳一下Java 用于控制可见性的4个访问修饰符

* 仅对本类可见————private。
* 对所有类可见————public。
* 对本包和所有子类可见————protected
* 对本包可见————默认（很遗憾)，不需要修饰符.

27. 为了防备name或hireDay可能为null的情况，需要使用Objects.equals 方法。
28. 关于equals方法
> 1. （默认方法）Object的equals方法检测两个类是否具有相同的引用。(但我们的需求经常是连个类的状态（域）相等即为相等，但这也不绝对，所以对于一个对象怎样算相等应当具体问题具体分析)
> 2. 两给类的状态相等即为相等这一情况又一般分为两种情况：
> * 例如AbstractSet.equals中的equals被定义为final（实际并不是，但后续覆盖的话基本思想不变只是使算法更高效），这是由于TreeSet和HashSet的实例也应当可以相等，只要他们包含的元素一样。一般来讲（上面特例），此时对于该类的所有子类都不允许重载。(对所有的AbstractSet子类都有同样的“语义”)
> * 严格控制只有实例的class相同才可能相等。
> 3. 下面给出编写一个完美的equals 方法的建议：
1 ) 显式参数命名为otherObject, 稍后需要将它转换成另一个叫做other 的变量。
2 ) 检测this与otherObject 是否引用同一个对象：
`if (this = otherObject) return true;`
3 ) 检测otherObject 是否为null .
`if (otherObject = null ) return false;`
4 ) 比较this 与otherObject 是否属于同一个类。如果equals 的语义在每个子类中有所改变，就使用getClass 检测：
`if (getClass() != otherObject.getCIass()) return false;`
如果所有的子类都拥有统一的语义，就使用instanceof 检测：
`if (!(otherObject instanceof ClassName)) return false;`
5 ) 将otherObject 转换为相应的类类型变量：
`ClassName other = (ClassName) otherObject`
6 ) 现在开始对所有需要比较的域进行比较了。使用== 比较基本类型域，使用equals比
较对象域。如果所有的域都匹配，就返回true; 否则返回false。
`return fieldl == other.field&& Objects.equa1s(fie1d2,`
`other.field2)`
**如果在子类中重新定义equals**,就要在其中包含调用super.equals(other)  

29. 对于数组类型的域，可以使用静态的Arrays.equals方法检测相应的数组元素是否相等。

30.hashcodeAPI
`int type.hashcode(type instance);`
`Objects.hash(name, salary, hireDay) ;`
`static int java.util.Arrays.hashCode(type[] a)`
31.Equals 与hashCode 的定义必须一致：如果x.equals(y) 返回true, 那么x.hashCode()就必须与y.hashCode()具有相同的值。例如，如果用定义的Employee.equals比较雇员的ID，那么hashCode 方法就需要散列ID，而不是雇员的姓名或存储地址。
32. 这就是Java 中不尽如人意的参数化类型的限制所带来的结果。鉴于兼容性的考虑，编译器在对类型转换进行检査之后， 如果没有发现违反规则的现象，就将所有的类型化数组列表转换成原始ArrayList对象。在程序运行时， 所有的数组列表都是一样的，即没有虚拟机中的类型参数。因此，类型转换（ArrayList ) 和( ArrayList<Employee> ) 将执行相同的运行时检查。
33. 下面这个调用
`list.add(3);`
将自动地变换成
`list.add(Integer.value0f(3)) ;`
这种变换被称为**自动装箱（autoboxing)**。
int n = list.get(i);
翻译成
int n = list.get(i).intValue();
这种变换被称为**自动拆箱（autoboxing)**.
在算术表达式中也能够自动地装箱和拆箱：
`Integer n = 3;`
`n++;`
自动拆装箱是编译器操作而不是虚拟机操作，编译器在编译时添加适当方法
34. 注意区分不可变对象和可变对象。
35. 可以将已经存在且**最后一个**参数是数组的方法重新定义为可变参数的方法，而不会破坏任何已经存在的代码,Object… 参数类型与Object[] 完全一样, 当然基本类型也是可以，如下面的例子。
```java
public static double max(double... values)
{
    double largest = Double.NECATIVEJNFINITY;
    for (double v : values) if (v > largest) largest = v;
    return largest;
}
```
36. 枚举：`public enuni Size { SMALL, MEDIUM, LARGE, EXTRAJARGE };`
实际上，这个声明定义的类型是一个类， 它刚好有4 个实例， 在此尽量不要构造新对象。
因此， 在比较两个枚举类型的值时， 永远不需要调用equals, 而直接使用“ = =” 就
可以了。
37. 枚举的复杂用法：
```java
public enum Size
{
    SMALL("S"), MEDIUM("M") , LARGE("L") , EXTRA_LARGE("XL");//只有四个对象
    private String abbreviation;
    private Size(String abbreviation) { this,abbreviation = abbreviation; }
    public String getAbbreviation() { return abbreviation; }
}
```

`Size s = Enum.valueOf(Size.class, "SMALL");`
`Size[] Size.values()`
38. 反射
> `Class cl = Cl ass.forName(className) ;`
鉴于历史原getName 方法在应用于数组类型的时候会返回一个很奇怪的名字：
• Double[] class.getName() 返回“ [Ljava.lang.Double; ’’
• int[].class.getName()返回“ [I ” ，
虚拟机为每个类型管理一个Class对象。因此， 可以利用=运算符实现两个类对象比较的操作
> Class 类的getDeclareFields、getDeclareMethods和getDeclaredConstructors方法将分别返回类中声明的全部域、方法和构造器， 其中包括私有和受保护成员，但不包括超类的成员。


39. Java 数组会记住每个元素的类型， 即创建数组时new 表达式中使用的元素类型。将一个Employee[ ]临时地转换成Object[ ] 数组， 然后再把它转换回来是可以的，但一从开始就是Objectt ] 的数组却永远不能转换成Employe [] 数组。
下面是java.util.Arrays.copyof的实现。
```java
public static Object badCopyOf(Object[] a, int newLength) // not useful
{
    ObjectD newArray = new Object[newlength]:
    System.arraycopy(a, 0, newArray, 0, Math.min(a.length, newLength)) ;
    //注意这个方法
    return newArray;
}
public static Object goodCopyOf(Object a, int newLength)
{
    Class cl = a.getClass()；
    if (！cl.isArray()) return null ;
    Class componentType = cl.getComponentType()；//注意
    int length = Array.getLength(a);
    Object newArray = Array.newlnstance(componentType, newLength) ://注意 java.lang.Array
    System.arraycopy(a, 0, newArray, 0, Math.min(length, newLength)) ;
    return newArray;
}
```
40. 调用任意方法
`Object invoke(Object obj, Object... args)` 如果是静态方法obj填null
41. 虽然在接口中不能包含实例域或**静态方法(java8之前)**，但却可以包含常量.
42. 目前为止， 通常的做法都是将静态方法放在伴随类中。在标准库中， 你会看到成对出现
的接口和实用工具类， 如Collection/Collections 或Path/Paths。面来看Paths 类， 其中只包含两个工厂方法。可以由一个字符串序列构造一个文件或目录的路径， 如Paths.get("jdk1.8.0", "jre", "bin")。在Java SE 8中， 可以为Path 接口增加以下方法：
```java
public interface Path{
    public static Path get(String first, String... more) {
    return Fi1eSystems.getDefault().getPath(first, more);
    }
}
```
这样一来， Paths 类就不再是必要的了。
43. default关键字：用于接口中方法的声明，意为接口中的实现为默认实现，如果实现接口的类不覆盖则使用这个实现。
44. 默认方法的一个重要用法是“接口演化” （interface evolution)。
45. 我们只讨论了两个接口的命名冲突。现在来考虑另一种情况，一个类扩展了一个超类，同时实现了一个接口，并从超类和接口继承了相同的方法。例如，假设Person 是一个类，Student 定义为：class Student extends Person implements Named { . . . }在这种情况下， 只会考虑超类方法， 接口的所有默认方法都会被忽略。在我们的例子中， Student从Person继承了getName方法，Named接口是否为getName提供了默认实现并不会带来什么区别。这正是“ 类优先” 规则。
46. 尽管LengthComparator对象没有状态，不过还是需要建立这个对象的一个实例。我们需要这个实例来调用compare方法，它不是一个静态方法。
47. 通常子对象都是可变的，必须重新定义clone方法来建立一个深拷贝，同时克隆所有子对象。在这个例子中，hireDay域是一个Date,这是可变的，所以它也需要克隆。（出于这个原因，这个例子使用Date类型的域而不是LocalDate来展示克隆过程。如果hireDay是不可变的LocalDate类的一个实例，就无需我们做任何处理了。）
![image.png](https://i.loli.net/2019/01/21/5c453bea3e69d.png)
48. Cloneable 接口是Java提供的一组标记接口(tagging interface) 之一
标记接口不包含任何方法；它唯一的作用就是允许在类型查询中使用instanceof。即使clone的默认（浅拷贝）实现能够满足要求（实例域全部是不可变时），还是需要实现Cloneable接口，将clone重新定义为public， 再调用super.clone()。
49. 如果在一个对象上调用clone,但这个对象的类并没有实现Cloneable接口，Object 类的clone方法就会拋出一个CloneNotSupportedException当然，Employee和Date类实现了Cloneable 接口，所以不会抛出这个异常。不过，编译器并不了解这一点，因此，我们声明了这个异常。
50. 所有数组类型都有一个public的clone 方法，而不是protected,可以用这个方法
建立一个新数组，包含原数组所有元素的副本。
51. 对于只有一个抽象方法的接口， 需要这种接口的对象时，就可以提供一个lambda 表达式。这种接口称为函数式接口（ functional interface )。
52. 甚至不能把lambda表达式赋给类型为Object的变量，Object不是一个函数式接口。
53. 
```java
java.util.function 包中有一个尤其有用的接口Predicate:
public interface Predicate<T>
{
    boolean test(T t);
    // Additional default and static methods
}
ArrayList 类有一个removelf 方法， 它的参数就是一个Predicate。这个接口专门用来传递
lambda 表达式。例如，下面的语句将从一个数组列表删除所有null值：
list.removelf(e -> e == null);
```
54. 方法引用：一种lambda表达式简化方式，根据lamdba表达式所在的函数式接口的位置，确定
>从这些例子可以看出， 要用::操作符分隔方法名与对象或类名。主要有3 种情况：
* object::instanceMethod
* Class::staticMethod
* Class::instanceMethod
在前2 种情况中， 方法引用等价于提供方法参数的lambda 表达式。前面已经提到，
System.out::println 等价于x -> System.out.println(x)。 类似地，Math::pow 等价于（x，y) ->Math.pow(x, y)。
对于第3 种情况， 第1个参数会成为方法的目标。例如，String::compareToIgnoreCase 等同于(x, y) -> x.compareToIgnoreCase(y);
55. lambda 表达式中捕获的变量必须实际上是**最终变量( effectivelyfinal)**。实际上的最终变量是指， 这个变量初始化之后就不会再为它赋新值。在这里，text 总是指示同一个 String对象，所以捕获这个变量是合法的。不过，i的值会改变，因此不能捕获i。
56. 内部类既可以访问自身的数据域，也可以访问创建它的外围类对象的数据域.为了能够运行这个程序，内部类的对象总有一个隐式引用，它指向了创建它的外部类对象。
57. TimePrinter 类声明为私有的。这样一来，只有TalkingClock的方法才能够构造TimePrinter 对象。只有内部类可以是私有类，而常规类只可以具有包可见性，或公有可见性。
58. 外围类，内部类。
59. 使用静态内部类的原因，使用内部类只是为了把一个类隐藏在另外一个类的内部，并不需要内部类引用外围类对象。为此，可以将内部类声明为static,以便取消产生的引用。
60. 这种功能只有在编译时无法确定需要实现哪个接口时才有必要使用，对于用程序设计人员来说，遇到这种情况的机会很少。
61. “ 如果出现RuntimeException 异常， 那么就一定是你的问题” 是一条相当有道理的规则。
应该通过检测数组下标是否越界来避免ArraylndexOutOfBoundsException 异常；应该通过在使用变量之前检测是否为null来杜绝NullPointerException异常的发生：
62. 前面曾经提到过：如果编写一个覆盖超类的方法，而这个方法又没有抛出异常（如JComponent中的paintComponent),那么这个方法就必须捕获方法代码中出现的每一个受查异常。不许在子类的throws 说明符中出现超过超类方法所列出的异常类范围。
63. catch (FileNotFoundException | UnknownHostException e) { . . . }
64. 同样，也不应该声明从RuntimeException 继承的那些非受查异常.
```java 
class MyAnimation
{
    void drawlmage(int i) throws ArraylndexOutOfBoundsException // bad style
    {
    }
}
```
65. 未被任何变量引用的日志记录器可能会被垃圾回收。为了防止这种情况发生，要像上面的例子中一样，用一个静态变量存储日志记录器的一个引用。

## JAVA和C++的区别

| 什么方面 | JAVA | C++ | 备注 |
| --- | --- | --- | --- |
| 类中函数 | 方法 | 成员函数 | |
| 字面数值表示 | 可以加下划线 | 不可以 | |
| 进制表示 | 可表示二进制（0b或0B） | 不可以 | |
| 无符号数 | 没有 | 有 | |
| 逗号运算符 | 没有 | 有 | |
| 更改器方法与访问器方法 | 无明显区别 | const关键字 | |
| 方法参数 | 按值（引用也是按值） | 真引用（换个名字） | |
  [2]: https://www.nobler.xyz/wp-content/uploads/2019/01/WX20190106-145446.png