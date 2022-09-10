---
title: out参数
date: 2022-09-09 15:56:43
tags: c#
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
        /// <summary>
        /// 判断登录是否成功
        /// </summary>
        /// <param name="name">用户名</param>
        /// <param name="password">密码</param>
        /// <param name="message">多余的返回值</param>
        /// <returns></returns>
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

#### 自己写一个TryParse()
```c#
using System;

namespace _09自己动手写tryparse
{
    class Program
    {
        static void Main(string[] args)
        {
            int num;
            //bool b = int.TryParse("123", out num);
            bool b = MyTryParse("1234a", out num);
            Console.WriteLine(num);
            Console.WriteLine(b);
            Console.ReadKey();
        }
        /// <summary>
        /// 自己写的tryParse ,它将字符串转换为数字，如果无法转换成数字，不会抛异常，只会返回bool
        /// 并且返回值为0
        /// </summary>
        /// <param name="str">需要转换成int类型的字符串</param>
        /// <param name="num">多余的返回值，返回转换成功的数字</param>
        /// <returns></returns>
        public static bool MyTryParse(string str, out int num)
        {
            try
            {
                num = Convert.ToInt32(str);
                return true;
            }
            catch
            {
                num = 0;//这里也必须给num赋值
                Console.WriteLine("不能转换为数字");
                return false;
            }

        }
    }
}


```