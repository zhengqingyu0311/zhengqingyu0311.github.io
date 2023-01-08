---
title: C++排序函数
categories: 编程
tags:
  - 编程
  - C++
  - 算法
  - 排序
abbrlink: 39415
date: 2022-09-17 13:03:47
---
## 各种排序算法函数
***
### 冒泡排序：
```cpp
void maopao(int a[],int n){
	for(int i=1;i<n;i++){
		for(int j=1;j<=n-i;j++)
		{
			if(a[j]<a[j+1]){
				swap(a[j],a[j+1]);
			}
		}
	}
}
```
***
### 选择排序：
```cpp
void xuanze(int a[],int n){
	int minx;
	for(int i=0;i<n-1;i++)
	{
		minx=i;
		for(int j=i+1;j<n;j++){
			if(a[minx]>arr[j])minx=j;
		}
		if(minx!=i){
			swap(a[i],a[minx]);
		}
	}
}
```
***
### 插入排序：
```cpp
void charu(int a[],int n){
	for(int i=2;i<=n;i++){
		for(int j=i-1;j>=0;j--){
			if(a[j]<a[i]){
			for(int k=i;k>=j+1;k--)a[k+1]=a[k];
			a[j+1]=a[i];
			break;
			}	
		}
	}
}
```
***
## 快速排序：
```cpp
void ksort(int l,int r){
	if(l>r)return;
	int key=a[l];
	int i=l;int j=r;
	while(i!=j){
		while(a[j]>=key&&i<j)j--;
		while(a[i]<=key&&i<j)i++;
		if(i<j)swap(a[i],a[j]);
	}
	a[l]=a[i];a[i]=key;
	ksort(l,i-1);
	ksort(i+1,r);
}
```
***
### 归并排序：
```cpp
void msort(int s,int t){
  if(s==t)return;
  int m=(s+t)/2;
    msort(s,m);msort(m+1,t);
  int k=s,i=s,j=m+1;
    while(i<=m&&j<=t){
         if(h[i]<=h[j])r[k]=h[i],i++,k++;
             else r[k]=h[j],j++,k++,t1+=m-i+1;
   } 
  while(i<=m)r[k]=h[i],i++,k++;
  while(j<=t)r[k]=h[j],j++,k++;
  for(int i=s;i<=t;i++)h[i]=r[i];
 }
```
***
### 希尔排序 [待完善]()
```cpp
//希尔排序：待完善代码
/*
void shell(int a[],int len){
	int g;
	int key;
	for(g=len>>1;g>0;g=g>>1){
		for(int i=g;i<len;i++){
			key=a[i];
			for(int j=i-g;j>=0&&a[j]>key;j-=g)a[j+g]=a[j];
			a[j+g]=key;
		}
	}	
}
*/
```
***
### STL 快排 sort
```cpp
#include<bits/stdc++.h>
using namespace std;
int n,a[100010]
int main(){
	cin>>n;
	for(int i=1;i<=n;i++)cin>>a[i];
	sort(a+1,a+n+1);
	for(int i=1;i<=n;i++)cout<<a[i]<<" ";
	return 0;
}
```
***
### 函数使用方法：
```cpp
#include<bits/stdc++.h>
using namespace std;
int n,a[100010]
int main(){
	cin>>n;
	for(int i=1;i<=n;i++)cin>>a[i];
	//以上一种排序函数：
	//_______________;
	//如 maopao(a,n);
	for(int i=1;i<=n;i++)cout<<a[i]<<" ";
	return 0;
}
```