## document

### 安装

- ubuntu安装：`curl -s https://get.docker.io/ubuntu/ | sudo sh`


### 镜像管理

- docker images：列出本地所有镜像
- docker search <IMAGE_ID/NAME>：查找image
- docker pull <IMAGE_ID>：下载image
- docker push <IMAGE_ID>：上传image
- docker rmi <IMAGE_ID>：删除image

### 容器管理

######docker run -i -t <IMAGE_ID> /bin/bash：

- -i：标准输入给容器    
- -t：分配一个虚拟终端    
- /bin/bash：执行bash脚本
- -d：以守护进程方式运行（后台）
- -P：默认匹配docker容器的5000端口号到宿主机的49153 to 65535端口
- -p <HOT_PORT>:<CONTAINER_PORT>：指定端口号
- -name： 指定容器的名称
- --rm：退出时删除容器

######docker stop <CONTAINER_ID>：停止container

######docker start <CONTAINER_ID>：重新启动container

######docker ps - Lists containers.

- -l：显示最后启动的容器
- -a：同时显示停止的容器，默认只显示启动状态

######docker attach <CONTAINER_ID> 连接到启动的容器

######docker logs <CONTAINER_ID>  : 输出容器日志

- -f：实时输出

###### docker cp <CONTAINER_ID>:path hostpath：复制容器内的文件到宿主机目录上

###### docker rm <CONTAINER_ID>：删除container

###### docker rm ``docker ps -a -q` `：删除所有容器

###### docker kill ``docker ps -q` `

###### docker rmi ``docker images -q -a` `

###### docker images|grep \<none\>|awk '{print $3}' | xargs docker rmi     删除所有标签为none的镜像：

###### docker wait <CONTAINER_ID>：阻塞对容器的其他调用方法，直到容器停止后退出

###### docker top <CONTAINER_ID>：查看容器中运行的进程

###### docker diff <CONTAINER_ID>：查看容器中的变化

###### docker inspect <CONTAINER_ID>：查看容器详细信息（输出为Json）

- -f：查找特定信息，如
`docker inspect -f - '{{ .NetworkSettings.IPAddress }}'
      docker commit -m "comment" -a "author" <CONTAINER_ID>  ouruser/imagename:tag`

###### docker extc -it <CONTAINER> <COMMAND>：在容器里执行命令，并输出结果











