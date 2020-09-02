# Docker操作手册

### 启动docker服务
systemctl start docker.service		
### 停止docker服务		
systemctl stop docker.service	
### 重启docker服务			
systemctl restart docker.service			

### 查看容器日志
docker logs -f --tail=100 evo-basic			

### 启动docker容器
docker startcontainerid				
### 重启docker容器
docker restart containerid				
### 关闭docker容器
docker stop containerid				
### 删除docker容器
docker rm containerid				
### 强制删除docker容器
docker rm -f containerid				
### 查看容器端口
docker port mysql-5.6				

### 启动docker镜像
docker run imageid	
### 删除docker镜像				
docker rmi imgid					

## 进入容器内部
docker exec -it evo-interface /bin/bash		
## 从容器中复制文件出来
docker cp evo-station:opt/evo-station/evo-station.jar /opt/docker

## 防止docker卡死

设置超时时间  
~~~
vim /etc/profile
export DOCKER_CLIENT_TIMEOUT=500
export COMPOSE_HTTP_TIMEOUT=500
source /etc/profile
~~~