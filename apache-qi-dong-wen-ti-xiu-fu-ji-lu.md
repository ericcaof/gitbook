# apache 启动问题修复记录

最近在一台云服务器上更新了一个静态html目录,重启httpd后，总是保持 启动错误

错误日志:

 \[Tue Jan 08 17:56:34 2019\] \[error\] \(2\)No such file or directory: could not open transfer log file /data/www/username.com/logs/access.log. Unable to open logs 

\[Tue Jan 08 17:59:43 2019\] \[error\] \(22\)Invalid argument: Could not set permissions on ssl\_mutex; check User and Group directives

第一个错误解决: 

mkdir -p /data/www/username.com/logs/

touch /data/www/username.com/logs/access.log

第二个错误：Could not set permissions on ssl\_mutex 却怎么也修复不了 google baidu都找了 但是解决不了

后面试着用 apachectl start 竟然启动成功

停止后 再用service httpd start 启动还是失败 报错 

用apachectl start 启动成



