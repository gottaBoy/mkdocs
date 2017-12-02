# 服务器运行dokcer jenkins容器:
 `sudo docker run -d --name myjenkins -p 4243:8080 -p 50000:50000 -v /var/jenkins:/var/jenkins_home jenkins:latest`
 `sudo docker run -d --name jenkins_gottaboy -u 0 -p 4243:8080 -v /var/jenkins:/var/jenkins_home jenkins:latest`
 # 命令
 * `docker rm -f jenkins`
 * `docker run -d --name myjenkins -p 4243:8080 -p 50000:50000 -v /var/jenkins:/var/jenkins_home jenkins:latest`
 * `docker logs jenkins` #日志
 * `docker run -ti --rm --entrypoint="/bin/bash" jenkins -c "whoami && id"`
 * `docker run -ti --rm --entrypoint="/bin/bash" jenkins -c "ls -la /var/jenkins_home"`
 * `docker run -ti --rm -v /var/jenkins:/var/jenkins_home --entrypoint="/bin/bash" jenkins -c "ls -la /var/jenkins_home"` 
 * `ls -la jenkins`
 * `sudo chown -R 1000 jenkins`
 * `docker start myjenkins`
 
 # 谈谈 Docker Volume 之权限管理（一）
 [Docker Volume](https://yq.aliyun.com/articles/53990)
 [权限管理](http://blog.csdn.net/yulei_qq/article/details/53228601)
 
 # Docker+Jenkins+Gitlab搭建Nodejs自动化测试实践
 [Docker+Jenkins+Gitlab](http://blog.csdn.net/jiangyongc5606/article/details/43484609)
 
 # 使用Git来对Jenkins项目设定做版本控制
 [版本控制](http://www.it165.net/admin/html/201304/1083.html)
 
 # 一步一步打造jenkins+docker+nodejs项目的自动部署环境
 [jenkins+docker+nodejs](http://www.jianshu.com/p/052a2401595a)
 
 # 持续集成 centos＋Jenkins＋maven＋nginx，完整搭建持续集成小结
 [centos＋Jenkins＋maven＋nginx](https://testerhome.com/topics/4043)
 
 # Docker 以 docker 方式运行 jenkins
 [以 docker 方式运行 jenkins](https://testerhome.com/topics/5798)
 
 # 基于Docker版jenkins的持续集成环境搭建(二)
 [持续集成](http://www.jianshu.com/p/33896fdaad77)
 [hello_world](https://gitee.com/ryzecode/HelloWorld_Node)
 
 # Linux配置SSH公钥认证与Jenkins远程登录进行自动发布
 [SSH公钥认证与Jenkins远程登录](https://www.cnblogs.com/jager/p/5986563.html)
 
 
 # ssh key
 `ssh-keygen -t rsa`  获取key
# Ubuntu环境下SSH的安装及使用
[Ubuntu环境下SSH的安装及使用](http://blog.csdn.net/netwalk/article/details/12952051)
# Free Software to Search and Analyze All Your Log Data
 `https://www.splunk.com/`
 https://www.splunk.com/goto/Splunk_Log_Management?utm_source=baiduSEM&utm_medium=Log&utm_campaign=Viewer&utm_term=%E6%9F%A5%E7%9C%8B%E6%97%A5%E5%BF%97&utm_content=&a=401623219&b=8064788&c=20103395&d=0&e=%ekid!&f=201763115&g=4055020&h=%g&i=%k[start_string]!?&j=AMsySZbJTvHWaE9ldKqLK9pO-5LL&k=1286093531&l=%p[start_string]!?&m=N386403.2754002-S