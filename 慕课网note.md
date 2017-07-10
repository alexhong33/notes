# Chapter3 基础知识回顾 section 3-4 正则表达式

## [正则表达式 菜鸟教程](http://www.runoob.com/regexp/regexp-syntax.html)

* ? 懒惰模式
* 星号 * 出现0-N次 (匹配 * 字符，使用 单反斜杠+星号\\*)
* 加好 + 出现至少1次-N次 (匹配 + 字符，使用单反斜杠+加好 \\+)
* . 任意字符
* ^ 从前端开始匹配
* $ 从末端开始匹配
* {1} 出现1次
* {2,} 出现2次以上
* {3, 5} 出现大于3次 最多5次
* | 或  

		line = "boobby123"
		regex_str = "((bobby|boobby)123)"
		match_obj = re.match(regex_str, line)
		if match_obj:
			print(match_obj.group(1))
	
		输出: bobby123
		先匹配了小括号 然后匹配大括号

* [abcd] 中括号中任意一个字符
* [0-9]{9} 0-9之间的数 出现9次
* [^1]{9} 不等于1 出现9次
* [.*] .代表. *代表*
* \s 匹配任何空白字符 等价于 [ \f\n\r\t\v]
* \S 匹配任何非空白字符 等价于 [^ \f\n\r\t\v]
* \w 匹配包括下划线的任何单词字符 等价于'[A-Za-z0-9_]'
* \W 匹配任何非单词字符。等价于 '[^A-Za-z0-9_]'
* [\u4E00-\u9FA5] 匹配utf8文字  

		regex_str = ".*?([\u4E00-\u9FA5]+大学)"

* \d 数字
		line = "2001年的第一场雪"
		regex_str = ".*?(\d+)年"
		输出2001


		line = "XXX出生于2001年6月"
		line = "XXX出生于2001/6/1"
		line = "XXX出生于2001-6-1"
		line = "XXX出生于2001-06-01"
		line = "XXX出生于2001-06"
		
		regex_str = ".*出生于(\d{4}[年/-]\d{1,2}([月/-]\d{1,2}|[月/-]$|$))"



---
##### 华丽的分割线
---

# Chapter3 基础知识回顾 Section5-6 Unicode, UTF8, ASCII, 深度优先和广度优先算法, URL去重策略

8个bit = 1个字节 (255)

* 网站的树结构
* 深度优先算法和实现
* 广度优先算法和实现


### 爬虫去重策略
1. 将访问过的url保存到数据库中
2. 将访问过的url保存到set中, 只需要o(1)的代价就可以查询url 100000000(1亿) * 2byte(16位) * 50个字符/1024/1024/1024=9G
3. url经过md5(128bit 16byte)等方法哈希后保存到set中 =3G
4. 用bitmap方法,将访问过的url通过hash函数映射到某一位 
5. bloomfilter方法对bitmap进行改进,多重hash函数降低冲突 =12M


---
##### 华丽的分割线
---


# Chapter4 初识Scrapy
## Section 1-3
## XPath语法

### part1
* article
	* 选取所有article元素的所有子节点
* /article
	* 选取根元素article	
* article/a
	* 选取所有属于article的子元素的a元素
* //div
	* 选取所有div子元素(无论出现在文档任何地方)
* article//div
	* 选取所有属于article元素的后代的div元素, 不管它出现在article之下的任何位置
* //@class
	* 选取所有名为class的属性  


### Part2
* /article/div[1]  
	* 选取属于article子元素的第一个div元素
* /article/div[last()]  
	* 选取属于article子元素的最后一个div元素 
* /article/div[last()-1]
	* 选取属于article子元素的倒数第二个div元素
* //div[@lang]
	* 选取所有拥有lang属性的div元素
* //div[@lang='eng']
	* 选取所有lang属性为eng的div元素

### Part3
* /div/* 
	* 选取属于div元素的所有子节点
* //*
	* 选取所有元素
* //div[@*]
	* 选取所有带属性的title元素
* /div/a | //div/p
	* 选取所有div元素的a和p元素
* //span | //ul
	* 选取文档中的span和ul元素
* article/div/p | //span
	* 选取所有属于article元素的div元素的p元素  以及文档中所有的span元素     



## Section 4-5

## 快速测试
1. scrapy shell http://blog.jobbole.com/110287/
2. title = response.xpath('//*[@id="post-111535"]/div[1]/h1/text()')
3. title
4. title.extract()

#### 去除日期标签内的回车换行符
1. 使用strip()去除空格
2. 使用replace(".", "")去除点


#### 内置函数contain(属性, 值)  

* 寻找一个span 属性中包含vote-post-up字段  转化为int类型
	*	int(response.xpath("//span[contains(@class, 'vote-post-up')]/h10/text()").extract()[0])


## Section 6-7

### CSS 选择器

### Part 1

* *
	* 选择所有节点
* <注意是#号> #container
	* 选择id为container的节点
* .container
	* 选取所有class包含container的节点
* li a
	* 选取所有li节点下的所有a节点
* ul+p
	* 选择ul后面的第一个p元素 <注意ul,p为兄弟元素>
* div#container>ul
	* 选取id为container的div的第一个ul子元素
     
### Part 2

* ul~p
	* 选取与ul相邻的所有p元素
* a[title]
	* 选取所有有title属性的a元素
* a[href="http://jobbole.com"]
	* 选取所有href属性为http://jobbole.com值的a元素
* a[href*="jobbole"]
	* 选取所有href属性包含jobbole的a元素	    
* a[href^="http"]
	* 选取所有href属性值以http开头的a元素
* a[href$=".jpg"]
	* 选取所有href属性值以.jpg结尾的a元素
* input[type=radio]:checked
	* 选择选中的radio的元素  

### Part 3

* div:not(#container)
	* 选取所有id非container的div属性
* li:nth-child(3)
	* 选取第三个li元素
* tr:nth-child(2n)
	* 第偶数个tr 



---
##### 华丽的分割线
---  

## Section 7-15

1. 异步机制MysqlTwistedPipeLine
2. 同步机制MysqlPipeline
3. 自定义图片输出ArticleImagePipeLine
4. 自定义导出Json格式
5. scrapy JsonExporter库导出Json格式


## Section 16

1. 使用ItemLoader()简化代码
2. 重写ArticleItemLoader
	default_output_processor = TakeFirst()
3. 调试items.py中的新设定




---
##### 华丽的分割线
---


# Chapter5 

1. Session与Cookie的区别  
	* 无状态请求
	* 有状态请求
2. Cookie,存储在本地浏览器当中
3. Session,存储在服务器中
	* 自动登录机制
	* 通过服务器的数据库, 查询cookie的ID 实现自动登录


###常见httpcode

200		:	请求被成功处理
301/302 :	永久性重定向/临时性重定向
403		:	没有权限访问
404		:	表示没有对应的资源
500		:	服务器错误
503			服务器停机或正在维护


###Requests
[Requests文档](http://cn.python-requests.org/zh_CN/latest/user/quickstart.html)


