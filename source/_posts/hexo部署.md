---
title: hexo部署
date: 2022-09-09 12:13:24
tags: hexo
---

## 配置文件

- 查看官方文档，里面写< >，配置文件中也必须写



### 安装hexo

- 电脑中需要有npm,node
- npm install -g hexo-cli
- hexo version 查看是否安装成功
- hexo init myblog 创建site
- cd myblog
- npm install
- hexo g 生产静态页面
- hexo server 可以在本地查看
- git init
- git remote add origin url
- git add . 
- git commit -m ""
- git push -u origin main
- hexo clean & hexo d
  - 这里我修改了配置，也无法部署，只能手动git push
  -  npm install hexo-deployer-git --save
- hexo new "" 自动生成到post文件夹中



### 部署到netify

- 直接到网站上操作就可以了
- npm run build

