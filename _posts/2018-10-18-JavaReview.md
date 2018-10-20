---
layout:     post   				    # 使用的布局（不需要改）
title:      2018-10-18-易错点记录 				# 标题
subtitle:   JavaReview #副标题
date:       2018-10-18 				# 时间
author:     Molly 						# 作者
header-img: img/review.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - JavaLearnReview
---

>这周进入了面向对象的学习之中。在昨天的学习里面，遇到了一些易错点。现记录于此：
---

# this的错误用法：

![](https://i.loli.net/2018/10/18/5bc7d6b1cbfe5.png)

这里我错写成了this，但其实联系上下文。这个是调用方法，而不是部署方法。特别还是在主函数里面调用方法，就更不能使用this来代替某个对象了。因为这个对象是确定的，所以只有部署方法的时候，不确定到底是类class里面的哪一个对象来调用这个方法，就需要使用this来替代所有可能对象。

修改为：

![](https://i.loli.net/2018/10/18/5bc7d77dd70e6.png)

---

# 构造方法我错加了void
![](https://i.loli.net/2018/10/18/5bc7dd40a589e.png)

构造方法不等同于普通方法，它没有返回值，甚至于连void都没有。应该这样写：
![](https://i.loli.net/2018/10/18/5bc7dd7231d25.png)

---
# 判断对象为空或者不为空
