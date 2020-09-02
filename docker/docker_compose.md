# docker-compose知识点

### 重新构建和启动镜像
docker-compose up -d				

### 实时查看日志
docker-compose logs --f evo-basic	
### 实时从最后100行开始查看日志		
docker-compose logs -f --tail=100 evo-basic		

### 显示运行容器
docker-compose ps  
### 显示所有容器                               		
docker-compose ps -a                             		
### 启动nignx容器                  		
docker-compose start nginx  
### 停止nignx容器                   		
docker-compose stop nginx 
### 强制停止服务	 
docker-compose kill -s nginx
### 重新启动nginx容器             		 	
docker-compose restart nginx     
### 删除容器（删除前必须关闭容器）            		
docker-compose rm nginx    
### 强制删除容器                   		
docker-compose rm -f nginx  
### 暂停nignx容器                 		
docker-compose pause nginx  
### 恢复ningx容器                		
docker-compose unpause nginx              		
### 重新构建镜像
docker-compose build evo-wes
### 拉取镜像			
docker-compose pull evo-wes			