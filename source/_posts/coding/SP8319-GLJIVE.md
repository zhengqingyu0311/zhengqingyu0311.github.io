---
title: 洛谷SP8319 GLJIVE 题解
mathjax: true
categories: 编程
tags:
  - 编程
  - C++
  - 算法
  - 洛谷
  - 题解
  - SPOJ
abbrlink: 42143
date: 2022-09-17 09:25:06
---
# GLJIVE - GLJIVE

## 题面翻译

给定十个整数，询问一个前缀和使得它与 100 的差值最小，如果与 100 的差值相同，取大的那一个。

## 题目描述

>In front of Super Mario there are **10 mushrooms**, arranged in a row. A certain amount of points is awarded for picking each of the mushrooms. Super Mario must pick mushrooms **in order** they appear, but is not required to pick them all – his goal is to score a number of points **as close as possible to 100**.    
In case there exist two such numbers which are equally close to 100 (e.g. 98 and 102), Mario will pick the **greater** one (in this case 102).    
Help Super Mario and tell him how many points he will score.  

## 输入格式

>Input consists of 10 lines, each of which contains one positive integer less than or equal to 100, denoting the scores awarded for picking each mushroom, in the order that Mario can pick them in.

## 输出格式

>The first and only line of output must contain the required number of points.

## 样例 #1

### 样例输入 #1

```
10
20
30
40
50
60
70
80
90
100
```

### 样例输出 #1

```
100
```

### 思路： 
求出 $a_1\sim a_t(t=10)$ 的前缀和， 用求绝对值函数取出 $a$ 数组中每个 $\left\vert a_i -100\right\vert$ 的值，如果比答案更优，更新答案为当前 $\left\vert a_i -100\right\vert$  的值，输出答案。

### 模拟过程：  
 
|  $\quad i\quad$ | $\quad1\quad$ | $\quad2\quad$ | $\quad3\quad$ | $\quad4\quad$ | $\quad5\quad$ | $\quad6\quad$ | $\quad7\quad$ | $\quad8\quad$ | $\quad9\quad$ | $\quad10\quad$ |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :---: |
| $\quad n\quad$  | $10$ | $20$ | $30$ | $40$ | $50$ | $60$ | $70$ | $80$ | $90$ | $100$ |
| $\quad\; a_i\quad$  | $10$ | $30$ | $60$ | $100$ | $150$ | $210$ | $280$ | $360$ | $450$ | $550$ |
| $\quad\left\vert a_i -100\right\vert\quad$ | $90$ | $70$ | $40$ |  $0$  | $50$ | $110$ | $180$ | $260$ | $350$ | $450$ |

**解释**：　
   
当 $i=1$ 时， $n=10$ ， 由于 $a_1$ 之前没有数，所以此时的前缀和 $a_i=n=10$  。  

当 $i=2$ 时， $n=20$ ， $a_{i-1}=a_1=10$ ，所以前缀和 $a_2=n+a_1=10+20=30$   。  

当 $i=3$ 时， $n=30$ ， $a_{i-1}=a_2=30$ ，所以前缀和 $a_3=n+a_2=10+20+30=30+30=60$  。  
  
以此类推……   
接下来是关于表格中 $a_{i}-100$ 的绝对值的推导过程：   
$\because a_1=10$ ， $\therefore\left\vert a_1 -100\right\vert=\left\vert 90-100\right\vert=\left\vert -10\right\vert=10$ 。  

$\because a_2=30$ ， $\therefore\left\vert a_2-100\right\vert=\left\vert 30-100\right\vert=\left\vert -70\right\vert=70$ 。  

$\because a_3=60$ ， $\therefore\left\vert a_3 -100\right\vert=\left\vert 60-100\right\vert=\left\vert -40\right\vert=40$ 。

### 前缀和求法
```cpp
//使用循环求解
for(int i=1;i<=t;i++){
	cin>>n;//输入n  
	a[i]=n+a[i-1];//第a[i]个数是当前n加上a数组中上一个数
}
```
### AC代码:  
```cpp
#include<bits/stdc++.h>  
using namespace std;
const int t=10;//定义常量 
long long n,ans,a[110];
void input(){//输入函数 
	for(int i=1;i<=t;i++){
		cin>>n;//输入n  
		a[i]=n+a[i-1];//求前缀和
	}
}
int main(){
	input();//使用输入函数
	for(int i=t;i>0;i--)//从大到小模拟，如果与 100 的差值相同，取大的那一个 
		if(abs(ans-100)>abs(a[i]-100))ans=a[i];//如果有更优解，更新答案 
	cout<<ans<<endl;//输出ans 
	return 0;
} 

```

