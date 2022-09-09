---
title: out参数
date: 2022-09-09 15:56:43
tags:
---

## out 参数的用途
- 当你在方法中需要返回多个变量，类型也不一样，这时候，就可以使用out类型的参数，它可以返回多余的变量 
>  需要注意⚠️ ，它在方法中，必须被赋值

### 格式 
- public 返回类型 方法名（参数类型 传入的参数，out 参数类型 形参数 )
- 方法调用的时候，记得out 

```c#
using System;

namespace 函数
{
    class Program
    {  static string _name = "zhangsan";
      static string _password = "123456";
        static void Main(string[] args)
        {
            while (true)
            {
                Console.WriteLine("请输入用户名:");
                string name = Console.ReadLine();
                Console.WriteLine("请输入密码:");
                string psw = Console.ReadLine();
                string message;



                if (CheckInput(name, psw, out message))
                {
                    Console.WriteLine(message);

                    Console.ReadKey();

                    return;

                }
                else
                {
                    Console.WriteLine(message);
                    Console.ReadKey();
                    continue;
                }

            }
        }
            
        

        //分别提示用户输入用户名和密码
        //写一个方法判断用户输入的是否正确
        //返回给用户一个登录结果，并且还要单独的返回用户的一个登录信息
        public static bool CheckInput(string name,string password,out string message)
        {      
            if (name != _name)
            { 
                message = "用户名不正确";
                return false;
            }else if(password != _password)
            {
                message = "密码不正确";
                return false;
            }
            else
            {
                message = "用户登录成功";
                return true;
            }
            
          

          
        }


    }
}


```