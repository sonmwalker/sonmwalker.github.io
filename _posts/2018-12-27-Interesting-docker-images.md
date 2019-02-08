---
title: Some useful docker images
layout: article
key: 20181227
tags: docker
---

Hello everyone! Below are some interesting docker images from: [https://www.xiaokyun.com/post/tag/youtube-dl](https://www.xiaokyun.com/post/tag/youtube-dl){:target=_blank}

<!--more-->

docker一键安装脚本

wget -qO- get.docker.com | sh

镜像01：rastasheep/ubuntu-sshd （带ssh的ubuntu）
地址：https://hub.docker.com/r/rastasheep/ubuntu-sshd/

sudo docker run -d -p 22:22 rastasheep/ubuntu-sshd:16.04

用户名、密码为root

镜像02：itscaro/debian-ssh （带ssh的ubuntu）
地址：https://hub.docker.com/r/itscaro/debian-ssh/

sudo docker run -d -p 22:22 itscaro/debian-ssh

用户名、密码为root

镜像03：tutum/centos （带ssh的centos）
地址：https://hub.docker.com/r/tutum/centos/

sudo docker run -d -p 22:22 tutum/centos

（centos7：tutum/centos:centos7 ）
用户名root，
密码随机，请执行 docker logs 查看
这个作者还有好多好东西：https://hub.docker.com/r/tutum/centos/

镜像04：alexwhen/docker-2048（游戏2048）
地址：https://hub.docker.com/r/alexwhen/docker-2048/

sudo docker run -d -p 80:80 alexwhen/docker-2048

镜像05：dorowu/ubuntu-desktop-lxde-vnc（noVNC、Firefox51）
地址：https://hub.docker.com/r/dorowu/ubuntu-desktop-lxde-vnc/

docker run -it -p 80:80 dorowu/ubuntu-desktop-lxde-vnc

Browse http://localhost/

镜像06：consol/centos-xfce-vnc （VNC、noVNC、密码、chrome、Firefox45）
地址：https://hub.docker.com/r/consol/ubuntu-xfce-vnc/

run -it -p 5901:5901 -p 6901:6901 -e “VNC_PW=my-new-password” -e VNC_RESOLUTION=800×600 consol/centos-xfce-vnc

默认VNC密码：vncpassword
VNC-Server (default VNC port 5901)
noVNC – HTML5 VNC client (default http port 6901)
其他相关

onsol/centos-xfce-vnc: Centos7 with Xfce4 UI session
consol/ubuntu-xfce-vnc: Ubuntu with Xfce4 UI session
consol/centos-icewm-vnc: dev Centos7 with IceWM UI session
consol/ubuntu-icewm-vnc: dev Ubuntu with IceWM UI session

镜像07：fish/peerflix-server （支持磁力，种子）
地址：https://hub.docker.com/r/fish/peerflix-server

docker run -it -p 9000:9000 fish/peerflix-server

Browse http://localhost:9000/

镜像08：jpillora/cloud-torrent（种子下载，搜索）
地址：https://hub.docker.com/r/jpillora/cloud-torrent/

docker run -d -p 3000:3000 -v /path/to/my/downloads:/downloads jpillora/cloud-torrent

Browse http://localhost:3000/

镜像09：jim3ma/google-mirror（google镜像，如需ssl要手动添加）
地址：https://hub.docker.com/r/jim3ma/google-mirror/

docker run -d -p 80:80 jim3ma/google-mirror

Browse http://localhost:80/

镜像⒑：google-reverse-proxy（google镜像，有ssl）
地址：https://hub.docker.com/r/jokester/google-reverse-proxy/

docker run -d –publish 54321:20081 –restart=always jokester/google-reverse-proxy

Browse https://ip:54321/

镜像⒒：forsaken-mail（临时邮箱）
地址：https://hub.docker.com/r/rockmaity/forsaken-mail/

docker run –name forsaken-mail -itd -p 25:25 -p 3000:3000 rockmaity/forsaken-mail

Browse http://ip:3000/

镜像⒓：imdjh/owncloud-with-ocdownloader（owncloud,torrent,aria2,youtube-dl）
地址：https://hub.docker.com/r/imdjh/owncloud-with-ocdownloader/

docker run -d -p 80:80 -e OWNCLOUD_VERSION=9.1.4 -v /var/www/html/data:/var/www/html/data imdjh/owncloud-with-ocdownloader

Browse http://ip/

镜像⒔：v2ray/official（v2ray）
地址：https://hub.docker.com/r/v2ray/official/

docker run -d -p 8001:8001 v2ray/official

镜像⒕：timonier/aria2
地址：https://hub.docker.com/r/timonier/aria2/

docker run -i -t -v /data:/data –net host timonier/aria2 –dir=/data –enable-rpc –rpc-listen-all=true

配合使用：timonier/webui-aria2（aria2web管理）
地址：https://hub.docker.com/r/timonier/webui-aria2/

docker run -i -t -p 80:80 timonier/webui-aria2

原文: [http://blog.jialezi.net/?post=35](docker一键安装脚本

wget -qO- get.docker.com | sh

镜像01：rastasheep/ubuntu-sshd （带ssh的ubuntu）
地址：https://hub.docker.com/r/rastasheep/ubuntu-sshd/

sudo docker run -d -p 22:22 rastasheep/ubuntu-sshd:16.04

用户名、密码为root

镜像02：itscaro/debian-ssh （带ssh的ubuntu）
地址：https://hub.docker.com/r/itscaro/debian-ssh/

sudo docker run -d -p 22:22 itscaro/debian-ssh

用户名、密码为root

镜像03：tutum/centos （带ssh的centos）
地址：https://hub.docker.com/r/tutum/centos/

sudo docker run -d -p 22:22 tutum/centos

（centos7：tutum/centos:centos7 ）
用户名root，
密码随机，请执行 docker logs 查看
这个作者还有好多好东西：https://hub.docker.com/r/tutum/centos/

镜像04：alexwhen/docker-2048（游戏2048）
地址：https://hub.docker.com/r/alexwhen/docker-2048/

sudo docker run -d -p 80:80 alexwhen/docker-2048

镜像05：dorowu/ubuntu-desktop-lxde-vnc（noVNC、Firefox51）
地址：https://hub.docker.com/r/dorowu/ubuntu-desktop-lxde-vnc/

docker run -it -p 80:80 dorowu/ubuntu-desktop-lxde-vnc

Browse http://localhost/

镜像06：consol/centos-xfce-vnc （VNC、noVNC、密码、chrome、Firefox45）
地址：https://hub.docker.com/r/consol/ubuntu-xfce-vnc/

run -it -p 5901:5901 -p 6901:6901 -e “VNC_PW=my-new-password” -e VNC_RESOLUTION=800×600 consol/centos-xfce-vnc

默认VNC密码：vncpassword
VNC-Server (default VNC port 5901)
noVNC – HTML5 VNC client (default http port 6901)
其他相关

onsol/centos-xfce-vnc: Centos7 with Xfce4 UI session
consol/ubuntu-xfce-vnc: Ubuntu with Xfce4 UI session
consol/centos-icewm-vnc: dev Centos7 with IceWM UI session
consol/ubuntu-icewm-vnc: dev Ubuntu with IceWM UI session

镜像07：fish/peerflix-server （支持磁力，种子）
地址：https://hub.docker.com/r/fish/peerflix-server

docker run -it -p 9000:9000 fish/peerflix-server

Browse http://localhost:9000/

镜像08：jpillora/cloud-torrent（种子下载，搜索）
地址：https://hub.docker.com/r/jpillora/cloud-torrent/

docker run -d -p 3000:3000 -v /path/to/my/downloads:/downloads jpillora/cloud-torrent

Browse http://localhost:3000/

镜像09：jim3ma/google-mirror（google镜像，如需ssl要手动添加）
地址：https://hub.docker.com/r/jim3ma/google-mirror/

docker run -d -p 80:80 jim3ma/google-mirror

Browse http://localhost:80/

镜像⒑：google-reverse-proxy（google镜像，有ssl）
地址：https://hub.docker.com/r/jokester/google-reverse-proxy/

docker run -d –publish 54321:20081 –restart=always jokester/google-reverse-proxy

Browse https://ip:54321/

镜像⒒：forsaken-mail（临时邮箱）
地址：https://hub.docker.com/r/rockmaity/forsaken-mail/

docker run –name forsaken-mail -itd -p 25:25 -p 3000:3000 rockmaity/forsaken-mail

Browse http://ip:3000/

镜像⒓：imdjh/owncloud-with-ocdownloader（owncloud,torrent,aria2,youtube-dl）
地址：https://hub.docker.com/r/imdjh/owncloud-with-ocdownloader/

docker run -d -p 80:80 -e OWNCLOUD_VERSION=9.1.4 -v /var/www/html/data:/var/www/html/data imdjh/owncloud-with-ocdownloader

Browse http://ip/

镜像⒔：v2ray/official（v2ray）
地址：https://hub.docker.com/r/v2ray/official/

docker run -d -p 8001:8001 v2ray/official

镜像⒕：timonier/aria2
地址：https://hub.docker.com/r/timonier/aria2/

docker run -i -t -v /data:/data –net host timonier/aria2 –dir=/data –enable-rpc –rpc-listen-all=true

配合使用：timonier/webui-aria2（aria2web管理）
地址：https://hub.docker.com/r/timonier/webui-aria2/

docker run -i -t -p 80:80 timonier/webui-aria2

原文: [http://blog.jialezi.net/?post=35](docker一键安装脚本

wget -qO- get.docker.com | sh

镜像01：rastasheep/ubuntu-sshd （带ssh的ubuntu）
地址：https://hub.docker.com/r/rastasheep/ubuntu-sshd/

sudo docker run -d -p 22:22 rastasheep/ubuntu-sshd:16.04

用户名、密码为root

镜像02：itscaro/debian-ssh （带ssh的ubuntu）
地址：https://hub.docker.com/r/itscaro/debian-ssh/

sudo docker run -d -p 22:22 itscaro/debian-ssh

用户名、密码为root

镜像03：tutum/centos （带ssh的centos）
地址：https://hub.docker.com/r/tutum/centos/

sudo docker run -d -p 22:22 tutum/centos

（centos7：tutum/centos:centos7 ）
用户名root，
密码随机，请执行 docker logs 查看
这个作者还有好多好东西：https://hub.docker.com/r/tutum/centos/

镜像04：alexwhen/docker-2048（游戏2048）
地址：https://hub.docker.com/r/alexwhen/docker-2048/

sudo docker run -d -p 80:80 alexwhen/docker-2048

镜像05：dorowu/ubuntu-desktop-lxde-vnc（noVNC、Firefox51）
地址：https://hub.docker.com/r/dorowu/ubuntu-desktop-lxde-vnc/

docker run -it -p 80:80 dorowu/ubuntu-desktop-lxde-vnc

Browse http://localhost/

镜像06：consol/centos-xfce-vnc （VNC、noVNC、密码、chrome、Firefox45）
地址：https://hub.docker.com/r/consol/ubuntu-xfce-vnc/

run -it -p 5901:5901 -p 6901:6901 -e “VNC_PW=my-new-password” -e VNC_RESOLUTION=800×600 consol/centos-xfce-vnc

默认VNC密码：vncpassword
VNC-Server (default VNC port 5901)
noVNC – HTML5 VNC client (default http port 6901)
其他相关

onsol/centos-xfce-vnc: Centos7 with Xfce4 UI session
consol/ubuntu-xfce-vnc: Ubuntu with Xfce4 UI session
consol/centos-icewm-vnc: dev Centos7 with IceWM UI session
consol/ubuntu-icewm-vnc: dev Ubuntu with IceWM UI session

镜像07：fish/peerflix-server （支持磁力，种子）
地址：https://hub.docker.com/r/fish/peerflix-server

docker run -it -p 9000:9000 fish/peerflix-server

Browse http://localhost:9000/

镜像08：jpillora/cloud-torrent（种子下载，搜索）
地址：https://hub.docker.com/r/jpillora/cloud-torrent/

docker run -d -p 3000:3000 -v /path/to/my/downloads:/downloads jpillora/cloud-torrent

Browse http://localhost:3000/

镜像09：jim3ma/google-mirror（google镜像，如需ssl要手动添加）
地址：https://hub.docker.com/r/jim3ma/google-mirror/

docker run -d -p 80:80 jim3ma/google-mirror

Browse http://localhost:80/

镜像⒑：google-reverse-proxy（google镜像，有ssl）
地址：https://hub.docker.com/r/jokester/google-reverse-proxy/

docker run -d –publish 54321:20081 –restart=always jokester/google-reverse-proxy

Browse https://ip:54321/

镜像⒒：forsaken-mail（临时邮箱）
地址：https://hub.docker.com/r/rockmaity/forsaken-mail/

docker run –name forsaken-mail -itd -p 25:25 -p 3000:3000 rockmaity/forsaken-mail

Browse http://ip:3000/

镜像⒓：imdjh/owncloud-with-ocdownloader（owncloud,torrent,aria2,youtube-dl）
地址：https://hub.docker.com/r/imdjh/owncloud-with-ocdownloader/

docker run -d -p 80:80 -e OWNCLOUD_VERSION=9.1.4 -v /var/www/html/data:/var/www/html/data imdjh/owncloud-with-ocdownloader

Browse http://ip/

镜像⒔：v2ray/official（v2ray）
地址：https://hub.docker.com/r/v2ray/official/

docker run -d -p 8001:8001 v2ray/official

镜像⒕：timonier/aria2
地址：https://hub.docker.com/r/timonier/aria2/

docker run -i -t -v /data:/data –net host timonier/aria2 –dir=/data –enable-rpc –rpc-listen-all=true

配合使用：timonier/webui-aria2（aria2web管理）
地址：https://hub.docker.com/r/timonier/webui-aria2/

docker run -i -t -p 80:80 timonier/webui-aria2

原文: http://blog.jialezi.net/?post=35


- docker-zmirror

https://hub.docker.com/r/fanvinga/docker-zmirror

https://github.com/aploium/zmirror


- you2php
https://you2php.github.io/download.html

provider: ramnode, vultr, vast.ai, paperspace, sonm 

