---
title: Path类
date: 2022-09-17 10:13:50
tags: c# 面向对象
---

## Path - 读取文件路径
- 如果是windows系统 ，读取文件名前可加@ ，这样就不需要给每一个\添加转义符
- 它是静态类，直接调用它的方法就可以了

## 用途
- 调用方法获取文件名，文件名后缀等

```csharp
// See https://aka.ms/new-console-template for more information

string fileName = "/Users/jessicazhu/Desktop/github_mypic/linux目录结构 2022-08-20 10.32.55.excalidraw.png";
//自己通过string 的方法
int index = fileName.LastIndexOf("/");
string name = fileName.Substring(index + 1);
Console.WriteLine(name);
//快速获得文件名
//Path是个静态类
string  s =  Path.GetFileName(fileName);


Console.WriteLine(s);
Console.ReadKey();
```