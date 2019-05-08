---
layout:     post   				    # 使用的布局（不需要改）
title:      Git的简单用法1				# 标题
subtitle:   HowToUseGit1 #副标题
date:       2019-04-26 				# 时间
author:     Molly 						# 作者
header-img: img/git.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 12Code:tool
---

# git的简单操作和使用
## git的安装（省）
这一步需要安装git和tortoisegit
## 配置git的用户信息
* 配置用户名
$ git config --global user.name "examplename"
* 配置邮箱
$ git config --globale user.email example@gmail.com
同样，在乌龟git下也可以进行设置,settings→Git→username&email

## 使用Git
* 初始化git：在目标文件夹下面，使用git bash：$ git init，就会出现.git这个重要的文件夹（这个命令也就是在某个文件夹下面，使用乌龟git右键，Git create repository here）
* git add index.html让Git来跟踪这个index.html文件（这个命令也就是乌龟git里面add）
* git commit -m "我今天新建了这个index.html文件"（在乌龟git里面的操作是，
* git log 查看提交的日志


## 多人使用Git协作开发项目Git flow
* master分支
* develop分支
  * feature分支
它们之间的逻辑关系如图：
