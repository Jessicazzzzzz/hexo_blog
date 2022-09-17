---
title: File文件类
date: 2022-09-15 17:58:48
tags: c# 面向对象
---

### Path 类 /IO
- Path 是静态类
- 可以通过它获取文件名，文件名后缀等

### 文件乱码
- 你保存文件跟你打开文件所采用的编码不一致导致的

### 读取和写入文件 File.ReadAllBytes/File.WriteAllBytes
- 不管是读取还是写入，我们都是对bytes[]类型的数据进行操作
- 所以我们需要将我们的字符串在写入的时候转换为bytes类型，在读取的时候将bytes类型转行为字符串类型,这些都是通过Encoding.Default.GetBytes() 和Encoding.Default.GetString()来进行操作的
```csharp
// See https://aka.ms/new-console-template for more information
using System.Text;


string fileName = "/Users/jessicazhu/Desktop/text.txt";
//创建一个文件
//在创建文件之后，无法对文件进行写入?会报错
//File.Create(fileName);
//Console.WriteLine("创建成功");
//删除
//File.Delete(fileName);
//复制一个文件
//File.Copy(源路径，目标路径)
string str = "hello";
//读取和写入文件，都需将字符串跟字符数组进行转换
byte[] bytes = Encoding.Default.GetBytes(str);
File.WriteAllBytes(fileName,bytes);
byte[] bContent = File.ReadAllBytes(fileName);
string sContent = Encoding.Default.GetString(bContent);
Console.WriteLine(sContent);
Console.WriteLine("成功");
Console.ReadKey();
```