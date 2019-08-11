# 配置安装说明

##系统需求

下载

mysql 

nginx

java8 sdk

extjs 5.11

curl

redis server 

ant

maven 

eclipse 

http://wc.mysvc.net/files1554/


##目录结构


开发软件目录c:\wchat-prj 为例

正式软件目录c:\wchat-app 为例


    /wchat-prj
        /bin 工具
        /etc/wx-sec.txt  微信参数文件
        /src   源码
        /src/misc/... 其他资源文件
        /src/web/... web文件
        /src/wchat-server 微信服务
             ...

    /wchat-app
        /bin 工具
        /etc/wx-sec.txt  微信参数文件
        /misc/... 其他资源文件
        /web/...     web文件
        /wchat-server 微信服务
                ...



##1 设置环境

1.1 JAVA环境变量
JAVA_HOME


1.2 软件环境变量

开发
x_wchat_root_dev = c:/wchat-prj 

c:\wchat-prj\bin 加入PATH 

正式

x_wchat_root_p  = c:/wchat-app
c:\wchat-app\bin 加入PATH 



1.3 配置nginx

        location /files {
           add_header Accept-Ranges bytes;
           autoindex on;
           alias  "c:/wchat-prj/files/";
        }        


1.4 安装redis-server

redis-server --service-install redis.windows-service.conf 


1.5 数据库安装

  /misc/mysql/目录

如果第一次安装设置

    mysqld --initialize-insecure
    init-root.sql
  
创建数据库的脚本

    init-db.sql 

 创建table
 
    init-table.sql 
    mg-all-create.sql


1.5 配置wx-sec.txt
n从1开始
[wx-1]
...
[wx-2]
...

    [wx-n]  
    appId=
    appSec=
    appToken=
    callbackHost=
    accessTokenProxy=
    serviceId=
    msgKey=
    appName=
    mchName=
    mchId=
    mchKey=
    mchCert=apiclient_cert.p12

 accessTokenProxy 获取token使用代理服务器,不用为空

1.6 开发配置




2 运行测试


启动nginx

启动mysql

启动redis

启动后台管理

c:\wchat-prj\src\wchat-mgr\run-test.bat 

浏览器http://localhost:8080/

 



####其他

   extjs-doc

	location /ext5doc {
           autoindex on;
           alias  "/extjs-511-docs/";
    }  