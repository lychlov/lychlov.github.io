---
layout: post
title:  L1-IT-开发-知识培训
date:   2019-07-20 14:10:51
categories: L1
comments: true
---
# L1考试-IT-开发专业知识体系培训

![pie](/assets/L1/pie-chart.png)

IT-开发L1认证考试的主要内容包括：通信基础知识、OSS基础知识、IT基础知识、数据库知识、软件开发管理、编程技术、大数据技术等内容。
其中通信基础知识、IT基础知识、数据库知识内容较为基础，且占比较高，建议大家优先学习、复习。


## 通信基础知识

主要考察通信网络相关的基础知识内容，网络制式、组网架构、网元功能等知识点，与日常维护工作相关性较强。

## OSS基础知识

主要考察网络运维中网管系统的相关知识，各网管系统的主要功能和基础架构等知识点，占比较小，题目简单。

## IT基础知识

以基本概念知识点为主。
- 计算机系统基础
- 操作系统基础：Linux、Windows
- 云计算基本概念
- 虚拟化、Docker基本概念
- 计算机网络基本概念
- 安全基本概念

## 数据库知识

题目较多，知识面覆盖广，但知识点浅显易懂，了解基本概念即可满足。

- 数据库基本操作
- 数据库概念知识：模式、事务、ER图、范式、实体关系等
- SQL语言：基本应用

## 软件开发管理

占比很少，基本了解即可，主要是一些DevOps和Scrum概念。

### DevOps
DevOps（Development和Operations的组合词）是一组过程、方法与系统的统称，用于促进开发（应用程序/软件工程）、技术运营和质量保障（QA）部门之间的沟通、协作与整合。

它是一种重视“软件开发人员（Dev）”和“IT运维技术人员（Ops）”之间沟通合作的文化、运动或惯例。透过自动化“软件交付”和“架构变更”的流程，来使得构建、测试、发布软件能够更加地快捷、频繁和可靠。

它的出现是由于软件行业日益清晰地认识到：为了按时交付软件产品和服务，开发和运营工作必须紧密合作。

![devops](https://gss0.bdstatic.com/-4o3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=618ff02df1deb48fef64a98c9176514c/0b55b319ebc4b745dfdcdd5acdfc1e178a821535.jpg)


### Scrum
Scrum 是用于开发、交付和持续支持复杂产品的一个框架，是一个增量的、迭代的开发过程。在这个框架中，整个开发过程由若干个短的迭代周期组成，一个短的迭代周期称为一个Sprint，每个Sprint的建议长度是一至四周。

在Scrum中，使用产品Backlog来管理产品的需求，产品backlog是一个按照商业价值排序的需求列表，列表条目的体现形式通常为用户故事。Scrum团队总是先开发对客户具有较高价值的需求。

在Sprint中，Scrum团队从产品Backlog中挑选最高优先级的需求进行开发。挑选的需求在Sprint计划会议上经过讨论、分析和估算得到相应的任务列表，我们称它为Sprint backlog。在每个迭代结束时，Scrum团队将递交潜在可交付的产品增量。 

Scrum起源于软件开发项目，但它适用于任何复杂的或是创新性的项目。Scrum 目前已被用于开发软件、硬件、嵌入式软件、交互功能网络、自动驾驶、学校、政府、市场、管理组织运营，以及几乎我们（作为个体和群体）日常生活中所使用的一切。
![scrum](http://5b0988e595225.cdn.sohucs.com/images/20180925/260755327ce94dc285b2bb987da681eb.jpeg)

Scrum框架包括3个角色、3个工件、5个事件、5个价值：

#### 3个角色

- 产品负责人（Product Owner）：
- Scrum Master
- 开发团队

#### 3个工件

- 产品Backlog（Product Backlog）
- SprintBacklog
- 产品增量（Increment）

#### 5个事件

- Sprint（Sprint本身是一个事件，包括了如下4个事件）
- Sprint计划会议（Sprint Planning Meeting）
- 每日站会（Daily Scrum Meeting）
- Sprint评审会议（Sprint Review Meeting）
- Sprint回顾会议（Sprint Retrospective Meeting）

#### 5个价值

- 承诺:愿意对目标做出承诺
- 专注:把你的心思和能力都用到你承诺的工作上去
- 开放:Scrum 把项目中的一切开放给每个人看
- 尊重:每个人都有他独特的背景和经验
- 勇气:有勇气做出承诺，履行承诺，接受别人的尊重

## 编程技术

主要是数据结构与算法的知识点，以及简单的程序阅读题目。

- 各种排序算法：快速、冒泡、选择、堆、归并等，只需了解基本原理和概念。
- 二叉树：
- 线性表、栈和队列：
- Java中数据结构基本概念：

### 排序算法

![algorithm](https://img-blog.csdn.net/20180913191410473?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JlYWxfbGlzYQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

1. 冒泡排序

基本思想：两个数比较大小，较大的数下沉，较小的数冒起来。

过程：
比较相邻的两个数据，如果第二个数小，就交换位置。
从后向前两两比较，一直到比较最前两个数据。最终最小数被交换到起始的位置，这样第一个最小数的位置就排好了。
继续重复上述过程，依次将第2.3...n-1个最小数排好位置。
![bubble](http://5b0988e595225.cdn.sohucs.com/images/20181009/e9011afacb434ea09c8a156dc9983bfb.gif)

2. 选择排序

基本思想：
在长度为N的无序数组中，第一次遍历n-1个数，找到最小的数值与第一个元素交换；
第二次遍历n-2个数，找到最小的数值与第二个元素交换；
。。。
第n-1次遍历，找到最小的数值与第n-1个元素交换，排序完成。
![select](https://www.runoob.com/wp-content/uploads/2015/09/12401)

3. 快速排序

基本思想：（分治）

先从数列中取出一个数作为key值；
将比这个数小的数全部放在它的左边，大于或等于它的数全部放在它的右边；
对左右两个小数列重复第二步，直至各区间只有1个数。

![quick](http://5b0988e595225.cdn.sohucs.com/images/20181009/bc6b0e52a9174bcaa71c2cb54c030d82.gif)

4. 归并排序

基本思想：
归并排序是建立在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用。将已有序的子序列合并，得到完全有序的序列；即先使每个子序列有序，再使子序列段间有序。若将两个有序表合并成一个有序表，称为2-路归并。

过程：
把长度为n的输入序列分成两个长度为n/2的子序列；
对这两个子序列分别采用归并排序；
将两个排序好的子序列合并成一个最终的排序序列。
![merge](http://5b0988e595225.cdn.sohucs.com/images/20181009/19840a8b80d6465dbe2026157435ad2c.gif)

知识点总结
![all](http://5b0988e595225.cdn.sohucs.com/images/20181009/cd87f05072c54e3782ebb8e781966a72.jpeg)

### 二叉树

树是数据结构中的重中之重，尤其以各类二叉树为学习的难点。一直以来，对于树的掌握都是模棱两可的状态，现在希望通过写一个关于二叉树的专题系列。在学习与总结的同时更加深入的了解掌握二叉树。本系列文章将着重介绍一般二叉树、完全二叉树、满二叉树、线索二叉树、霍夫曼树、二叉排序树、平衡二叉树、红黑树、B树。

#### 树的定义

树（Tree）是n（n>=0)个结点的有限集。n=0时称为空树。在任意一颗非空树中：
- 1）有且仅有一个特定的称为根（Root）的结点；
- 2）当n>1时，其余结点可分为m(m>0)个互不相交的有限集T1、T2、......、Tn，其中每一个集合本身又是一棵树，并且称为根的子树。

此外，树的定义还需要强调以下两点：
- 1）n>0时根结点是唯一的，不可能存在多个根结点，数据结构中的树只能有一个根结点。
- 2）m>0时，子树的个数没有限制，但它们一定是互不相交的。
![tree](https://upload-images.jianshu.io/upload_images/7043118-2c735a2733887dc3.png?imageMogr2/auto-orient/strip|imageView2/2/format/webp)

#### 度
![degree](https://upload-images.jianshu.io/upload_images/7043118-cfa7c45bb8f1e332.png?imageMogr2/auto-orient/strip|imageView2/2/w/535/format/webp)

#### 层次
![level](https://upload-images.jianshu.io/upload_images/7043118-7c9318a6f5c1349d.png?imageMogr2/auto-orient/strip|imageView2/2/w/652/format/webp)

#### 满二叉树
在一棵二叉树中。如果所有分支结点都存在左子树和右子树，并且所有叶子都在同一层上，这样的二叉树称为满二叉树。
满二叉树的特点有：
- 1）叶子只能出现在最下一层。出现在其它层就不可能达成平衡。
- 2）非叶子结点的度一定是2。
- 3）在同样深度的二叉树中，满二叉树的结点个数最多，叶子数最多。
![full-tree](https://upload-images.jianshu.io/upload_images/7043118-c7a557dda4ffc7da.png?imageMogr2/auto-orient/strip|imageView2/2/w/392/format/webp)

#### 完全二叉树
对一颗具有n个结点的二叉树按层编号，如果编号为i(1<=i<=n)的结点与同样深度的满二叉树中编号为i的结点在二叉树中位置完全相同，则这棵二叉树称为完全二叉树。
![total-tree](https://upload-images.jianshu.io/upload_images/7043118-132fd0379f34bcc1.png?imageMogr2/auto-orient/strip|imageView2/2/w/404/format/webp)

#### 遍历方式
![tree-example](https://upload-images.jianshu.io/upload_images/7043118-df454c0a574836de.png?imageMogr2/auto-orient/strip|imageView2/2/w/441/format/webp)

- 前序遍历：ABDHIEJCFG
- 中序遍历：HDIBJEAFCG
- 后序遍历：HIDJEBFGCA
- 层次遍历：ABCDEFGHIJ
#### 线性表
线性表，全名为线性存储结构。使用线性表存储数据的方式可以这样理解，即“把所有数据用一根线儿串起来，再存储到物理空间中”。
![linear](http://c.biancheng.net/uploads/allimg/190426/1G0425554-2.gif)
- 顺序存储结构
- 链式存储结构
![linked](http://c.biancheng.net/uploads/allimg/190426/1G4213X2-3.gif)


#### 栈和队列
![stack-queue](/assets/L1/stack-queue.png)
- 栈：后进先出（LIFO-last in first out）:最后插入的元素最先出来。
- 队列：先进先出（FIFO-first in first out）:最先插入的元素最先出来。



## 大数据技术

大数据相关的基础概念知识

- HDFS
- Hadoop
- Spark
- 大数据概念


### Hadoop
Hadoop实现了一个分布式文件系统（Hadoop Distributed File System），简称HDFS。HDFS有高容错性的特点，并且设计用来部署在低廉的（low-cost）硬件上；而且它提供高吞吐量（high throughput）来访问应用程序的数据，适合那些有着超大数据集（large data set）的应用程序。HDFS放宽了（relax）POSIX的要求，可以以流的形式访问（streaming access）文件系统中的数据。

Hadoop的框架最核心的设计就是：HDFS和MapReduce。HDFS为海量的数据提供了存储，而MapReduce则为海量的数据提供了计算。

适合
- 大规模数据
- 流式数据（写一次，读多次）
- 商用硬件（一般硬件）
不适合
- 低延时的数据访问
- 大量的小文件
- 频繁修改文件（基本就是写1次）

![hadoop](https://atts.w3cschool.cn/attachments/image/wk/hadoop/architecture.png)
- HDFS: 分布式文件存储
- YARN: 分布式资源管理
- MapReduce: 分布式计算
- Others: 利用YARN的资源管理功能实现其他的数据处理方式

#### HDFS
![hdfs](https://atts.w3cschool.cn/attachments/image/20190627/1561603936683523.png)
##### Block数据块;

1. 基本存储单位，一般大小为64M（配置大的块主要是因为：1）减少搜寻时间，一般硬盘传输速率比寻道时间要快，大的块可以减少寻道时间；2）减少管理块的数据开销，每个块都需要在NameNode上有对应的记录；3）对数据块进行读写，减少建立网络的连接成本）
2. 一个大文件会被拆分成一个个的块，然后存储于不同的机器。如果一个文件少于Block大小，那么实际占用的空间为其文件的大小
3. 基本的读写单位，类似于磁盘的页，每次都是读写一个块
4. 每个块都会被复制到多台机器，默认复制3份

##### NameNode

1. 存储文件的metadata，运行时所有数据都保存到内存，整个HDFS可存储的文件数受限于NameNode的内存大小
2. 一个Block在NameNode中对应一条记录（一般一个block占用150字节），如果是大量的小文件，会消耗大量内存。同时map task的数量是由splits来决定的，所以用MapReduce处理大量的小文件时，就会产生过多的map task，线程管理开销将会增加作业时间。处理大量小文件的速度远远小于处理同等大小的大文件的速度。因此Hadoop建议存储大文件
3. 数据会定时保存到本地磁盘，但不保存block的位置信息，而是由DataNode注册时上报和运行时维护（NameNode中与DataNode相关的信息并不保存到NameNode的文件系统中，而是NameNode每次重启后，动态重建）
4. NameNode失效则整个HDFS都失效了，所以要保证NameNode的可用性

##### Secondary NameNode

定时与NameNode进行同步（定期合并文件系统镜像和编辑日志，然后把合并后的传给NameNode，替换其镜像，并清空编辑日志，类似于CheckPoint机制），但NameNode失效后仍需要手工将其设置成主机

##### DataNode

1. 保存具体的block数据
2. 负责数据的读写操作和复制操作
3. DataNode启动时会向NameNode报告当前存储的数据块信息，后续也会定时报告修改信息
4. DataNode之间会进行通信，复制数据块，保证数据的冗余性

#### MapReduce
![map-reduce](https://atts.w3cschool.cn/attachments/image/wk/hadoop/mapreduce-process-overview.png)

- Record reader:记录阅读器会翻译由输入格式生成的记录，记录阅读器用于将数据解析给记录，并不分析记录自身。记录读取器的目的是将数据解析成记录，但不分析记录本身。它将数据以键值对的形式传输给mapper。通常键是位置信息，值是构成记录的数据存储块.自定义记录不在本文讨论范围之内.
- Map:在映射器中用户提供的代码称为中间对。对于键值的具体定义是慎重的，因为定义对于分布式任务的完成具有重要意义.键决定了数据分类的依据，而值决定了处理器中的分析信息.本书的设计模式将会展示大量细节来解释特定键值如何选择.
- Shuffle and Sort:ruduce任务以随机和排序步骤开始。此步骤写入输出文件并下载到本地计算机。这些数据采用键进行排序以把等价密钥组合到一起。
- Reduce:reducer采用分组数据作为输入。该功能传递键和此键相关值的迭代器。可以采用多种方式来汇总、过滤或者合并数据。当ruduce功能完成，就会发送0个或多个键值对。
- 输出格式:输出格式会转换最终的键值对并写入文件。默认情况下键和值以tab分割，各记录以换行符分割。因此可以自定义更多输出格式，最终数据会写入HDFS。类似记录读取，自定义输出格式不在本书范围。

