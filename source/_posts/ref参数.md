---
title: ref参数
date: 2022-09-10 08:28:58
tags: c#
---

- 将类型变成的引用类型
### 可以在方法中改变传入的参数的值，在传回给实参数
> 注意事项：这个传入的参数是必须在传入之前就得赋值

```csharp
namespace  refVariable{
 class Program{
     
   static void Main(string[] args){
     
      int salary = 500;
     UseRef(ref salary);//注意关键字ref 
     Console.WriteLine(salary);//salary = 550;

}

static void UseRef(ref int salary){
   salary += 50;

}



}




}

```

####例子：写一个方法交换两个变量，如果没有ref 关键字，我们出了方法体，变量还是那样，因为是值拷贝！！非常重要，需要特别深刻理解值拷贝和引用传递

```csharp

namespace  交换两个变量{


class Program{

 static void Main(string[] args){
     int a = 3;
     int b = 4;

    //调用函数
Exchange(ref a,ref b);
   //此时变量的值就被改变了
    Console.WriteLine("a={0},b={1}",a,b);//4,3



}
//写一个方法交换两个变量，注意基本类型应该是值拷贝
//想要将变量交换的结果传出去，那么必须使用关键字
static void Exchange(ref int a,ref int b){
     a= a^b;
    b = a^b;
     a = a^b;

}





}





}
```

