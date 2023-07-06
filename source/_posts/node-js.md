---
title: node.js
date: 2023-07-05 19:04:21
tags: js
---

## Node架构

javascript-> V8-> 中间层(libuv)->操作系统

## Node应用场景
- node 包管理工具
- npm ,yarn,pnpm
- node.js 作为web服务器,中间件,代理服务器
- SSR,完成前后端同构应用
- 编写脚本

## 管理node版本
- n
- nvm
  - nvm install latest 安装最新的版本
  - nvm list  查看版本
  - nvm use 版本号
  
## Node 输入
  #### node 中输入值
  - 它都存储在process.argv 
  
## global 
> 浏览器中有个全局变量window ,在node中就是global 
- globalThis 在浏览器中= window,在node 中= global 

## 模块开发
  ### CommonJs
  - 导出 exports 开发一般不用
  - module.exports 这个用的多
  - 导入 require()
  ```nodejs
  let name = "jess"
  module.exports= {

   NAME:name
}
  ```
```nodejs
  const re = require("js文件")
  console.log(re.NAME)
```