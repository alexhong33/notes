## Ubuntu下的MySQL

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


