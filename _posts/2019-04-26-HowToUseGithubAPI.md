---
layout:     post   				    # 使用的布局（不需要改）
title:      手把手教你使用GitHub API备份仓库issues				# 标题
subtitle:   HowToUseGitHubAPI #副标题
date:       2019-04-30 				# 时间
author:     Molly 						# 作者
header-img: img/restful.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 12Code:tool
---
> GitHub API是典型的REST风格的web API，是学习REST API设计的优质样本。本文的初衷是为了备份某些重要仓库的issues进行的一篇学习输出。

## 使用cURL工具
* cURL是一个利用URL语法在命令行下工作的文件传输工具。
* 如果没有安装，需要在自己的电脑上安装cURL。
* 使用git bash来使用cURL的命令发送请求
>下面是常用的cURL的相关请求的整理清单，需要使用的时候被备查
* GET ONLY RESPONSE
``curl url``
* GET RESPONSE AND HEADERS
``curl -i url``
* GET ONLY HEADERS
``curl --head url``
``curl -I url``
* GET DETAILS OF CLIENT SERVER INTERACTION
``curl -v url``
* GET EVEN MORE DETAILS AND LOG ALL INTERACTION TO FILE
``curl --trace FILE URL``
* SEND HEADERS IN REQUEST
``curl -H "Accept:application/json"``
* POST
``curl URL -d "POST_CONTENT"``
``curl -X POST -H "Accept:application/json" https://reqres.in/api/users -d '{"name": "morpheus", "job": "leader"}'``
* PUT
`` curl -i -X PUT https://reqres.in/api/users/2 -d '{"name": "morpheus", "job": "zion resident"}'``
* DELETE
``curl -i -X DELETE https://reqres.in/api/users/2``
## 发送请求
* Githu的Schema是``https://api.github.com``
* 查阅githubAPI文档在git bash中调用相应的命令行
## postman
其实也可以使用postman模拟发送请求这个工具完成这个需求

### References：
* [How to use CURL on Windows | How to test API with CURL | CURL Basics Step by Step - YouTube](https://www.youtube.com/watch?v=8f9DfgRGOBo)
* [GitHub API v3 | GitHub Developer Guide](https://developer.github.com/v3/)
