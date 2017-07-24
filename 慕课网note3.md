# Selenium

[官网](http://www.seleniumhq.org/)

[Selenium + Python API](http://selenium-python.readthedocs.io/api.html)

### 安装
> pip install selenium



1. intro. selenium python interface api
2. 模拟登录知乎, 微博, OSChina
	* 使用time的sleep 避免因未加载完毕而执行登录的报错 
3. 使用JavaScript下拉加载
4. intro. 微博开放平台 爬取量不大的时候使用, 注意限速



### 课程2

* 设置chromedriver不加载图片 (加速界面加载)


### phantomjs, 无界面浏览器, 缺点 多进程下phantomjs性能下降严重

[Phantomjs官网](http://phantomjs.org/)


### 课程3

* 将selenium集成到scrapy中
* 在middlewares中自定义类JSPageMiddleware
	* 自定义类JSPageMiddlewar(注意使用htmlresponse()方法返回改写下载中间件)
	* 在setting中的Downloader middlewear中设置自定义配置

*　设置爬取后关闭chrome ☆☆☆ 复杂 难点!!!☆☆☆
	
### 使用以上操作 将selenium集成到scrapy中会降低性能, 该操作为同步操作, 而scrapy底层使用twisted为异步操作. 可以通过改写downloader middleware进行改写为异步操作 需要熟悉scrapy规范和twisted.

> 在github上有开源框架 搜索scrapy downloader


### 课程4 <chrome需要界面, 本节介绍使用无界面环境的框架>

* 无界面运行chrome(在windows下报错, 只适用于linux)

> pip install pyvirtualdisplay

* scrapy-splash (针对动态网站, 自己运行server通过http, 类似phantomjs 但容易被网站定义为爬虫而禁止, 支持分布式)
* selenium grim (类似splash, 采用分布式)
* splinter 操控浏览器的解决方案 类似selenium

####建议使用chrome 稳定性最好




### 课程5 scrapy的暂停和重启

### 课程6 url去重

* dupefilter.py