## Ubuntu下的MySQL

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'admin' WITH GRANT OPTION;  

* 检测是否已经安装MySQL
> sudo netstat -tap | grep mysql

* 如果没有安装, 则安装MySQL
> sudo apt-get install mysql-server mysql-client

* 登录MySQL
> mysql -uroot -p

* 启动MySQL服务
> sudo start mysql

* 停止MySQL服务
> sudo stop mysql

* 修改MySQL管理员密码
> sudo mysqladmin -u root password newpassword


## Mysql授权
如果你想允许用户root从ip为192.168.1.6(或任意主机'%')的主机连接到mysql服务器，并使用admin作为密码
> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'admin' WITH GRANT OPTION;  
>    
> FLUSH   PRIVILEGES;  