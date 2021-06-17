---
layout:        post
title:         "Git | 代码提交"
subtitle:      "本地仓库更改后同时提交到多个远程仓库"
date:          2021-06-17
author:        "Haauleon"
header-style:  text
catalog:       true
tags:
    - Git
---

## 背景
&emsp;&emsp;写了个博客，开始是在 github 上拉下来的代码，本地仓库代码做了更改，想提交到 github 远程的同时提交到 gitee 远程仓库。于是乎有了这个需求。              


<br><br>

## 实践
1.检查当前仓库关联的远程仓库地址              
```
D:\Git仓库\haauleon.github.io>git remote -v
origin  https://github.com/Haauleon/haauleon.github.io.git (fetch)
origin  https://github.com/Haauleon/haauleon.github.io.git (push) 
```

<br>

2.添加 gitee 远程仓库      
```
D:\Git仓库\haauleon.github.io>git remote set-url --add origin https://gitee.com/haauleon/haauleon.git
```      

<br>

3.再次检查当前关联的远程仓库（显示已成功添加 gitee 远程仓库成功）        
```
D:\Git仓库\haauleon.github.io>git remote -v
origin  https://github.com/Haauleon/haauleon.github.io.git (fetch)
origin  https://github.com/Haauleon/haauleon.github.io.git (push) 
origin  https://gitee.com/haauleon/haauleon.git (push)
```      

<br>

4.修改本地仓库代码       
```
D:\Git仓库\haauleon.github.io>git add .
D:\Git仓库\haauleon.github.io>git commit -a -m "[create] create post"
```    

<br>

5.同时提交到 github 和 gitee 远程仓库     
```
# 加 -–all 表示推送到所有的远程仓库
D:\Git仓库\haauleon.github.io>git push origin master --all  
```