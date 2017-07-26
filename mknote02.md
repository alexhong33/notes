### 第七章
* section 1
	* Scrapy 架构解析
* Section 2 
	* User-Agent 解析
	* 设置随即取UA
	* fake_useragent		 
	* scrapy-proxies
	* scrapy-crawlera 动态IP配置 官网提供 收费的话建议使用
	

#### 最好限速爬虫 珍惜自己的IP 代理速度更慢

* Section 3
	* 验证码识别方法
	* 编码实现(tesseract-ocr) (开发难度大, 识别略低, 不建议使用)
	* 在线打码 (代码识别技术)
	* 人工打码 

* Section 4
	* Scrapy的配置
	* cookie_enable
	* download_delay
	* autothrottle_enabled 自动限速扩张
	* custom_settings 使用 自定义设置

* Section 5
	* 自己写 动态设置IP设置
	* 框架1 scrapy proxies
	* 框架2 scrapy crawlera
	* Tor 洋葱网络 使用VPN 经过Tor 匿踪 稳定性>代理
	
1. 无状态请求
2. 有状态请求

#### 常见httpcode
* 200 : 请求被成功处理
* 301/302 : 永久性重定向/临时性重定向
* 403 : 没有权限访问
* 404 : 表示没有对应的资源
* 500 : 服务器错误
* 503 : 服务器停机或正在维护


#### 爬虫策略

1. User-agent模拟firefox, 获取ip代理
2. 注册账号, 每次请求带cookie或者token
3. 注册多个账号, 多个账号联合爬取
4. 模仿人请求, 限制请求速度
5. 通过各种手段识别验证码
6. 通过selenium和phantomjs完全模拟浏览器操作


#### 反爬虫策略

1. 监控发现某个时间段访问剧增, ip相同, user-agent是python,直接限制访问(不能封ip)
2. 发现ip变化, 直接要求登录才能访问
3. 健全账号体系, A只能访问好友的信息
4. 请求过于频繁, 进一步加剧ip访问频率限制
5. 弹出验证码, 让识别验证码
6.  * 增加动态网站, 数据通过js动态加载, 增加网络分析复杂
	* 发现大量请求只请求html,不请求image和css以及js
	 
