# 安装 Redis5.0.3

## 1.安装gcc

yum install gcc

## 2.下载安装包

wget http://download.redis.io/releases/redis‐5.0.3.tar.gz  

## 3.解压安装包

tar xzf redis‐5.0.3.tar.gz

## 4.编译与安装

cd redis‐5.0.3  
make

## 5.安装

* 本次直接安装：  
make install 

~~~
redis默认安装路径  
/usr/local/bin/redis-cli  
/usr/local/bin/redis-server
~~~

* 可以尝试下面方式，给redis安装设置路径：  
make install prefix=/usr/local/redis

## 6.启动并指定配置文件

移动配置文件:
 
mv /opt/software/redis-5.0.3/redis.conf /usr/local/etc   
注意：要使用后台启动，所以修改redis.conf里的daemonize改为yes

启动：  
/usr/local/bin/redis-server /usr/local/etc/redis.conf

## 7.验证是否启动成功

ps -ef|grep redis

## 8.进入redis客户端

cd /usr/local/bin/
./redis-cli

## 9.退出redis服务

退出客户端：

quit

退出服务：
* kill -9 pid
* /usr/local/redis/bin/redis-cli shutdown

## Redis开机启动

vim /etc/rc.local
加入
/usr/local/redis/bin/redis-server /usr/local/redis/etc/redis-conf

## Windows下面访问

注意：由于redis有保护模式，如果要在windows上面用distop manager来远程链接redis就需要修改几个地方：

(1)注释以下绑定的主机地址  

bind 127.0.0.1 

(2)解除保护模式

protected-mode:no

(3)设置后台启动

daemonize ：yes

(4)开放6379端口

service iptables stop

## 附录
/usr/local/redis/bin目录下的几个关键文件：  
* redis-benchmark：redis性能测试工具  
* redis-check-aof：检查aof日志的工具  
* redis-check-dump：检查rdb日志的工具  
* redis-server：redis服务进程  
* redis-cli：连接用的客户端  

## 配置介绍

conf 配置项介绍

* daemonize：如需要在后台运行，把该项的值改为yes
* pdifile：把pid文件放在/var/run/redis.pid，可以配置到其他地址
* bind：指定redis只接收来自该IP的请求，如果不设置，那么将处理所有请求，在生产环节中最好设置该项
* port：监听端口，默认为6379
* timeout：设置客户端连接时的超时时间，单位为秒
* loglevel：等级分为4级，debug，revbose，notice和warning。生产环境下一般开启notice
* logfile：配置log文件地址，默认使用标准输出，即打印在命令行终端的端口上
* database：设置数据库的个数，默认使用的数据库是0
* save：设置redis进行数据库镜像的频率
* rdbcompression：在进行镜像备份时，是否进行压缩
* dbfilename：镜像备份文件的文件名
* dir：数据库镜像备份的文件放置的路径
* slaveof：设置该数据库为其他数据库的从数据库
* masterauth：当主数据库连接需要密码验证时，在这里设定
* requirepass：设置客户端连接后进行任何其他指定前需要使用的密码
* maxclients：限制同时连接的客户端数量
* maxmemory：设置redis能够使用的最大内存
* appendonly：开启appendonly模式后，redis会把每一次所接收到的写操作都追加到appendonly.aof文件中，当redis重新启动时，会从该文件恢复出之前的状态
* appendfsync：设置appendonly.aof文件进行同步的频率
* vm_enabled：是否开启虚拟内存支持
* vm_swap_file：设置虚拟内存的交换文件的路径
* vm_max_momery：设置开启虚拟内存后，redis将使用的最大物理内存的大小，默认为0
* vm_page_size：设置虚拟内存页的大小
* vm_pages：设置交换文件的总的page数量
* vm_max_thrrads：设置vm IO同时使用的线程数量
