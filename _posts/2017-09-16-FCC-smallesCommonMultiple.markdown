---
layout: post
title: FCC 找出能被两个给定参数和它们之间的连续数字整除的最小公倍数
date: 2017-09-16 20:58:00.000000000 +09:00
tags: fcc
---
***
#### 辗转相除法

##### 思路1：
=====
待求数组(allNum)的每一个数字都去除以质数数组(primes)中的元素，
**只要有一个元素能被整除**就推入commonFactor
原理理解错了，做了很久。
code：
```javascript
function smallestCommon(arr){
	var min = Math.min(arr[0],arr[1]);
	var max = Math.max(arr[0],arr[1]);
	var allNum = [];
	var primes = [];//质数
	var commonFactor = [];//存储因子
	for(var i=min;i<=max;i++){
		allNum.push(i);//生成最小到最大值之间的所有数
	}
	for(var j=2;j<=max;j++){
		primes.push(j);
	}
	primes = primes.filter(function(val){
		for(k=2;k<val;k++){
			if(val%k === 0){
				return false;
			}
		}
		retrun true;
	});
	//当allNum中有一个数不为1，则继续辗转相除
	while((allNum.filter(function(val){return (val===1)?false:true})).length>0){
		for(var m=0;m<allNum.length;m++){
			var isratio=0;
			for(var n=0;n<primes.length;n++){
				if(allNum[m]%primes[n] === 0){
					isratio=1;
					allNum[m] /= primes[n];
				}
			}
			if(isratio){
				commonFactor.push(primes[n]);
			}
		}
	}
	return commonFactor.reduce(function(acc,curr){
		return acc*curr;
	});
}
```
***
Q：如何判断一个函数数组为空？？？
`arr.length === 0`
