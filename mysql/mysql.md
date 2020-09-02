
# Mysql相关知识点

mysql相关操作

## 导出数据库数据

mysqldump -h 127.0.0.1 -uroot -p --databases auth  evo_basic  evo_console evo_rcs notification > 20200803.sql

## 数据库线程相关

### 查看数据库连接线程数
show status like 'Threads%'	
			
* Threads_connected				这个数值指的是打开的连接数  
* Threads_running					这个数值指的是激活的连接数，这个数值一般远低于connected数值

### 查询数据库当前设置的最大连接数
show variables like '%max_connections%'	
### 输出结果显示了有哪些线程在运行	
show processlist		
### 查询睡眠线程时间			
show global variables like'wait_timeout'	
### 设置睡眠线程时间	
set global wait_timeout=60				

