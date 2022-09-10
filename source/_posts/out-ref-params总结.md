---
title: out,ref,params总结
date: 2022-09-10 09:14:23
tags: c#
---

- out ,ref,params 在形式参数列表中，都必须使用关键字
- 在传参数的时候，只有out ,ref 还需要使用，params不需要，因为它只是需要通知接收方我传入的是多个同一类型的值就可以了

- out 是返回多余的类型的数据
- ref 是将值传进函数，再传出函数