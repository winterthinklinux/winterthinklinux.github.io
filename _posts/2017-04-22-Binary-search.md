---
layout: post
title: 常见基础算法
tags: 算法
category: 算法
date: 2017-04-22 11:13:57
---


### 二分查找

```java
public static int TestBinarySearch(int [] a,int key){
		int low = 0;
		int high = a.length-1;
		while(low<=high){
			int mid = (low+high)/2;
			if(a[mid]>key)
				high = mid-1;
			else if(a[mid]<key)
				low = mid+1;
			else 
				return mid;
		
		}
	
		return -1;
	}
	public static void main(String[] args) {
		int [] a = {1,2,3,4,5,6,7,8};
		System.out.println(TestBinarySearch(a, 2));
	}
```
     编写二分查找的程序时
如果令 `left <= right，则right = middle - 1;
如果令left < right，则 right = middle;`
换言之，算法所操作的区间,是左闭右开区间,还是左闭右闭区间,这个区间,需要在循环初始化。且在循环体是否终止的判断中,以及每次修改left, right区间值这三个地方保持一致,否则就可能出错。