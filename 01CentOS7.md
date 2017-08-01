# CentOS7的学习笔记

---
## 02-RHEL7-Linux控制台使用和shell命令执行  

#### 控制台
* tty1 图形化界面
* ctrl+fn+alt+f2 字符界面
* alt+f1 图形界面

#### pty-控制台的使用
* 虚拟终端pty(pseudo-tty),我们远程telnet到主机或使用xshell时也需要一个终端交互

#### pts/ptmx-控制台的使用
* ctrl+shift+T 新建伪终端
* Alt+数字键 终端切换
* Alt+F4 关闭所有终端
* 使用who am i 查询当前终端对应的pts

* ctrl+shift+(+) 放大终端
* ctrl+(-) 缩小终端


#### Shell 命令格式
*　命令字　［选项］　［参数］
*　命令字：　具体执行的命令
*　选项：　匹配的条件
*　参数：　命令处理的对象

#### Shell 命令使用
* pwd 查看当前位置
* cd 切换目录
	* cd + 指定目录
	* cd. 当前目录
	* cd.. 上级目录
* ls 查看目录
	* ls -l 显示详细信息
	* ls -a 显示隐藏目录
	* ls -d 显示当前目录  

* cat 查看文件


---
## 03-RHEL7-Linux系统维护管理命令使用

本节 需要自行再查看[菜鸟教程](http://www.runoob.com/linux/linux-tutorial.html)

* date 查看日期,设置日期(超级用户)
* clear 清屏
* man 查看帮助信息
* who 当前用户
* w 当前用户
* uname 操作系统信息
* uptime 输出系统任务队列信息
* last 输出上次和过去系统登录的信息
* dmesg 显示开机信息
* free 显示系统内存状态





---
## 04-RHEL7-Linux文本编辑器使用

#### Vim编辑器
* vi编辑器支持编辑模式和命令模式
	* 编辑模式对文本进行编辑
	* 命令模式对文件进行操作
* 从编辑模式 → 命令模式 ESC
* 从命令模式 → 编辑模式 "A","a","O","o","I","i",

[Vim基础命令](http://www.runoob.com/linux/linux-vim.html)

* 安装vim
* >  yum -y install vim
* 查看vim版本
* > rpm -qf `which vim`


---
## 05-RHEL7-Linux远程连接工具使用
1. Xshell的安装
2. Xftp