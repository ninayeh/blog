---
title: Hexo 部署到 GitHub Page
date: 2023-11-19 23:05:32
tags:
categories:
  - 學習
---


# GitHub 部署
我的 Repository 是原本就存在的，所以就略過建立的步驟。
也因為預設的 main 分支已經是拿來紀錄每一次的 commit，所以不希望部署的時候蓋掉 main 分支的 commit 紀錄。

<!-- more -->

後來是參考 Hexo 官方的 [One-Command Deployment - Git](https://hexo.io/docs/one-command-deployment#Git) 的篇章，在設定時讓部屬的時候用的會是 gh-pages。

這邊也有中文版的文件 [在 GitHub Pages 上部署 Hexo - 一鍵部署](https://hexo.io/zh-tw/docs/github-pages.html#%E4%B8%80%E9%8D%B5%E9%83%A8%E5%B1%AC)

按照步驟
1. 安裝 hexo-deployer-git
```
npm install hexo-deployer-git --save
```

2. 編輯 _config.yml 
```
deploy:
  type: git
  repo: git@github.com:ninayeh/ninayeh.github.io.git
  branch: gh-pages
```

3. 使用指令部署網站
`hexo clean && hexo deploy`

4. 檢查網站 username.github.io


# 最後
雖然現在整理起來不過是幾行字的事情，但當時在操作上因為弄錯了導致分支沒有辦法如我預期的一個是紀錄、另一個是部署。

好在參考了文件，也參考了許多人的筆記，最後能夠以自己想要的形式完成了分支的管理，部落格也部署成功了。

參考：https://blog.ccknbc.cc/posts/hexo-toss/