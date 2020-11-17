## 1. nginx 安装

Ubuntu下：

```
sudo apt-get install nginx
```

检查一下nginx的版本，看下是否安装成功

```
nginx -v
```

## 2. nginx配置

进入nginx的目录下

```
cd /etc/nginx/
```

进入到conf.d文件夹，新建一个命名为xxx.conf的配置文件

```
cd conf.d
sudo vim xxx.conf
```

文件配置如下：

```
server {
    # 待设置的端口和地址
    listen xxxx;
    server_name xx.xx.xx.xx;
    
    location / {
        #源地址和端口
        proxy_pass http://xx.xx.xx.xx:xxxx;
        proxy_redirect off; 
    }
}
```

## 3. 启动服务

写完配置文件然后开始运行

```
sudo nginx -t
nginx -c /etc/nginx/nginx.conf
nginx -s reload
```

## 4. 关闭服务

```
nginx -s stop
```

