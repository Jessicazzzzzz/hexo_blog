---
title: filestream
date: 2022-09-17 10:32:37
tags: c# 面向对象
---

### 它可以读取大文件，因为是一部分一部分读取的
- file 是一次性读取，这个更好一点
- 需要关闭资源，可以使用using(){}的方式，就不需要手动关闭资源
- 它读取的都是字节流，所以需要转换的 Encoding.Default中的方法
- 返回一个int类型的值，表示读取了多少个字节，如果是0 ，就表示读完了，那么这个可以作为判断条件

```csharp
// See https://aka.ms/new-console-template for more information

//FileStream File
//FileStream 操作字节的
//StreamReader StreamWriter 操作字符的

using System.Text;
using static System.Net.Mime.MediaTypeNames;
//读取
FileStream fileStream = new FileStream("/Users/jessicazhu/Desktop/text.txt", FileMode.OpenOrCreate, FileAccess.Read);

byte[] bytes = new byte[1024 * 1024 * 5];//5m
//返回只读去到的字节数组的大小
int r = fileStream.Read(bytes, 0, bytes.Length);
string str = Encoding.Default.GetString(bytes,0,r);
//关闭
fileStream.Close();
//释放
fileStream.Dispose();
Console.WriteLine(str);

//写入
//用using(){}就不需要自己释放资源
using( FileStream fw = new FileStream("/Users/jessicazhu/Desktop/text1.txt",FileMode.OpenOrCreate,FileAccess.Write))
{
    string s = "看我有没有把你覆盖";
    byte[] b = Encoding.Default.GetBytes(s);//如果出现乱码，就修改Encoding.UTF-8.GetBytes(),确保读写的编码一致
    fw.Write(b,0,b.Length);
}
```

```csharp
using (FileStream fr = new FileStream("/Users/jessicazhu/Desktop/移动web/day1/05-源视频/01-阶段课程介绍.mp4", FileMode.Open, FileAccess.Read))
{
    using (FileStream fw = new FileStream("/Users/jessicazhu/Desktop/new.mp4", FileMode.OpenOrCreate, FileAccess.Write))
    {
        //每次读取的大小
        byte[] buffer = new byte[1024 * 1024 * 3];
        //循环去读取这么大的字节流
        //因为只要它读取到数据，就会返回到读取的字节流的大小，那么读不到，就是0，就可以通过这个break循环
        //每次一读入到buffer数组，就写入到目标文件中去就可以了
        while (true)
        {
            int r = fr.Read(buffer, 0, buffer.Length);
            if (r == 0)
            {
                break;
            }
            fw.Write(buffer, 0, r);

        }
    }

}
```

### StreamReader/StreamWriter
- 它们只能操作文本
```csharp
//使用streamReader来读取一个文本文件
using(StreamReader sr = new StreamReader("/Users/jessicazhu/Desktop/text.txt"))
{
    while (!sr.EndOfStream)
    {
        Console.WriteLine(sr.ReadLine());
    }
}
//写入
using(StreamWriter sw = new StreamWriter("/Users/jessicazhu/Desktop/text.txt",true))
{
    sw.Write("nihao");
}
//注意拷贝的相对路径需要在bin/debug中的可以执行的文件一起
using(FileStream fr1 = new FileStream("text1.txt",FileMode.Open,FileAccess.Read))
{
    fr1.Read(bytes, 0, bytes.Length);
    string frString = Encoding.Default.GetString(bytes, 0, bytes.Length);
    Console.WriteLine(frString);
}
Console.ReadKey();
```