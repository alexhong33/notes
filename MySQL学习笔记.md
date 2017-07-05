# Day01
1. 逻辑删除


### 数据库

* 创建数据库
	* create database 数据库名 charset=utf8;
	

* 删除数据库
	* drop database 数据库名;

* 切换数据库
	* use 数据库名;

* 查看当前选择的数据库
	* select database();

* 显示当前数据库
	* show databases;  
	

### Table的操作

* 查看表结构　
	* desc students;
　
* 创建表
	* auto_increment 表示自动增长  
	
>		create table students(
		id int auto_increment primary key,
		name varchar(10) not null
		);

* 修改表

##### 注意-数据存在的时候, 修改表结构, 容易报错!

三种修改方式 
add|change|drop


> alter table students2 add isDelete bit default 0; 

* 删除表

##### 注意 此为物理删除

drop table 表名;

* 更改表名

> rename table 原表名 to 新表名;


* 查看表的创建语句

> show create table students

		create table students(
		id int auto_increment primary key not null,
		name varchar(10) not null,
		birthday datetime,
		gender bit default 1,
		isDelete bit default 0
		);







# Day02


### 数据操作

#### 查询
> select * from 表名


#### 添加
* 全列插入
>insert into 表名 values(0, 'sona', 1, '2018-1-1');  

* 部分插入
>insert into 表名(name) values('Hasaki');  

* 同时插入多条数据
>insert into 表名(gender,name) values(1, "Talon");  

>insert into 表名(name) values('Annie'),('Zed'),('Ali');


#### 修改
>update 表名 set 列1=值1 where 条件

>update 表名 set birthday='2017-1-1' where id=2

>update 表名 set gender=0,birthday='2017-2-2' where id=6


#### 删除
* 物理删除
> delete from 表名 where id=4

* 逻辑删除
> update 表名 set isDelete=1 where id=3;



# 查询

## 条件

### 比较运算符

* 等于 =
* 大于 >
* 大于等于 >=
* 小于 <
* 小于等于 <=
* 不等于 != 或者 <>

> select * from students2 where id>1 

### 逻辑运算符

*　and
*　or
*　not

> select * from students2 where id>1 and gender=0;

### 模糊查询

* like
* %表示任意多个任意字符
* _表示一个任意字符

> select * from students2 where name like 'Ali%';


### 范围查询

* in 表示在一个非连续的范围内
* 查询编号是1, 3,8的学生
> select * from students where id in(1,3,8);

* between...and... 表示在一个连续的范围内
* 查询编号是3-8的学生
> select * from students where id between 3 and 8;

* 查询学号是3-8的男学生
> select * from students where id between 3 and 8 and gender=1;

### 空判断

* 注意: null 和 ' ' 的区别
	* null表示空 不指向任何事物
	* ' ' 表示空字符串

* 查询地址为NULL的学生

> select * from students2 where hometown is null;

* 查询地址为非NULL的学生

> select * from students2 where hometown is not null;

* 查询填写了地址的女生

> select * from students where hometown is not null and gender=0;


### 优先级

* 小括号 > not > 比较运算符 > 逻辑运算符
* and 比 or 先运算, 如果同时出现并希望先算or, 需要结合()使用


# 5个聚合函数

* count(*)表示计算总行数 
* 查询学生总数

> select count(*) from students2;

* max(列)表示求此列的最大值
* 查询女生的编号最大值

> select max(id) from students2 where gender=0;

* min(列)表示求此列的最小值
* 查询为删除的学生最小编号

> select min(id) from students2 where isdelete=0;

* sum(列)表示求此列的和
* 查询男生的编号之和

> select sum(id) from students2 where gender=1;

* avg(列)表示求此列的平均值
* 查询为删除女生的编号平均值
* select avg(id) from students2 where isdelete=0 and gender=0;


# 子查询
查找未删除的最小编号的学生信息
> select * from students2 where id=(select min(id) from students2 where isdelete=0);



# 分组

* 查询男女总数

> select gender as 性别,count(*) from students group by gender;


## where 对比 having

* where是对from后面指定的表进行数据筛选, 属于对原始数据的筛选
* having是对group by的结果进行筛选


#### 查询男生总人数

* 方案1:
> select count(*) from students2 where gender=1;

* 方案2:
> select gender as 性别,count(*) from students group by gender having gender=1;


# 排序

* asc 从小到大排序, 升序
* desc 从大到小排序, 降序

>　select * from 表名 order by 列1 asc|desc, 列2 asc|desc, ..

#### 将行数据按照列1进行排序, 如果某些行列1的值相同, 则按照列2排序, 以此类推.

* 查询未删除男学生信息
> select * from students where gender=1 and isdelete=0 order by id desc;

