---
title: dictionary
date: 2022-09-17 10:32:22
tags: c# 面向对象
---

## 它可以限定参数类型，其它跟hashtable 很像




> 循环方式可以有个好的
```csharp
foreach (KeyValuePair<int,string> keyValuePair in dic)
{
    Console.WriteLine("{0}--{1}", keyValuePair.Key, keyValuePair.Value);
}
```
 
```csharp
// See https://aka.ms/new-console-template for more information
Dictionary<int, string> dic = new Dictionary<int, string>();

dic.Add(1, "zhangsan");
//添加相同的key ,怎么zu
dic[1] = "lisi";
//另一种方式遍历
foreach (KeyValuePair<int,string> keyValuePair in dic)
{
    Console.WriteLine("{0}--{1}", keyValuePair.Key, keyValuePair.Value);
}
foreach (var item in dic.Keys)
{
    Console.WriteLine("{0}--{1}",item, dic[item]); 
}

Console.ReadKey();
```