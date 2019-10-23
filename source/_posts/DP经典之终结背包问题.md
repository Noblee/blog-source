---
title: DP经典之终结背包问题
tags:
  - 笔记
  - 算法
  - 动态规划
originContent: >-
  # DP经典之终结背包问题


  前两天刷题一道完全背包问题，无论如何都超时，百思不得其解。查了之后才知道有一维数组的解决方法。现来总结一下基本的背包问题。

  <!-- more -->

  ### 01背包

  #### 状态转移方程：

  `f[i][j] = max(f[i - 1][j] , f[i - 1][j - weight[i]] + value[i]) `

  > i为物品范围（列），j为背包重量（行）

  n个物品，m空间


  #### 举例如何分析转移方程：

  其一，我们发现列扫描（j固定，i变化）只能从小到大。原因是我们所求值（f（i,j））所在位置的列值(j)和需要用到的数据列值**有相同**且为前置数据（f(i-1,j)），故必然只能从小到大。


  其二，行扫描（i固定，j变化）则无所谓。原因是我们所求值（f（i,j））所在位置的行值(i)和需要用到的数据列值**都不同**，故当前行扫描无论以何种顺序都是正确的。


  其三，由于行扫描只需要扫描前一行的数据，最多只需要当前行和上一行，故实际上不需要简历f[n][m]数组，只需要f[2][m]即可，i-1之前的状态不需要要记忆。


  其四，进一步的来讲，不难想到，可以通过适当的扫描顺序来重复利用一行数据达到仅使用一位数组的目的。即将行扫描倒序进行。此时的倒序进行不是转移方程所要求的，而是优化技巧而已。

  #### 代码

  ```C++

  for (int i = 1; i <= n; i++) {
      for (int j = m; j >= weight[i]; j--) {
           f[j] = f[j] > f[j - weight[i]] + value[i] ? f[j] : f[j - weight[i]] + value[i];
      }
  }

  ```

  ### 完全背包

  #### 复杂状态转移方程：

  `f[i][v]=max{f[i-1][v-k*c[i]]+k*w[i]|0<=k*c[i]<=v}`

  时间复杂度：O(V*Σ(V/c[i]))

  #### 化简状态转移方程：

  `f[i][v]=max{f[i-1][v],f[i][v-c[i]]+w[i]}`

  时间复杂度：O(VN)

  > i为物品范围（列），v为背包重量（行）

  #### 为何可以这样化简？

  简要说明：

  >完全背包的特点恰是每种物品可选无限件，所以在考虑“加选一件第i种物品”这种策略时，却正需要一个可能已选入第i种物品的子结果f[i][v-c[i]]，所以就可以并且必须采用v=0..V的顺序循环。这就是这个简单的程序为何成立的道理。

  ——背包九讲

  #### 代码

  ```C++
      for (int i = 1; i <= n; i++) {
          for (int j = weight[i]; j <= m; j++) {
              f[j] = max(f[j], f[j - weight[i]] + value[i]);
          }
      }
  ```

  ### 多重背包

  #### 题目：

  有N种物品和一个容量为V的背包。第i种物品最多有n[i]件可用，每件费用是c[i]，价值是w[i]。求解将哪些物品装入背包可使这些物品的费用总和不超过背包容量，且价值总和最·大。

  #### 状态转移方程

  `f[i][v]=max{f[i-1][v-k*c[i]]+k*w[i]|0<=k<=n[i]}`

  时间复杂度：O(V*Σn[i])

  #### 转化为01背包问题

  将多个物品相同物品转化为单个不同物品，通过二进制的思想进项转化。

  >
  考虑二进制的思想，我们考虑把第i种物品换成若干件物品，使得原问题中第i种物品可取的每种策略——取0..n[i]件——均能等价于取若干件代换以后的物品。另外，取超过n[i]件的策略必不能出现。


  >方法是：将第i种物品分成若干件物品，其中每件物品有一个系数，这件物品的费用和价值均是原来的费用和价值乘以这个系数。使这些系数分别为1,2,4,...,2^(k-1),n[i]-2^k+1，且k是满足n[i]-2^k+1>0的最大整数。例如，如果n[i]为13，就将这种物品分成系数分别为1,2,4,6的四件物品。

  #### 伪代码（二进制分解法）

  ```Python

  procedure MultiplePack(cost,weight,amount)
      if cost*amount>=V
          CompletePack(cost,weight)
          return
      integer k=1
      while k<amount
          ZeroOnePack(k*cost,k*weight)
          amount=amount-k
          k=k*2
      ZeroOnePack(amount*cost,amount*weight)
  ```

  #### 代码（非二进制分解法实现）

  ```C++

  #include <iostream>

  using namespace std;

  #define V 1000

  int weight[50 + 1];

  int value[50 + 1];

  int num[20 + 1];

  int f[V + 1];

  int max(int a, int b) {
      return a > b ? a : b;
  }

  int main() {
      int n, m;
      cout << "请输入物品个数:";
      cin >> n;
      cout << "请分别输入" << n << "个物品的重量、价值和数量:" << endl; 
      for (int i = 1; i <= n; i++) {
          cin >> weight[i] >> value[i] >> num[i];
      }
      int k = n + 1;
      for (int i = 1; i <= n; i++) {
          while (num[i] != 1) {
              weight[k] = weight[i];
              value[k] = value[i];
              k++;
              num[i]--;
          }
      }
      cout << "请输入背包容量:";
      cin >> m;
      for (int i = 1; i <= k; i++) {
          for (int j = m; j >= 1; j--) {
              if (weight[i] <= j) f[j] = max(f[j], f[j - weight[i]] + value[i]);
          }
      }
      cout << "背包能放的最大价值为:" << f[m] << endl;
  }

  ```

  #### 代码（二进制分解法实现）

  //todo

  #### O(VN)算法的存在

  >
  多重背包问题同样有O(VN)的算法。这个算法基于基本算法的状态转移方程，但应用单调队列的方法使每个状态的值可以以均摊O(1)的时间求解。由于用单调队列优化的DP已超出了NOIP的范围，故本文不再展开讲解。我最初了解到这个方法是在楼天成的“男人八题”幻灯片上。


  ### 混合三种背包问题

  #### 01背包与完全背包的混合

  ##### 伪代码

  ```python

  for i=1..N
      if 第i件物品属于01背包
          for v=V..0
              f[v]=max{f[v],f[v-c[i]]+w[i]};
      else if 第i件物品属于完全背包
          for v=0..V
              f[v]=max{f[v],f[v-c[i]]+w[i]};
  ```

  #### 再加上多重背包

  ##### 伪代码

  ```python

  for i=1..N
      if 第i件物品属于01背包
          ZeroOnePack(c[i],w[i])
      else if 第i件物品属于完全背包
          CompletePack(c[i],w[i])
      else if 第i件物品属于多重背包
          MultiplePack(c[i],w[i],n[i])
  ```

  参考资料

  [背包问题九讲](https://www.kancloud.cn/kancloud/pack/70129)

  [背包问题：0-1背包、完全背包和多重背包](https://www.cnblogs.com/fengziwei/p/7750849.html)
categories:
  - 算法
toc: true
date: 2019-03-29 16:22:37
---

# DP经典之终结背包问题

前两天刷题一道完全背包问题，无论如何都超时，百思不得其解。查了之后才知道有一维数组的解决方法。现来总结一下基本的背包问题。
<!-- more --> 
### 01背包
#### 状态转移方程：
`f[i][j] = max(f[i - 1][j] , f[i - 1][j - weight[i]] + value[i]) `
> i为物品范围（列），j为背包重量（行）
n个物品，m空间

#### 举例如何分析转移方程：
其一，我们发现列扫描（j固定，i变化）只能从小到大。原因是我们所求值（f（i,j））所在位置的列值(j)和需要用到的数据列值**有相同**且为前置数据（f(i-1,j)），故必然只能从小到大。

其二，行扫描（i固定，j变化）则无所谓。原因是我们所求值（f（i,j））所在位置的行值(i)和需要用到的数据列值**都不同**，故当前行扫描无论以何种顺序都是正确的。

其三，由于行扫描只需要扫描前一行的数据，最多只需要当前行和上一行，故实际上不需要简历f[n][m]数组，只需要f[2][m]即可，i-1之前的状态不需要要记忆。

其四，进一步的来讲，不难想到，可以通过适当的扫描顺序来重复利用一行数据达到仅使用一位数组的目的。即将行扫描倒序进行。此时的倒序进行不是转移方程所要求的，而是优化技巧而已。
#### 代码
```C++
for (int i = 1; i <= n; i++) {
    for (int j = m; j >= weight[i]; j--) {
         f[j] = f[j] > f[j - weight[i]] + value[i] ? f[j] : f[j - weight[i]] + value[i];
    }
}
```
### 完全背包
#### 复杂状态转移方程：
`f[i][v]=max{f[i-1][v-k*c[i]]+k*w[i]|0<=k*c[i]<=v}`
时间复杂度：O(V*Σ(V/c[i]))
#### 化简状态转移方程：
`f[i][v]=max{f[i-1][v],f[i][v-c[i]]+w[i]}`
时间复杂度：O(VN)
> i为物品范围（列），v为背包重量（行）
#### 为何可以这样化简？
简要说明：
>完全背包的特点恰是每种物品可选无限件，所以在考虑“加选一件第i种物品”这种策略时，却正需要一个可能已选入第i种物品的子结果f[i][v-c[i]]，所以就可以并且必须采用v=0..V的顺序循环。这就是这个简单的程序为何成立的道理。
——背包九讲
#### 代码
```C++
    for (int i = 1; i <= n; i++) {
        for (int j = weight[i]; j <= m; j++) {
            f[j] = max(f[j], f[j - weight[i]] + value[i]);
        }
    }
```
### 多重背包
#### 题目：
有N种物品和一个容量为V的背包。第i种物品最多有n[i]件可用，每件费用是c[i]，价值是w[i]。求解将哪些物品装入背包可使这些物品的费用总和不超过背包容量，且价值总和最·大。
#### 状态转移方程
`f[i][v]=max{f[i-1][v-k*c[i]]+k*w[i]|0<=k<=n[i]}`
时间复杂度：O(V*Σn[i])
#### 转化为01背包问题
将多个物品相同物品转化为单个不同物品，通过二进制的思想进项转化。
> 考虑二进制的思想，我们考虑把第i种物品换成若干件物品，使得原问题中第i种物品可取的每种策略——取0..n[i]件——均能等价于取若干件代换以后的物品。另外，取超过n[i]件的策略必不能出现。

>方法是：将第i种物品分成若干件物品，其中每件物品有一个系数，这件物品的费用和价值均是原来的费用和价值乘以这个系数。使这些系数分别为1,2,4,...,2^(k-1),n[i]-2^k+1，且k是满足n[i]-2^k+1>0的最大整数。例如，如果n[i]为13，就将这种物品分成系数分别为1,2,4,6的四件物品。
#### 伪代码（二进制分解法）
```Python
procedure MultiplePack(cost,weight,amount)
    if cost*amount>=V
        CompletePack(cost,weight)
        return
    integer k=1
    while k<amount
        ZeroOnePack(k*cost,k*weight)
        amount=amount-k
        k=k*2
    ZeroOnePack(amount*cost,amount*weight)
```
#### 代码（非二进制分解法实现）
```C++
#include <iostream>
using namespace std;
#define V 1000
int weight[50 + 1];
int value[50 + 1];
int num[20 + 1];
int f[V + 1];
int max(int a, int b) {
    return a > b ? a : b;
}
int main() {
    int n, m;
    cout << "请输入物品个数:";
    cin >> n;
    cout << "请分别输入" << n << "个物品的重量、价值和数量:" << endl; 
    for (int i = 1; i <= n; i++) {
        cin >> weight[i] >> value[i] >> num[i];
    }
    int k = n + 1;
    for (int i = 1; i <= n; i++) {
        while (num[i] != 1) {
            weight[k] = weight[i];
            value[k] = value[i];
            k++;
            num[i]--;
        }
    }
    cout << "请输入背包容量:";
    cin >> m;
    for (int i = 1; i <= k; i++) {
        for (int j = m; j >= 1; j--) {
            if (weight[i] <= j) f[j] = max(f[j], f[j - weight[i]] + value[i]);
        }
    }
    cout << "背包能放的最大价值为:" << f[m] << endl;
}
```
#### 代码（二进制分解法实现）
//todo
#### O(VN)算法的存在
> 多重背包问题同样有O(VN)的算法。这个算法基于基本算法的状态转移方程，但应用单调队列的方法使每个状态的值可以以均摊O(1)的时间求解。由于用单调队列优化的DP已超出了NOIP的范围，故本文不再展开讲解。我最初了解到这个方法是在楼天成的“男人八题”幻灯片上。

### 混合三种背包问题
#### 01背包与完全背包的混合
##### 伪代码
```python
for i=1..N
    if 第i件物品属于01背包
        for v=V..0
            f[v]=max{f[v],f[v-c[i]]+w[i]};
    else if 第i件物品属于完全背包
        for v=0..V
            f[v]=max{f[v],f[v-c[i]]+w[i]};
```
#### 再加上多重背包
##### 伪代码
```python
for i=1..N
    if 第i件物品属于01背包
        ZeroOnePack(c[i],w[i])
    else if 第i件物品属于完全背包
        CompletePack(c[i],w[i])
    else if 第i件物品属于多重背包
        MultiplePack(c[i],w[i],n[i])
```
参考资料
[背包问题九讲](https://www.kancloud.cn/kancloud/pack/70129)
[背包问题：0-1背包、完全背包和多重背包](https://www.cnblogs.com/fengziwei/p/7750849.html)