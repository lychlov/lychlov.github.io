---
layout: post
title:  ETL工具Kettle基础
date:   2018-07-07 14:10:51
categories: ETL,Kettle
comments: true
---
# ETL工具——Kettle（PDI）教程
![Kettle](https://community.hitachivantara.com/servlet/JiveServlet/showImage/102-1009855-24-19581/CommunityDataIntegration%28Trans%29.png)

## ETL概念
ETL——是英文 Extract-Transform-Load 的缩写，用来描述将数据从来源端经过抽取（extract）、清洗（clean)、转换（transform）、加载（load）至目的端的过程。
通俗的说法就是从数据源抽取数据出来，进行清洗加工转换，然后加载到定义好的数据仓库模型中去。
ETL负责将分布的、异构数据源中的数据如关系数据、平面数据文件等抽取到临时中间层后进行清洗、转换、集成，
最后加载到数据仓库或数据集市中，成为联机分析处理、数据挖掘的基础。
目的是将企业中的分散、零乱、标准不统一的数据整合到一起，为企业的决策提供分析依据。
常用的三种工具（Datastage，Informatica，Kettle）！
在网络运维中常常使用ETL工具作为数据采集工具。

## ETL的使用场景
* 当数据来自不同的物理主机，这时候如使用SQL语句去处理的话，就显得比较吃力且开销也更大。
* 数据来源可以是各种不同的数据库或者文件，这时候需要先把他们整理成统一的格式后才可以进行数据的处理，这一过程用代码实现显然有些麻烦。
* 在数据库中我们当然可以使用存储过程去处理数据，但是处理海量数据的时候存储过程显然比较吃力，而且会占用较多数据库的资源，这可能会导致数据资源不足，进而影响数据库的性能。
* 图形化的界面操作十分方便，使用技术门槛低。
* 处理海量数据速度快、流程更清晰等，过程可视化监控。

## Kettle介绍
Kettle是常用的ETL工具之一，纯Java编写的开源工具，绿色免安装，可以在Window、Linux、Unix上运行，数据抽取高效稳定。
Kettle中文直译为水壶，该项目的主程序员MATT 希望把各种数据放到一个水壶里，然后以一种指定的格式流出。
* chef/spoon（勺子）：允许你通过图形界面来设计ETL转换过程（Transformation）。
* kitchen（厨房）：允许你批量使用由Chef设计的任务 (例如使用一个时间调度器)。KITCHEN也是一个后台运行的程序
* pan（平底锅）：允许你批量运行由Spoon设计的ETL转换 (例如使用一个时间调度器)。Pan是一个后台执行的程序，没有图形界面
Kettle这个ETL工具集，它允许你管理来自不同数据库的数据，通过提供一个图形化的用户环境来描述你想做什么，而不是你想怎么做。
Kettle中有两种脚本文件，transformation和job，transformation完成针对数据的基础转换，job则完成整个工作流的控制。
Kettle中有两种脚本文件，transformation和job，transformation完成针对数据的基础转换，
好比工厂里的生产流水线，每个组件相当于一个员工；
job则完成整个工作流的控制，好比工厂里的管理。如果用记事本打开文件可发现转换和作业都是xml类型文件。

[官方网址：https://community.hitachivantara.com/docs/DOC-1009855](https://community.hitachivantara.com/docs/DOC-1009855)

### Kettle特性
    
    *
     
### 同类产品对比


### 在工作中的应用

## 扩展知识-Apache Nifi
