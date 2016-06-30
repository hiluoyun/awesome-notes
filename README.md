# awesome-notes
this is some awesome notes including lots of links in the internet to setup many development environment


<h4>1.Linux服务器相关环境搭建</h4>
1.开启8080防火墙端口:  A RH-Firewall-1-INPUT -p tcp -m state -m tcp --dport 8080 --state NEW -j ACCEPT  

2.查看防火墙状态:   /etc/init.d/iptables status  
3.编辑防火墙:   vi /etc/sysconfig/iptables   
4.查看端口启动状态:   netstat -nat                 

5.添加环境变量:vi /etc/profile     
6.使环境变量生效:source /etc/profile 

7.查看系统版本:cat /etc/centos-release 

8.重启Apache: service httpd restart 



9.关闭tomcat服务器: /usr/local/tomcat/bin/shutdown.sh 

10.开启tomcat服务器:/usr/local/tomcat/bin/startup.sh 

11.配置tomcat的项目路由:<Context path="/mayi" docBase="${catalina.home}/webapps/mayi/WebRoot" reloadable="true"/> 

12.lamp安装教程：http://blog.csdn.net/xiaokuang513204/article/details/8517562

13.Jdk安装：http://www.cnblogs.com/zhoulf/archive/2013/02/04/2891608.html

14.tomcat安装：http://www.cnblogs.com/zhoulf/archive/2013/02/04/2891633.html

<h4>2.mysql安装卸载，配置相关</h4>

1.mysql重启: /etc/init.d/mysqld restart  
2.卸载mysql:<br>
(1).yum remove mysql*
(2)、查找以前是否装有mysql
	命令：rpm -qa|grep -i mysql
	可以看到mysql的两个包：
	mysql-*..*.RHEL**
	mysqlclient*.RHEL**<br>
(3)、删除mysql
	删除命令：rpm -e --nodeps 包名
	( rpm -ev mysql-*.RHEL* )<br>
(4)、删除老版本mysql的开发头文件和库
	命令：rm -fr /usr/lib/mysql
	rm -fr /usr/include/mysql<br>
	注意：卸载后/var/lib/mysql中的数据及/etc/my.cnf不会删除，如果确定没用后就手工删除
	rm -f /etc/my.cnf
　　	rm -fr /var/lib/mysql

3.更改mysql密码：<br>
mysql > USE mysql;
mysql > delete from user where user=''; 
mysql > UPDATE user SET password = PASSWORD('新密码') WHERE user = 'root'; 
mysql > FLUSH PRIVILEGES;

4.修改mysql字符集：http://www.tuicool.com/articles/6b2Qvm

(1).set names utf8;<br>
(2).vim /etc/my.cnf 追加:<br>
	[client]<br>
	default_character_set=utf8<br>
	[mysql]<br>
	default_character_set=utf8<br>
	[mysqld]<br>
	default_character_set=utf8

5.新建数据库：CREATE DATABASE `test2` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci

6.mysql导入mysql文件：

source /usr/local/tomcat/jiajiao.sql

7.远程连接数据库：

http://www.fantxi.com/blog/archives/enable-remote-access-mysql-centos/


<h4>3.redis配置相关</h4>

1、通过ps -ef|grep redis命令查看Redis进程；<br>
2、开启Redis服务操作通过/etc/init.d/redis_6379 start命令，也可通过（service redis_6379 start）；<br>
3、关闭Redis服务操作通过/etc/init.d/redis_6379 stop命令，也可通过（service redis_6379 stop）；<br>



<h4>4.安装PHP5.5</h4>

yum remove php  php-bcmath php-cli php-common  php-devel php-fpm    php-gd php-imap  php-ldap php-mbstring php-mcrypt php-mysql   php-odbc   php-pdo   php-pear  php-pecl-igbinary  php-xml php-xmlrpc
 
rpm -Uvh http://mirror.webtatic.com/yum/el6/latest.rpm
  
yum install php55w  php55w-bcmath php55w-cli php55w-common  php55w-devel php55w-fpm    php55w-gd php55w-imap  php55w-ldap php55w-mbstring php55w-mcrypt php55w-mysql   php55w-odbc   php55w-pdo   php55w-pear  php55w-pecl-igbinary  php55w-xml php55w-xmlrpc php55w-opcache php55w-intl php55w-pecl-memcache

重启centos：
shutdown -r now 立刻重启(root用户使用)

正则表达式验证：
http://mp.weixin.qq.com/s?__biz=MjM5ODI5Njc2MA==&mid=2655807432&idx=1&sn=6ee6af53f1fbaee19960446afba1b575&scene=0

<h4>5.git 教程相关</h4>
1.http://www.yiibai.com/git/git_pull.html
2.30 分钟 git 命令入门:<br>
http://mp.weixin.qq.com/s?__biz=MjM5OTA1MDUyMA==&mid=2655436216&idx=1&sn=07cb1ceab6cf16fdf311d801739563b3&scene=23&srcid=0629eCqdpgkfEhljVPB6Iork#rd
