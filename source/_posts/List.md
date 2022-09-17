---
title: List
date: 2022-09-17 10:32:07
tags: c# 面向对象
---

## 它跟Arraylist的区别
- 基本方法一致，但是它是不需要拆箱和装箱的，因为它可以限定数据类型

```csharp
// See https://aka.ms/new-console-template for more information

//创建泛形集合对象
List<int> list = new List<int>();

//DONE
//这个里面放的是条件，以后再说
//list.RemoveAll() 

//list 泛形集合可以转换为数组
int[] ints = list.ToArray();
```