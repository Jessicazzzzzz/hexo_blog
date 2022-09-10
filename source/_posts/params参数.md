---
title: params参数
date: 2022-09-10 08:58:10
tags: c#
---

### params 是可变参数，当传入的参数类型是一致的时候，就可以默认他们是一个数组，那么就可以使用params关键字

- 传入的值是1,2,3,4
- 接受的参数列表就应该写为 params int[] ints
- 那么传入的值即使是有变化，也没有关系

> 注意事项：***它具有唯一性***，一个形式参数列表中只能有一个可变参数类型；***它必须在最后一个***，不然如果后面再接收同一类型的变量，它不知道是属于数组中的，还是另外一个单独变量

```csharp

namespace 可变参数{
  
class Program{

static void Main(string[] args){


int[] ints = {1,2,3,4}

//调用方法
//第一种方式传参数
ParamsUse(ints);

//第二种方式传参数
ParamsUse(1,2,3,4);


}

//求和，不知道数据是多少，那么我们就可以使用params关键字
static void ParamsUse(params int[] ints){

   int sum = 0;
   for(int i = 0;i< ints.length;i++){
     sum += ints[i];
}
  
 Console.WriteLine("数组的总和为{0}",sum);

}





}





}
```