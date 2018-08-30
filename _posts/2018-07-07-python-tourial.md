---
layout: post
title:  Python基础培训
date:   2018-07-07 14:10:51
categories: python
comments: true
---
# Python语言基础学习
![Python](https://www.python.org/static/img/python-logo@2x.png)

## 基本介绍——WHY PYTHON？
* 集团自主研发"五个一"之一："推广一门编程语言"要求各省推广Python
* 目前稳居第四位的编程语言，[TIOBE](https://www.tiobe.com/tiobe-index/)
![TIOBE](/assets/tiobe-index.jpg)

* 人生苦短，我用python（Life is short，use Python）
![python](http://5b0988e595225.cdn.sohucs.com/images/20171212/22f1ec8cd7924cc0b513f6217abe1422.jpeg)
{% highlight java %}
//JAVA
public class HelloWorld{
    public static void main(args){
        System.out.println("Hello World!")
    }
}
{% endhighlight %}
{% highlight c %}
//C/C++
int main{
    printf("Hello World!");
    return 0;
}
{% endhighlight %}
{% highlight python %}
#python
print("Hello World")
{% endhighlight %}

* 简单、易学、应用广——逐步走进中小学课堂
* 使用Python的公司
    * 谷歌：Google App Engine 、code.google.com 、Google earth 、谷歌爬虫、Google广告等项目都在大量使用Python开发
    * NASA: 美国航天局大量使用Python进行数据分析和运算，使用tkInter编写了火箭发射仪表盘。
    * YouTube:世界上最大的视频网站YouTube就是用Python开发的
    * Dropbox:美国最大的在线云存储网站，全部用Python实现，每天网站处理10亿个文件的上传和下载
    * Instagram:美国最大的图片分享社交网站，每天超过3千万张照片被分享，全部用python开发
    * Facebook:大量的基础库均通过Python实现的
    * Redhat: 世界上最流行的Linux发行版本中的yum包管理工具就是用python开发的
    * Reddit/豆瓣: 公司几乎所有的业务均是通过Python开发的
    * Quora/知乎: 国内外最大的问答社区，通过Python开发

* Python应用领域：[Applications for Python](https://www.python.org/about/apps/)
    * Web Development: Django, Pyramid, Bottle, Tornado, Flask, web2py
    * GUI Development: tkInter, PyGObject, PyQt, PySide, Kivy, wxPython
    * Scientific and Numeric: SciPy, Pandas, IPython
    * Software Development: Buildbot, Trac, Roundup
    * System Administration: Ansible, Salt, OpenStack
    * ...

## Python开发环境搭建——HOW PYTHON？
![选择困难](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1531992846&di=25637367fa3a19c1083de8641e38e0d5&imgtype=jpg&er=1&src=http%3A%2F%2Fimg1.gtimg.com%2Fsjz_house%2Fpics%2Fhv1%2F144%2F232%2F204%2F13324404.jpg){:height="150px" width="150px"}

1. 版本：Python2 VS Python3？  
    - Python社区官方表示Python2将在2020年停止维护，大量的第三方包也逐渐迁移至Python3.
    - 对于初学者，差别不大，但推荐使用Python3。
    - Python3.X 源码文件默认使用utf-8编码，对中文支持更好。
2. 解释器：[Anaconda](https://www.anaconda.com/download/) VS [官方原生](https://www.python.org/)
    - Anaconda提供大量常用三方包，图形化管理三方包;原生需要手动使用pip命令行安装
    - Anaconda便于管理不同的开发环境，提供相互隔离的开发环境，避免各版本间互相干扰
    - 官方原生python轻便小巧，Anaconda安装包500M+
3. 安装IDE：[PyCharm](http://www.jetbrains.com/pycharm/) VS [VS Code](https://code.visualstudio.com)
    - Pycharm由JetBrains出品，VS Code由Microsoft出品
    - Pycharm更全面、提供大量插件，VS Code更轻量

## Python基本语法——PLAY WITH PYTHON
### 变量类型
{% highlight python %}
a_number = 2.42
a_string = 'Hello World!'
a_tuple = ( 'runoob', 786 , 2.23, 'john', 70.2 )
a_list = [1,2,3,4,5,'zhangsan','lisi',[6,7,8],True,False,None,(9,10)]
a_dict = {'name': 'john','code':6734, 'dept': 'sales'}
{% endhighlight %}

### 运算符
#### 算数运算符


|运算符|描述|实例
|:---:|:------|:------
|+	|加 - 两个对象相加	|a + b 输出结果 30
|-	|减 - 得到负数或是一个数减去另一个数	|a - b 输出结果 -10
|*	|乘 - 两个数相乘或是返回一个被重复若干次的字符串	|a * b 输出结果 200
|/	|除 - x除以y	|b / a 输出结果 2
|%	|取模 - 返回除法的余数	|b % a 输出结果 0
|**	|幂 - 返回x的y次幂	|a**b 为10的20次方， 输出结果 100000000000000000000
|//	|取整除 - 返回商的整数部分	|9//2 输出结果 4 , 9.0//2.0 输出结果 4.0


#### 比较运算符


|运算符|描述|实例
|:---:|:------|:------
|==	|等于 - 比较对象是否相等	|(a == b) 返回 False。
|!=	|不等于 - 比较两个对象是否不相等	|(a != b) 返回 true.
|<>	|不等于 - 比较两个对象是否不相等	|(a <> b) 返回 true。这个运算符类似 != 。
|>	|大于 - 返回x是否大于y	|(a > b) 返回 False。
|<	|小于 - 返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。这分别与特殊的变量True和False等价。	|(a < b) 返回 true。
|>=	|大于等于	- 返回x是否大于等于y。	|(a >= b) 返回 False。
|<=	|小于等于 -	返回x是否小于等于y。	|(a <= b) 返回 true。


#### 赋值运算符


|运算符|描述|实例
|:---:|:------|:------
|=	|简单的赋值运算符|c = a + b 将 a + b 的运算结果赋值为 c
|+=	|加法赋值运算符	|c += a 等效于 c = c + a
|-=	|减法赋值运算符	|c -= a 等效于 c = c - a
|*=	|乘法赋值运算符	|c *= a 等效于 c = c * a
|/=	|除法赋值运算符	|c /= a 等效于 c = c / a
|%=	|取模赋值运算符	|c %= a 等效于 c = c % a
|**=|幂赋值运算符	|c **= a 等效于 c = c ** a
|//=|取整除赋值运算符	|c //= a 等效于 c = c // a


#### 逻辑运算符


|运算符|逻辑表达式|描述|实例
|:---:|:---|:------|:------
|and	|x and y	|布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。	|(a and b) 返回 20。
|or	|x or y	|布尔"或"	- 如果 x 是非 0，它返回 x 的值，否则它返回 y 的计算值。	|(a or b) 返回 10。
|not	|not x	|布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。	|not(a and b) 返回 False


### 条件语句
![条件语句](http://www.runoob.com/wp-content/uploads/2013/11/if-condition.jpg)


{% highlight python %}
num = 5     
if num == 3:            # 判断num的值
    print 'boss'        
elif num == 2:
    print 'user'
elif num == 1:
    print 'worker'
elif num < 0:           # 值小于零时输出
    print 'error'
else:
    print 'roadman'     # 条件均不成立时输出
{% endhighlight %}



### 循环语句
- for
![for](http://www.runoob.com/wp-content/uploads/2013/11/python_for_loop.jpg)

{% highlight python %}
for letter in 'Python':     # 第一个实例
   print '当前字母 :', letter
 
fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # 第二个实例
   print '当前水果 :', fruit
 
print "Good bye!"
{% endhighlight %}



- while
![while](http://www.runoob.com/wp-content/uploads/2013/11/python_while_loop.jpg)
![循环](http://www.runoob.com/wp-content/uploads/2013/11/loop-over-python-list-animation.gif)


{% highlight python %}
# continue 和 break 用法
 
i = 1
while i < 10:
    i += 1
    if i%2 > 0:     # 非双数时跳过输出
        continue
    print i         # 输出双数2、4、6、8、10
 
i = 1
while 1:            # 循环条件为1必定成立
    print i         # 输出1~10
    i += 1
    if i > 10:     # 当i大于10时跳出循环
        break
{% endhighlight %}



## 应用案例——DANCE WITH PYTHON
在日常的网络运维和网管系统开发中，有很多环节可以使用Python来解决问题。
![](/assets/biaoyan.jpg)
### 网络编程：影视剧封面图片接口
- 需求背景：某系统呈现IPTV播放量指标时，为了美观需要展示节目封面图，厂家反馈由于电视节目动态更新，无法通过静态方式展示节目封面，实现难度大，无法支撑。
- 需求分析：如：输入"小猪佩奇"，输出封面图，提供一个获取图片的API接口。
![封面图](https://img3.doubanio.com/view/photo/s_ratio_poster/public/p2368873040.jpg)
- 实现方案：这是一个很典型的网络爬虫
    - 首先确定来源：百度？豆瓣！
    - 分析搜索页面参数及搜索结果代码。
    - 使用Flask框架实现REST API
- 源码分享：[Github](https://github.com/lychlov/flask_rest)
{% highlight python %}
# 使用Flask框架构建API访问地址
@app.route('/tv/<tvname>')
def show_tv_image(tvname):
    # show the tv image for  TV
    # 访问豆瓣根据剧名进行搜索
    target = 'https://www.douban.com/search?cat=1002&q=' + tvname
    html = requests.get(target).content.decode('utf-8')
    doc_tree = etree.HTML(html)
    # 截取封面图片链接
    image_links = doc_tree.xpath('//*[@id="content"]/div/div[1]/div[3]/div[2]/div[1]/div[1]/a/img/@src')
    filename = image_links[0].split('/')[-1]
    path_to_img = IMG_STORE + filename
    # 如果曾经下载过图片就从本地获取，否则下载图片并保存
    if not os.path.exists(path_to_img):
        print "New download"
        save_img(image_links[0], filename)
    image = file(IMG_STORE + filename)
    # 返回图片结果
    resp = Response(image, mimetype="image/jpeg")
    return resp
{% endhighlight %}
![效果图](/assets/affect.png)

### 人工智能：利用OCR识别设备串号
- 需求背景：某分公司运维人员需要管理一些板卡，主要信息包含板卡串号、安装位置、时间，人工识别图片中的串号费时费力，使用excel管理不方便。
![串号图片](/assets/source.jpg)
- 需求分析：使用人工智能OCR识别图片串号，建立数据模型，将图片及其他信息关联管理。
- 实现方案：
    - 利用[百度](https://console.bce.baidu.com/ai/?_=1531069792885&fromai=1#/ai/ocr/overview/index)提供的OCR API
    ![识别信息](/assets/recognize.png)
    - 使用Django框架实现ORM数据建模及管理。[站点](http://223.105.3.139:8002/admin/login/?next=/admin/)
- 源码分享：[Github](https://github.com/lychlov/work_site)
{% highlight python %}
# 初始化OCR模块
client = AipOcr(APP_ID, API_KEY, SECRET_KEY)
options = {}
options["language_type"] = "ENG"
image = get_file_content('source.jpg')
""" 以本地图片为识别目标，调用通用文字识别 """
result = client.basicGeneral(image, options=options)
{% endhighlight %}
``` json
{'log_id': 6131613080778703762,
'words_result_num': 2,
'words_result': [
    {'words': 'A PCU2-E'},
    {'words': 'S / N : 1M111600597'}
    ]}
```
- 应用场景：
    - 现场运维人员使用微信发来一张设备串码图，自动识别设备信息，关联呈现设备安装手册，注意事项等，进一步将此次安装结果登记备案。
    - 建立设备生命周期档案，对设备厂家、类型、用途等维度进行分析，甚至预测设备寿命等。
    - 智能抄表、智能自助服务机器人、工单助手等等。
### 告警监控与微信通知

## 获取更多知识：
- [runoob](http://www.runoob.com/python/python-tutorial.html)
- [学习笔记](https://github.com/lijin-THU/notes-python)
