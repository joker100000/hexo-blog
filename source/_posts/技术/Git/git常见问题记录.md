---
title: git常见问题记录
date: 2021-04-26 15:17:03
categories:
- 技术
- git
tags:
- git
---

### 1、在 .gitignore 文件中增加忽略文件不生效的解决办法

解决方法是先把本地缓存删除，然后重新加入再提交：
```
// 从本地移除缓存
git rm -rf --cached .
// 重新添加到本地
git add .
// 提交到本地仓库
git commit -m '更新 .gitignore 文件'
```

### 2、Git报错解决：OpenSSL SSL_read: Connection was reset, errno 10054

首先，造成这个错误很有可能是网络不稳定，连接超时导致的，
如果再次尝试后依然报错，可以执行下面的命令
``` git config --global http.sslVerify "false" ```

### 3、warning: LF will be replaced by CRLF in 解决办法

在windows下面提交和linux提交的换行符不一样,windows中的换行符为 CRLF 
而在linux下的换行符为LF，在windows下直接回车就会出现这个提示,修改的办法是把 core.autocrlf 设置成false

解决办法：
```git config --global core.autocrlf false```