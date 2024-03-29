---
layout: post
title:  ETL工具Kettle基础
date:   2019-07-20 14:10:51
categories: ETL,Kettle
comments: true
---
# ETL工具——Kettle（PDI）基础知识和网络运维实战工具
![etl-intro](/assets/kettle/etl-intro.png)

## ETL概念

ETL——是英文 Extract-Transform-Load 的缩写，用来描述将数据从来源端经过抽取（extract）、清洗（clean)、转换（transform）、加载（load）至目的端的过程。

通俗的说法就是从数据源抽取数据出来，进行清洗加工转换，然后加载到定义好的数据仓库模型中去。
ETL负责将分布的、异构数据源中的数据如关系数据、平面数据文件等抽取到临时中间层后进行清洗、转换、集成，
最后加载到数据仓库或数据集市中，成为联机分析处理、数据挖掘的基础。

目的是将企业中的分散、零乱、标准不统一的数据整合到一起，为企业的决策提供分析依据。
常用的三种工具（Datastage，Informatica，Kettle）。
在网络运维中常常使用ETL工具作为数据采集工具。

## ETL的使用场景
* 当数据来自不同的物理主机，这时候如使用SQL语句去处理的话，就显得比较吃力且开销也更大。
* 数据来源可以是各种不同的数据库或者文件，这时候需要先把他们整理成统一的格式后才可以进行数据的处理，这一过程用代码实现显然有些麻烦。
* 在数据库中我们当然可以使用存储过程去处理数据，但是处理海量数据的时候存储过程显然比较吃力，而且会占用较多数据库的资源，这可能会导致数据资源不足，进而影响数据库的性能。
* 图形化的界面操作十分方便，使用技术门槛低。
* 处理海量数据速度快、流程更清晰等，过程可视化监控。

在网络运维的自研过程中，我们常常面对的是多个系统的数据源。
面对的是“4+1”网管系统和各种辅助系统，这些数据源厂家不同、架构各异、百花齐放、眼花缭乱、花里胡哨。
需要的数据可能在Oracle、Mysql、FTP、HDFS，存放格式可能是csv、txt、excel、xml。
手动提取操作费事费力，机械重复。
需要使用ETL工具自动、可视的完成。

![bi](/assets/kettle/mengbi.gif)

## Kettle介绍
![Kettle](https://community.hitachivantara.com/servlet/JiveServlet/showImage/102-1009855-24-19581/CommunityDataIntegration%28Trans%29.png)

Kettle（PDI）是常用的ETL工具之一，纯Java编写的开源工具，绿色免安装，可以在Window、Linux、Unix上运行，数据抽取高效稳定。

在2006年 Kettle 加入了开源的 BI 组织 Pentaho，英文全称为Pentaho Data Integeration。

Kettle中文直译为水壶，该项目的主程序员MATT 希望把各种数据放到一个水壶里，然后以一种指定的格式流出。

[官方网址：https://community.hitachivantara.com/docs/DOC-1009855](https://community.hitachivantara.com/docs/DOC-1009855)

### Kettle特性
>"免费开源的基于java的企业级ETL工具，功能强大简单易用，无可抗拒"

* 免费开源：基于java的免费开源的软件，对商业用户也没有限制
* 易配置：可以在Window、Linux、Unix上运行，绿色无需安装，数据抽取高效稳定
* 异构数据源：ETL工具集，它允许你管理来自不同数据库、不同的数据
* 两种脚本文件：transformation和job，transformation完成针对数据的基础转换，job则完成整个工作流的控制
* 图形界面设计：通过图形界面设计实现逻辑设计，托拉拽组件即可，无需写代码去实现
* 定时功能：在Job下的start模块，有一个定时功能，可以每日，每周等方式进行定时

#### 使用感受
* “生产工具的进步是生产力发展的标志”，kettle和传统的编写代码相比，工具的使用在效率（包括代码复用）、可靠性、低出错率、可维护性上面绝对都是巨大的进步！
* 和任何工具一样，导入期都比较漫长，需要一些学习成本，但是请各位务必坚持下去，因为回报会非常丰厚！
* 使用Kettle使得ETL过程实现非常简单，因此设计思路就显得非常重要。
* 对于目前自研工作和自研人员的性质，Kettle工具是一个非常不错的选择毕竟维护性和开发效率都很高，而且又不会把自己拖入繁复的代码维护和修改之中。
* Kettle工具的使用有很高的上限，使用得当甚至可以直接实现报表输出等数据分析功能，甚至实现BI。

### 同类产品对比
![kettle-compare](/assets/kettle/kettle-compare.png)

![kettle-compare2](/assets/kettle/kettle-compare2.png)

### 基本概念

![concept](/assets/kettle/concept.png)
* Transformation（转换）：完成针对数据的基础转换，
好比工厂里的生产流水线，每个组件相当于一个员工；
* Job（作业）：成整个工作流的控制，好比工厂里的管理。
* 如果用记事本打开文件可发现转换和作业都是xml类型文件。
* Spoon（勺子）：允许你通过图形界面来设计ETL逻辑（Transformation/Job）。
* Kitchen（厨房）：允许你批量运行Job 。Kitchen也是一个后台运行的程序，没有图形界面。
* Pan（平底锅）：允许你批量运行Transformation。Pan是一个后台执行的程序，没有图形界面。
* Carte（菜单）：	一个轻量级的Web容器，用于建立专用、远程的ETL Server，集群运行。

#### Transformation（转换）
Transformation（转换）是由一系列被称之为step（步骤）的逻辑工作通过hop（节点连接）连接的网络。
转换本质上是数据流。下图是一个转换的例子，这个转换从文本文件中读取数据，过滤，然后排序，最后将数据加载到数据库。本质上，转换是一组图形化的数据转换配置的逻辑结构。
![trans](/assets/kettle/trans.png)
* Step(步骤)

Steps（步骤）是转换的建筑模块，比如一个文本文件输入或者一个表输出就是一个步骤。
在PDI中有140多个步骤，它们按不同功能进行分类，比如输入类、输出类、脚本类等。
每个步骤用于完成某种特定的功能，通过配置一系列的步骤就可以完成你所需要完成的任务。
* Hop（节点连接）

Hops（节点连接）是数据的通道，用于连接两个步骤，使得元数据从一个步骤传递到另一个步骤。
在上图所示的转换中，它像似顺序执行发生的，但事实并非如此。
节点连接决定了贯穿在步骤之间的数据流，步骤之间的顺序不是转换执行的顺序。
当执行一个转换时，每个步骤都以自己的线程启动，并不断的接受和推送数据。

注意：所有的步骤是同步开启和运行的，所以步骤的初始化的顺序是不可知的。

在一个转换中，一个步骤可以有多个连接，数据流可以从一个步骤流到多个步骤。
在Spoon中，hops就想是箭，它不仅允许数据从一个步骤流向另一个步骤，也决定了数据流的方向和所经步骤。
如果一个步骤的数据输出到了多个步骤，那么数据既可以是复制的，也可以是分发的。

#### Job（工作）

Jobs（工作）是基于工作流模型的，协调数据源、执行过程和相关依赖性的ETL活动。
将功能性和实体过程聚合在了一起。下图是一个Job的例子。

![job](/assets/kettle/job.png)

一个工作可实现的任务有从FTP获取文件、核查一个必须存在的数据库表是否存在、执行一个转换、发送邮件通知一个转换中的错误等。最终工作的结果可能是数据仓库的更新等。

工作由工作节点连接、工作实体和工作设置组成。

#### Transformation常用功能
* 多样化数据输入
    - 基本的文本文件
    - Access、Excel、XML、Properties文件格式
    - 关系型数据库（Oracle、DB2、Microsoft SQL Server、Microsoft Access、MySQL等）
    - Big Data（hadoop、Hbase等）
    - 系统信息，如文件名称、系统时间等

![solution](/assets/kettle/input.png)

* 多种查询
    - 调用数据库存储过程
    - 基本的数据库查询
    - 判断表以及列、操作系统文件是否存在
    - 从URL接收查询
    - 使用Web服务查询信息
    - 使用数据流中的值作为参数来执行一个数据库查询
    - 流查询：从转换中其他流里查询值

![solution](/assets/kettle/query.png)

* 转换
    - 值映射、分组、去重、拆分字段、行列转换
    - 复制行

![solution](/assets/kettle/trans-k.png)

* 数据输出
    * 把数据写入到Excel
    * 把数据写入XML、CSV
    * 把数据写入数据库，全量、增量
    
![solution](/assets/kettle/output.png)

* 支持脚本和代码
    * JS脚本
    * SQL脚本
    * 正则表达式
    * Java代码
    
![solution](/assets/kettle/script.png)

#### Job常用功能
* Ping 主机
* 写日志
* 发送邮件
* 比较文件夹、文件
* 创建、复制、移动、删除、压缩文件
* 从HTTP获取或者上传文件
* 操作延迟等待
* 判断文件是否存在
* 执行JavaScript、SQL、Shell脚本
* 支持安全FTP获取、上传文件
* 删除远程文件
* 支持SSH2上传下载

![solution](/assets/kettle/job1.png)
![solution](/assets/kettle/job2.png)
![solution](/assets/kettle/job3.png)

## 在工作中的应用——实战案例
Kettle在网络运维的使用场景非常广泛，涉及到数据采集的都可以使用。各大三方厂商在实现采集任务时也都在使用ETL工具。
* OMC 性能、配置文件采集
* DPI XDR文件采集
* 集团三费系统数据载入
* 报表汇聚（魔改功能）
* ...

![](/assets/biaoyan.jpg){:height="150px" width="150px"}

### XDR数据采集、清洗、转存案例
在2018年中，接到了一项实现集团性能管理应用市场Docker移植应用的工作。在实现某省自主研发的《视频端到端质量分析》
移植的过程中，由于应用对于数据的格式、字段内容等有特殊的要求，与集团XDR规范有差异。
- csv文件格式，字段以逗号（,)隔断
- 数据按5min时间粒度划分，超过200mb是需要切断
- 文件上传完成需要上传完成标记文件，同名的.ctl
- 文件名要求：VI_%A_%Y%m%d%H%M_%E.csv，如VI_ha_201907211400_000.csv
- 数据筛选：筛选在uri字段中包含“.letv.com”、“.le.com”、“.youku.com”、“msg.71.am” 、“msg.71.am”关键字的所有记录，其余数据抛弃
- 字段要求：

|字段名|说明|字段类型
|:---:|:--------:|:------:
|st1|开始时间戳|整数
|pts|开始时间字符串|浮点
|st2|结束时间戳|整数
|pte|结束时间字符串|浮点
|ms|手机号码|整数
|tac|TA code|整数
|eci|小区编号|整数
|sui|上行流量|整数
|sdi|下行流量|整数
|etype|事务类型|整数
|host|HOST|字符串
|uri|URl|字符串
|city|城市区号|字符串
|sgw|SGW/GGSN IP Add|字符串
|dip|App Server IP_IPv4|字符串

#### 系统环境
* 厂家做不了
    - 没有冗余机器处理
    - 当前处理逻辑不支持对原始XDR的裁剪筛选和分发
* 数据共享层有多台FTP实现FTP共享
    - 数据留存6小时
    - 分布在8台主机上
* 标准XDR数据
    - 单个文件250MB
    - 全部字段、全量记录
* 安全困境
    - 数据安全传输
    - 敏感字段脱敏

#### 解决方案
![solution](/assets/kettle/sol1.png)
根据系统的现状，设计了两个Kettle任务，分别处理FTP文件下载和数据的筛选裁剪。

* FTP下载

![solution](/assets/kettle/ftp1.png)
![solution](/assets/kettle/ftp2.png)
![solution](/assets/kettle/ftp3.png)

* 数据转换

![solution](/assets/kettle/transformation.png)

文件下载：[Job文件](/assets/kettle/docker-ftp-http.kjb)  [Tranformation文件](/assets/kettle/http-etl.ktr)

{% highlight shell %}
运行FTP下载Job
./kitchen.sh -file=/home/docker/kettle/docker-ftp-http.kjb
运行文件处理Transformation
./pan.sh -file=/home/docker/kettle/http-etl.ktr
{% endhighlight %}

### 随堂练习

#### 任务描述
在课程资料中包含部分XDR原始文件，请使用Kettle对文件进行处理
- 获取XDR文件并解压
- 对XDR文件进行过滤，过滤条件：domain字段包含baidu.com或qq.com
- 裁剪字段，保留字段：city\domain\url\type
- 每个输出文件保存300000行
- 文件存储，文件名要求：s1u_http_日期_时间_分段.csv

#### 任务解答
文件下载：[解答文件](/assets/kettle/docker-ftp-http.kjb)



## 扩展知识-Apache Nifi
