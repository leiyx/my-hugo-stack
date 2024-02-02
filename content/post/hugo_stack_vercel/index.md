---
title: hugo_stack_vercel
date: 2023-09-07
description: 博客搭建记录
tags: 
    - 博客
categories:
    - 博客
---

## hugo

```shell
# 构建你的站点，并将文件发布到public目录中。要将站点发布到其他目录，请使用--destination标志或在站点配置中设置publishDir。
hugo

# 将站点构建到内存中，并使用一个最小的HTTP服务器提供页面。运行hugo server后，它会显示你本地站点的URL
hugo server

# 以上两个命令都可以在后面附上--buildDrafts、-D
# --buildDrafts 等价于 -D  表示发布草稿

```

## stack

[stack主题官方文档](https://stack.jimmycai.com/guide/)


## 部署到vercel

1. 部署

登录vercel，new project 选中github上对应库，框架选择hugo，最后注意以下几点：
- BUILD COMMAND 替换为 `amazon-linux-extras install golang1.11 && hugo --gc --minify`
- OUTPUT DIRECTORY 设置为 public
- 添加环境变量：HUGO_VERSION  0.93.2
开始构建，构建成功后就能看见网站了。

> 第一步结束后，在任何地方对你的github对应库进行push后，vercel会自动重新部署更新

2. 按照操作提示添加自己的域名

3. cdn加速
