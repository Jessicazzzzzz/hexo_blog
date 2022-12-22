---
title: Grid容器布局
date: 2022-09-21 14:45:01
tags: Wpf
---

#  StackPanel
- 默认是从上到下排列

# DockPanel
- 子元素会拉伸至容器的大小，前提是子元素的前面没有其他元素占了空间
- lastChildFill 是对最后一个元素的控制

# WrapPanel
- 默认是从左到右，一行结束后到下一行

# Border
- 一般是嵌套在stackpanel等容器外面，做边框处理
- Borderthickness  边框的宽度
- BorderBrush 边框的颜色
- Background
- padding
- CornerRadius

# Grid 面板
- GridRowDefinition 设置行
- GridColumnDefinition 设置列
- showGridlines 显示网格
- 布局舍入 UseLayoutRounding = "true" 这是如果分割的格度不是整数的话，那么就渲染格子里的图片的边缘就会模糊，那么我们可以通过设置这个属性，让它清晰
- Grid.ColumnSpan 跨列
- 如果想要每一个盒子的属性设置都一样，可以使用sharedsizeGroup="名字" ,注意这个名字必须相同
- Grid.splitter 网格分割器，首先必须得给这个分一个空的Column,必须设置VerticalAlignment="center",HorizontalAlignment = "Stretch"，不然就没有效果
- 