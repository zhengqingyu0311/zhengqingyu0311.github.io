---
title: C++类型转换
mathjax: true
categories: 编程
tags:
  - 编程
  - 算法
  - C++
  - 技巧
abbrlink: 2308
date: 2022-09-16 19:57:39
---
## C++类型转换
| 函数名 | 作  用 |
|--|--|
| ``itoa()`` | 将整型值转换为字符串 |
| ``itoa()`` | 将长整型值转换为字符串 |
|``atoi()``| 将字符串转换为整型数值|
| ``ultoa()`` | 将无符号长整型值转换为字符串 |
***
在 ``stdlib.h`` 中 ``atoi`` 函数,可用于将 ``char`` 字符串转为 ``int`` 整数类型
***
``atoi`` (表示 $\text{ascii to integer}$ )是把字符串转换成整型数的一个函数，应用在计算机程序和办公软件中. 
``int atoi(const char & nptr) `` 函数会扫描参数 ``nptr`` 字符串，会跳过前面的空白字符（例如空格，``tab`` 缩进）等。如果 ``nptr`` 不能转换成 ``int`` 或者 ``nptr`` 为空字符串，那么将返回 $0$。特别注意，该函数要求被转换的字符串是按十进制数理解的。``atoi`` 输入的字符串对应数字存在大小限制（与``int``类型大小有关），若其过大可能报错 $-1$ 。
***
### 转换示例：连续加减乘运算
### 题目描述
给出一序列数值及其运算符号，依次进行计算（不考虑优先级）。

### 输入
每行一个运算符号以及运算数。第一个数前面的符号为 $+/-$ 号，第二数前面的符号才是运算符,  $+$ 号可以省略
### 输出
最后的运算结果。==整数不用输出符号==，负数必须输出符号
### 样例输入 #1
```
-19
+21
*10
 5
-3
```
### 样例输出 #1
```
22
```
***
### 正解
```cpp
#include<bits/stdc++.h>
using namespace std;
int ans=0;string s;
int main(){
	while(cin>>s){
		if(isdigit(s[0]))ans+=atoi(s.c_str());
		else{
			if(s[0]=='+')s.erase(0,1),ans+=atoi(s.c_str());
			else if(s[0]=='-')s.erase(0,1),ans-=atoi(s.c_str());
			else if(s[0]=='*')s.erase(0,1),ans*=atoi(s.c_str());
			else if(s[0]=='/')s.erase(0,1),ans/=atoi(s.c_str());
		}
	}
	cout<<ans<<endl;
	return 0;
}
```

