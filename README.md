# Summary
# ERP线上环境一键部署脚本

操作说明
--
1. 将devenv.zip 上传到目标服务区任意目录 建议放置到剩余空间比较大的目录
2.  将devenv.zip 解压缩 指令: unzip devenv.zip   如果执行报错 可能未安装unzip  执行 yum -y install unzip zip
3. 将进入解压缩得到的目录 devenv, 将systeminit.sh文件设置为可执行  指令: chmod 700 systeminit.sh
4. 执行 systeminit.sh  指令 ./systeminit.sh
5. 如需执行部分，请先在systeminit.sh 注释不需要执行子模块sh文件

目录说明
--
##### 1. JAVA目录
	/home/sanyuanse/java/
	java -version;
	默认设置环境变量为jdk1.8
	环境变量设置/etc/profile
##### 2. NGINX目录
	/home/sanyuanse/nginx
	nginx默认已经启动 
	查看ps -ef|grep nginx
	启动 ./nginx 
	停止 killall nginx  
	conf /home/sanyuanse/nginx/conf/nginx.conf
##### 3. TOMCAT目录
	/home/sanyuanse/tomcat
	/home/sanyuanse/webapp7 ##tomcat7 application
	/home/sanyuanse/webapp8 ##tomcat8 application
	/home/sanyuanse/webapp9 ##tomcat9 application
	默认启动tomcat8,如需启动其他tomcat 请修改tomcat的server.xml端口设置 以防端口冲突
	查看 ps -ef|grep tomcat
##### 4. MYSQL目录
	/home/sanyuanse/mysql/mysql5/
	操作
	service mysql5 start|stop|restart;
	mysql当前端口设置为3309
	当前mysql为初始化账号信息
	mysql -uroot -p #默认密码为空 直接回车即可
	修改密码
	进入mysql shell后
	use mysql;
	update Password=password("新密码");
	update user set Password=password("新密码") where User='root';
	清理空账号
	delete from user where User='';
	flush privileges;
##### 5. REDIS目录
	/home/sanyuanse/redis
    端口6379 
	默认连接密码:testest*&&* 安装后请修改 
	操作 
	service redis start|stop|restart
##### 6. MONGODB目录
	/home/sanyuanse/mongodb
	端口20717
	操作 
	service mongod start|stop|restart
