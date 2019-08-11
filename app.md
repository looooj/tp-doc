# app设置

1  配置微信环境

设置消息

http://域名/wc-msg/p/1

网页授权域名

JS接口安全域名


2 配置一个测试活动

2.1 红包活动配置
    选择公众号
    配置初始方案

2.2 红包活动管理
    生成数据,启动

3 配置一个测试菜单

辅助工具->公众号菜单设置 
     选择菜单模板


## 附录
代理软件 https://github.com/snail007/goproxy 使用说明


服务器的地址公网IP是123.123.123.123为例

生成key

    proxy keygen -C proxy


服务器运行

    proxy bridge -p ":9088" -C proxy.crt -K proxy.key --daemon

    proxy server -r ":9089@:8082" -P "127.0.0.1:9088" -C proxy.crt -K proxy.key --daemon


个人电脑

    proxy client -P "123.123.123.123:9088" -C proxy.crt -K proxy.key --deamon


访问 123.123.123.123:9089 等于访问个人电脑的8082


服务器http代理 用于白名单

    proxy http -t tcp -p "0.0.0.0:9078" --deamon




