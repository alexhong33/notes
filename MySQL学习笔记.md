###Class-1
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