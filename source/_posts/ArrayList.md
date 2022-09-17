---
title: ArrayList
date: 2022-09-14 19:56:04
tags: c# 面向对象
---
## Add 跟AddRange的区别
- Add 打印引用类型的时候需要做判断
- AddRange 不需要

## 一些需要掌握的方法
- Clear()
- Remove()
- RemoveAT()
- RemoveRange()
- Sort()
- Reverse()
- Insert()
- InsertRange()
- Contains() 很重要，可以判断是否有这个元素


```csharp
// See https://aka.ms/new-console-template for more information
using System.Collections;

Console.WriteLine("Hello, World!");

ArrayList list = new ArrayList();

// DONE
//Add 添加引用类型的时候，输入需要做判断，写逻辑
//AddRange 添加引用类型，可以直接输出结果
list.AddRange(new int[]{1,2,3,4});
for(int i = 0; i < list.Count; i++)
{
    Console.WriteLine(list[i]);
}

//写一个长度为10的集合，要求里面随机的存放10个数字（0-9）
//但是要求所有的数字不重复
Random r = new Random();
ArrayList l = new ArrayList();
for(int i = 0; i < 10; i++)
{
    int rNum = r.Next(0, 10);
    if (!l.Contains(rNum))
    {
     l.Add(rNum);
    }
    else
    {
        i--;
    }
   
}
for(int i = 0; i < l.Count; i++)
{
    Console.Write(l[i]+"\t");
}

Console.ReadKey();
```

