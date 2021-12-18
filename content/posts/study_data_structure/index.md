---
title: Learning Data Structure & Algorithm
date: "2020-09-03"
tags: ["nodejs", "express"]
published: true
description: "学习数据结构和算法的总结。"
---
## Preface

数据结构和算法属于基础的东西，有句话就是program = data structure + algorithm. 数据结构构造不同的存储数据方式（往往根据现实需求），通过特定算法组成程序的逻辑，解决真实问题。实际中并不会去手写一个stack/queue/linkedlist来去解决问题，这些在不同语言中已经实现了，关键是用他们去解决一些问题（比如地图染色，找最大最小，etc）。

## 书籍 Books

### 《算法导论》Introduction to Algorithms

这本书从recursion开始讲起，包括不同的数据结构（stack|queue|heap|hash table|binary search tree),排序算法（merge sort|binary search|quick sort), 还有一部分图算法。

优点是：内容设置很合理，从最简单的递归－>深度优先，广度优先，最简单的选择排序－>二分查找－>合并排序，快速排序，然后再次基础上讲图算法。
缺点是：每一章节会在数学论证上挖的比较深（比如各种算法的lower upper bound的证明，这种东西不太适合一般程序员，会让初学者顾此失彼。）

算法导论课后习题答案: [solution1](https://sites.math.rutgers.edu/~ajl213/CLRS/CLRS.html), [solution2](https://walkccc.github.io/CLRS/).

### 《Algorithms》算法

[地址](https://algs4.cs.princeton.edu/home/) 这本书是普林斯顿一个教授写的，完全不用买纸质书，因为全书都已经在上述的地址里了，而且包括所有内容的相关代码。并且这门课在coursera上是有视频的，并且免费。

优点：极其注重实践，和算法导论完全不是一个风格，用的语言是Java（Java各种数据结构的API设计的很规范，有些动态语言如python很灵活，比如list本身就可以当作queue和stack用，对一些不是很熟悉的学习者来说，比如我，555，在练习的时候就会产生迷惑，对学习基础的内容反而不是很有帮助）。

缺点：对初学者极其不友好。这本书最好的用户是有了一定基础的学习者。coursera上的网课第一次作业就是union find, 而且几个视频的内容是算法导论一章才能讲完的。

## 网课

a. 算法导论是没有网课的，算法这本书有网课，但是并不适合初学者。

b. 九章算法只看过一些，好像价格也比较合理，时间比较灵活，并且比较实用，适合面试的人使用。

c. 一个英文的课程：[course](https://www.educative.io/courses/grokking-the-coding-interview?aff=K7qB). 这个我其实没上过，按月收费的，而且面向找工作的人，也不是很适合初学者。

d. 我之前旁听过来offer的直播课（每周固定时间），讲得不错，但是一是很贵，二是面向的人群是在美国找工作的人。

## leetcode/lintcode

我只用过leetcode，lintcode没用过，不过应该也类似。leetcode现在有1000多题，题目质量有好有坏，怎么做leetcode，不同的人也有不同的做法：

a. 爆刷流，按照题号直接一题一题做；

b. 精刷流，对于一道题可能会钻研半天，尝试使用不同的解法（bfs｜dfs）而且不达成100%（运行时间少于100%的人）不罢休。

不同的方法没有好坏之分，只有适合不适合。之前认识的朋友，有做了300-400就去了大厂的，也有leetcode全刷了一遍去大厂的，也有极其聪明200多去谷歌的。当然，大部分人属于第一种，对于大部分题目有个基础的认识，对于不同的数据结构有清晰的用法和场景，其实就足够了。

leetcode有个板块，[explore/learn](https://leetcode.com/explore/learn/), 按照最基础的array/linkedlist/binary tree/binary search tree/hash table 来区分的。加在一起200题左右。并且每个部分先会有讲解，然后由浅入深的练习。（但是每个板块的最后几题有可能会出现hard）刚开始做的时候实在做不出来不一定非要钻牛角尖。这部分可以结合算法导论的理论部分，学习理论并且在这个板块中进行练习，个人觉得效果还行= =。
对于大部分面试来说 easy|medium （20% esay 80% medium） 绝对够用了，hard可以给学有余力或者大神去解决，而且个别hard题目解法比较刁钻。

在做完learn之后，可以参加leetcode的weekly contest，1小时30分钟 4道题目，有排名。刚开始学习的时候不建议参加= =因为很可能第一道题就不会做导致打击学习热情。

## 为什么要刷题｜学习算法数据结构？

a. 理论一点来说，算法和数据结构是学习cs的基础，坚实基础，永远都没有错。

b. 对于国外的公司（国内就是相当一部分外企+某些企业，如字节），刷题是成本最低的筛选方式。如果一个面试者题目都做得出来，那么要么很聪明，要么花了一部分时间，那么这样的人招进来，肯定符合要求。而且很多公司的项目组或者系统很复杂，进去一段时间内都在熟悉业务和整体架构，那么招个聪明或者辛勤努力的学习者，一定没错。

当然这种方式下存在两种人不适合这个筛选方式：（1）只会刷题工程能力很弱的 （2）工程能力很强但是不会刷题的。对于（1）给够一定时间学习就行了，只要脑子不笨或者愿意花时间，业务上的东西都会搞明白的，工程能力是可以慢慢培养的。对于（2），这种人有，但很少，比如2015年homebrew的作者去面试谷歌，因为不会翻转二叉树而挂掉面试（invert binary searh tree）。但是这样的人很少。没有哪一种方式是完美的～

c. 这个是玄学的说法，但是make sense: 刷题刷多了，经常动脑去思考，对于思考业务逻辑（还有工程能力）也是有一定帮助的～

## 网盘？

九章算法：[链接](https://pan.baidu.com/s/1_LRWPfuWd-Jp5yt1Ria07g)  提取码: ybsn

我上过的来offer的讲义（这个讲义对很多题目的方法都很不错）：
[链接](https://pan.baidu.com/s/1mqgQdtZ_PcGKiYmUZbSZsQ)  提取码: h5zs
