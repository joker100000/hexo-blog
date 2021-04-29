---
title: Hexo站点建设之——WARN-No-layout-index-html
categories:
  - 技术
  - Hexo
tags:
  - hexo
date: 2021-04-26 16:03:34
---
## 一 现象描述
---
执行hexo g或hexo s时，可能会出现如下情况，
![](https://img.imgdb.cn/item/60867779d1a9ae528fbb7107.png)

## 二 原因猜测
---
* 插件
* 主题
* markdown文件

## 三 解决办法
---
### 3.1 插件

#### 3.1.1 查看npm安装hexo插件的情况

`npm ls --depth 0`
![](https://img.imgdb.cn/item/60867779d1a9ae528fbb711e.png)

#### 3.1.2 安装缺失的插件

`npm install acorn --save`
![](https://img.imgdb.cn/item/60867779d1a9ae528fbb70e2.png)

#### 3.1.3 再次执行 npm ls --depth 0查看插件安装情况

### 3.2 主题(themes)
---

#### 3.2.1 检查themes下的主题和配置
![](https://img.imgdb.cn/item/60867779d1a9ae528fbb7158.png)

#### 3.2.2 下载最新主题并配置_config.yml

`git clone https://github.com/theme-next/hexo-theme-next themes/next
`
![](https://img.imgdb.cn/item/60867779d1a9ae528fbb7144.png)

#### 3.2.3 执行hexo g查看执行情况(文件能正常生成)
![](https://img.imgdb.cn/item/60867779d1a9ae528fbb7158.png)

