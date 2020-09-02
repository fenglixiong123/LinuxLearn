# RZ SZ命令安装

rz: Receive Zmodem      上传   
sz：Send Zmodem          下载


用途说明：  
* sz:命令是利用ZModem协议来从Linux服务器传送文件到本地，一次可以传送一个或多个文件。
* rz:命令相对应的从本地上传文件到Linux服务器。

## 1.安装GCC环境
如果机器已经安装了gcc则可以忽略此步骤  

yum install gcc

## 2.下载安装包

wget http://www.ohse.de/uwe/releases/lrzsz-0.12.20.tar.gz

## 3.解压安装包

tar zxvf lrzsz-0.12.20.tar.gz

## 4.进入安装路径

cd lrzsz-0.12.20

## 5.配置安装路径

./configure

## 6.编译&安装

make && make install

## 7.创建软连接

上面安装过程默认把lsz和lrz安装到了/usr/local/bin/目录下

cd /usr/local/bin  
1）创建rz的软链接，并命名rz  
ln -s /usr/local/bin/lrz rz  
2）创建sz的软链接，并命名sz  
ln -s /usr/local/bin/lsz sz  

注：软链接类似于Windows系统下的快捷方式，被删除后，不影响原始文件；而硬链接被删除后，原始文件也会被删除。



