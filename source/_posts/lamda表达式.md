---
title: lamda表达式
date: 2022-09-18 20:36:44
tags: c# 面向对象
---
```csharp

List<int> ints = new List<int>() { 1,2,3,4,5,6};
ints.RemoveAll(n => n < 4);//lamba表达式
foreach (var item in ints)
{
Console.WriteLine(item);
}
Console.ReadKey();
```