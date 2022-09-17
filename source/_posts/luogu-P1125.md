---
title: 洛谷P1125 笨小猴 题解
date: 2022-09-17 13:06:07
mathjax: true
categories: 编程
tags:
- 编程
- C++
- 算法
- 洛谷
- 题解
---
### [洛谷 P1125 [NOIP2008 提高组] 笨小猴](https://www.luogu.com.cn/problem/P1125) 题解
## 题目描述

笨小猴的词汇量很小，所以每次做英语选择题的时候都很头疼。但是他找到了一种方法，经试验证明，用这种方法去选择选项的时候选对的几率非常大！
这种方法的具体描述如下：假设 $\text{maxn}$ 是单词中出现次数最多的字母的出现次数，$\text{minn}$ 是单词中出现次数最少的字母的出现次数，如果 $\text{maxn}-\text{minn}$ 是一个质数，那么笨小猴就认为这是个 Lucky Word，这样的单词很可能就是正确的答案。

## 输入格式

一个单词，其中只可能出现小写字母，并且长度小于 $100$ 。

## 输出格式

共两行，第一行是一个字符串，假设输入的的单词是 Lucky Word，那么输出 `Lucky Word`，否则输出 `No Answer` ；

第二行是一个整数，如果输入单词是 `Lucky Word`，输出 $\text{maxn}-\text{minn}$ 的值，否则输出 $0$ 。

### 样例输入 #1

```
error
```

### 样例输出 #1

```
Lucky Word
2
```

### 样例输入 #2

```
olympic
```

### 样例输出 #2

```
No Answer
0
```

***

## 提示

**输入输出样例 1 解释：**

>单词 `error` 中出现最多的字母 $\texttt r$ 出现了 $3$ 次，出现次数最少的字母出现了 $1$ 次，$3-1=2$，$2$ 是 质数。

**输入输出样例 2 解释：**

>单词 `olympic` 中出现最多的字母 $\texttt i$ 出现了 $1$ 次，出现次数最少的字母出现了 $1$ 次，$1-1=0$，$0$ 不是 质数。

***
### 解题思路：  
我们首先使用 ``char`` 型储存字符串，把每个字符 用循环扫一遍 ，然后将它强制转换成``int`` 型存入 $a$ 数组,统计一遍，最后使用 STL 中的封装函数 $\text{sort}$ 进行排序，统计出最大值 $\max$ 和最小值 $\min$ ，求出它们的差，判断是否为 质数 就好了。
***
#### 这里需使用check判断质数函数:
```cpp
bool check(int x)
{
    if(x<=1) return false;//如果小于等于1，返回假
    int tt=int(sqrt(double(x)+1.0));
    for(int i=2;i<=tt;i++)
    {
       if(x%i==0)//如果x是i的倍数(说明x是合数)
       {
            return false;//返回假
       }
    }
    return true;//返回真
}
```
***
### 上代码：
```cpp
#include<bits/stdc++.h>
using namespace std;
char s[100000010];int a[200],len,n;
bool check(int x)
{
    if(x<=1) return false;
    int tt=int(sqrt(double(x)+1.0));
    for(int i=2;i<=tt;i++)
    {
       if( x%i==0)
       {
            return false;
       }
    }
    return true;
}
int main(){
	while(cin>>s){
		memset(a,0,sizeof(a));
		len=strlen(s)-1;
		for(int i=0;i<=len;i++){
			a[int(s[i])-96]++;
		}
		sort(a+1,a+26+1);
		int con=1;
		while(!a[con])con++;
		n=(a[26]-a[con]);
		//cout<<a[26]<<" "<<a[con]<<" "<<n<<endl;
		if(check(n)==true){
			cout<<"Lucky Word\n"<<n<<endl;
		}
		else cout<<"No Answer\n"<<0<<endl;
	}
	return 0;
}

```
***
$31 \text{ms  AC}$
