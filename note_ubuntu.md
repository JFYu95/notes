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

linux install and join network(zerotier):

```shell
curl -s https://install.zerotier.com | sudo bash
sudo zerotier-cli join your work ID
sudo zerotier-cli join 93afae59638cef06
```

图形化docker  (samba jellyfin)

```shell
docker pull portainer/portainer
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock --restart=always --name prtainer portainer/portainer

docker run -d -p 8096:8096 -v /jellyfin/config:/config -v /root/data/downloads:/media jellyfin/jellyfin
```

