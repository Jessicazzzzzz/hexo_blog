---
title: HashTable
date: 2022-09-14 20:28:14
tags: c# 面向对象
---

### 键值对
- 通过键-- 找到value ，那么就意味这这个键必须是唯一的
- 如果已经有了key ，那么是无法使用add
- 想要覆盖必须使用索引的方式来覆盖

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

### var 关键字
- 根据变量的类型来判断变量是什么类型，但是它有个问题，就是使用前必须使用给变量赋值