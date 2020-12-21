## Ubuntu 常用命令备忘
### WiFi相关命令
开启WiFi：

```shell
ifconfig wlan0 up
```

关闭wifi：

``` shell
ifconfig wlan0 down
```

查找网络：

```shell
iw dev wlan0 scan
```

初次连接：

```shell
touch /etc/my_wpa_supplicant.conf
```

```txt
ctrl_interface=/var/run/wpa_supplicant
network={
    ssid="TP-LINK_22E1D2"
    psk="密码"
}
```

设置WiFi上网：

```shell
wpa_supplicant -B -i wlan0 -c /etc/my_wpa_supplicant.conf
ifconfig wlan0 192.168.1.132
route add default gw 192.168.1.1 dev wlan0
```

### 图形化docker  (samba jellyfin)

```shell
docker pull portainer/portainer
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock --restart=always --name prtainer portainer/portainer

docker run -d -p 8096:8096 -v /jellyfin/config:/config -v /root/data/downloads:/media jellyfin/jellyfin
```

### 开机自启动

```shell
vim /lib/systemd/system/rc-local.service
# 在文件尾部加入
[Install]
WantedBy=multi-user.target
Alias=rc-local.service
# 然后在 /etc/ 目录下创建 rc.local 
vim /etc/rc.local
# 在里面写上开机要运行的命令，例如启动 frp
#!/bin/sh
nohup /home/ubuntu/frp_xxxx/frpc -c /home/ubuntu/frpxxxx/frpc.ini &
exit 0
# 给rc.local加权限,切记
chmod +x /etc/rc.local
# 在 /etc/systemd/system 目录下创建软链接
ln -s /lib/systemd/system/rc-local.service /etc/systemd/system/
```

