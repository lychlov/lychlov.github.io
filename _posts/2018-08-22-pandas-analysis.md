---
layout: post
title:  使用Pandas进行告警处理及分析
date:   2018-08-22 14:10:51
categories: python,pandas
comments: true
---
# 告警业务分析
![pandas](https://pandas.pydata.org/_static/pandas_logo.png)
- [Pandas](https://pandas.pydata.org):强大的Python数据分析工具。


## 题目内容
### 题干
本试题为告警处理方向的试题。选手应根据试题提供的行政区域的资源信息，基站资源信息，告警信息，对基站的中断情况进行全面的分析。并在此基础上，分析基站可用情况，衍生大面积断站的预警信息，甚至大面积断站严重告警，分析基站可用率情况。
### 数据输入
1. 行政区域信息：省、市、县
2. 基站资源信息
3. 告警信息
[下载地址](/assets/csv.rar)
### 算法说明
1. 在基站的资源信息中标示了每一个基站归属的行政区域
2. 现网中，基站会因为停电，设备故障，线路故障等原因，导致基站停止运行，形成断站，现网中该种类型告警的告警号为007-103-00-040012。中断的基站经过处理后，会恢复正常。
3. 某基站告警号为007-103-00-040012的告警产生后又恢复，则该基站的中断时长即为“告警恢复时间”减去“告警发生时间”所得出的时长“。如果在统计的时间点，断站告警仍未清除，则中断时长为“告警发生时间”至当前统计时间的时长即为该基站的中断时长
4. 某个地市本地网如果同时有60个或以上的基站中断，则应衍生一条本地网大面积断站二级预警。某地市如果同时有150个或以上的基站中断，则应衍生一条本地网大面积断站一级预警。如果预警的条件不再满足则生成预警恢复消息，同时预警清除。对于资源信息中有工程标记，退网标记的基站，其产生的告警信息不纳入统计。

### 题目&求解
[Jupyter Notebook代码地址](https://github.com/lychlov/compaign/blob/master/alarm_anlysis.ipynb)
使用pandas并导入csv
{% highlight python %}
import pandas as pd
sheng = pd.read_csv(r'..camp\sheng.csv')
shi=pd.read_csv(r'..\camp\shi.csv')
xian=pd.read_csv(r'..\camp\xian.csv')
alarms=pd.read_csv(r'..\camp\alarms.csv')
jizhan=pd.read_csv(r'..\camp\jizhan.csv')
{% endhighlight %}
- 问题1：统计该省本地网的数量，县区的数量，全省可用基站的数量（不含工程标记和退网标记）以及全省基站的数量，并输出至文件count.csv，结果分为四行，每行一个数字，第一行为本地网数，第二行为县区数，第三行为可用基站数，第四行为基站数。
    - 本地网的数量对应市行政区域信息条数
    - 县区的数量对应县区信息条数
    - 全省可用基站的数量对应基站信息表中状态为“在网”的基站信息条数。
    - 全省基站的数量对应基站信息条数。
{% highlight python %}
# 使用pandas的info函数查看表信息可得到信息条数
jizhan.info()
jizhan_in_use = jizhan[jizhan.status == '在网']
jizhan_in_use.info()
{% endhighlight %}
- 问题2：对于告警信息进行标准化，并统计8月8日0点至2018年8月8日24点，标准化后告警数量从多到少数量排名前三的地市的告警数量，并输出至文件citys.csv，结果分为三行，每行一个数字，第一行为数量最多的本地网的告警数，第二行为数量第二多的本地网的告警数，第三行为数量第三多的本地网的告警数
{% highlight python %}
# 使用pandasmerge函数对数据进行关联，形成标准化告警。
standard_alarms=pd.merge(alarms,jizhan,on='alarm_object')
standard_alarms=pd.merge(standard_alarms,xian,on='xian_id')
standard_alarms=pd.merge(standard_alarms,shi,on='shi_id')
standard_alarms.head()
# 将两列时间信息转成datetime格式
standard_alarms['end_time'] =pd.to_datetime(standard_alarms['end_time'])
standard_alarms['start_time'] =pd.to_datetime(standard_alarms['start_time'])
# 按照时间条件进行筛选
zero = pd.to_datetime('2018-08-08 00:00:00')
two_four = pd.to_datetime('2018-08-09 00:00:00')
standard_alarms[(standard_alarms.start_time < two_four)] \
    [standard_alarms.start_time >= zero].groupby('shi_name').describe() \
    ['serial_no'].sort_values(by='count', ascending=False)
{% endhighlight %}
