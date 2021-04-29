---
title: Hexo站点建设之—如何将github站点布置到本地
date: 2021-04-26 16:49:59
categories:
- 技术
- hexo
tags:
- hexo
---

## 1、拷贝相关文件


*可以将下列文件提交到git，从git拉代码*

必须拷贝文件：  
├──_config.yml  
├── themes # 主题模板  
├── scaffolds #文章模板  
├── package.json #说明使用哪些包  
├── .gitignore #限定在提交的时候哪些文件可以忽略  
└── source  


（1）讨论下哪些文件是必须拷贝的：首先是之前自己修改的文件，像站点配置_config.yml，theme文件夹里面的主题，以及source里面自己写的博客文件，这些肯定要拷贝的。除此之外，还有三个文件需要有，就是scaffolds文件夹（文章的模板）、package.json（说明使用哪些包）和.gitignore（限定在提交的时候哪些文件可以忽略）。其实，这三个文件不是我们修改的，所以即使丢失了，也没有关系，我们可以建立一个新的文件夹，然后在里面执行hexo init，就会生成这三个文件，我们只需要将它们拷贝过来使用即可。总结：_config.yml，theme/，source/，scaffolds/，package.json，.gitignore，是需要拷贝的。

（2）再讨论下哪些文件是不必拷贝的，或者说可以删除的：首先是.git文件，无论是在站点根目录下，还是主题目录下的.git文件，都可以删掉。然后是文件夹node_modules（在用npm install会重新生成），public（这个在用hexo g时会重新生成），.deploy_git文件夹（在使用hexo d时也会重新生成），db.json文件。其实上面这些文件也就是是.gitignore文件里面记载的可以忽略的内容。总结：.git/，node_modules/，public/，.deploy_git/，db.json文件需要删除。

## 2、安装模块

执行命令 `npm install`  
安装完会生成 `node_modules`文件夹  

## 3、生成文件并发布

```
hexo clean  
hexo deploy  
```

引用参考
`https://www.jianshu.com/p/906294181814`
`https://blog.csdn.net/qq_34187711/article/details/88592760`

