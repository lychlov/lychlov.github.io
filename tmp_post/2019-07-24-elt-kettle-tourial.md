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
ETL——是英文 Extract-Transform-Load 的缩写，用来描述将数据从来源端经过抽取（extract）、转换（transform）、加载（load）至目的端的过程。
通俗的说法就是从数据源抽取数据出来，进行清洗加工转换，然后加载到定义好的数据仓库模型中去。
目的是将企业中的分散、零乱、标准不统一的数据整合到一起，为企业的决策提供分析依据。
ETL是BI项目重要的一个环节，其设计的好坏影响生成数据的质量，直接关系到BI项目的成败。
ETL的定义 ETL分别是“Extract”、“ Transform” 、“Load”三个单词的首字母缩写也就是“抽取”、“转换”、“装载” ，但我们日常往往简称其为数据抽取。ETL是BI/DW（商务智能/数据仓库）的 核心和灵魂，按照统一的规则集成并提高数据的价值，是负责完成数据从数据源向目标数据仓库转化的过程，是实施数据仓库的重要步骤。ETL包含了三方面，首 先是“抽取”：将数据从各种原始的业务系统中读取出来，这是所有工作的前提。其次“转换”：按照预先设计好的规则将抽取得数据进行转换，使本来异构的数据 格式能统一起来。最后“装载”：将转换完的数据按计划增量或全部导入到数据仓库中。
ETL是数据仓库中的非常重要的一环，是承前启后的必要的一步。ETL负责将分布的、异构数据源中的数据如关系数据、平面数据文件等抽取到临时中间层后进行清洗、转换、集成，最后加载到数据仓库或数据集市中，成为联机分析处理、数据挖掘的基础。下面给大家介绍一下什么是ETL以及ETL常用的三种工具（Datastage，Informatica，Kettle）！

## Kettle介绍
Kettle是一款国外开源的ETL工具，纯Java编写，可以在Window、Linux、Unix上运行，数据抽取高效稳定。
Kettle 中文名称叫水壶，该项目的主程序员MATT 希望把各种数据放到一个壶里，然后以一种指定的格式流出。
Kettle这个ETL工具集，它允许你管理来自不同数据库的数据，通过提供一个图形化的用户环境来描述你想做什么，而不是你想怎么做。
Kettle中有两种脚本文件，transformation和job，transformation完成针对数据的基础转换，job则完成整个工作流的控制。
Kettle是一款国外开源的ETL工具，纯java编写，绿色无需安装，数据抽取高效稳定(数据迁移工具)。
ETL是数据抽取（Extract）、清洗（Cleaning）、转换（Transform）、装载（Load）的过程。
Kettle中有两种脚本文件，transformation和job，transformation完成针对数据的基础转换，好比工厂里的生产流水线，每个组件相当于一个员工；
job则完成整个工作流的控制，好比工厂里的管理。如果用记事本打开文件可发现转换和作业都是xml类型文件。

[官方网址：https://community.hitachivantara.com/docs/DOC-1009855](https://community.hitachivantara.com/docs/DOC-1009855)

### Kettle特性
    
    *
     
### 同类产品对比


### 在工作中的应用

## 扩展知识-Apache Nifi
