---
title: HashTable
date: 2022-09-14 20:28:14
tags: c# 面向对象
---

### 键值对
```csharp
// See https://aka.ms/new-console-template for more information
using System.Collections;

Console.WriteLine("Hello, World!");

Hashtable hashTable = new Hashtable();

hashTable.Add(1, "张三");
hashTable.Add(2, "张一");
hashTable.Add(3, "张四");
hashTable[6] = "新来的";
hashTable[1] = "张";
//ContainsKey()
//Remove()
//Clear()
//foreach
//TODO：
//var 会根据变量的类型来决定变量是什么类型
//但是它必须在声明的时候被赋值
//通过key 拿到value
foreach (var item in hashTable.Keys)
{
    Console.WriteLine(hashTable[item]);
}
```