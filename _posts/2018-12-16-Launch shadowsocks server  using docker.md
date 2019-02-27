---
title: Launch a shadowsocks server using docker / 使用docker启动`shadowsocks`服务
layout: article
key: 20181216
tags: shadowsocks, docker
---

This tutorial will show how to launch a shadowsocks server using docker. / 本教程说明如何使用`docker`启动`shadowsocks`服务。

<!--more-->

### 1. Install docker.io / 安装 docker.io

`sudo apt install docker.io`

### 2. Run docker-shadowsocks / 运行docker-shadowsocks映像文件

`docker run -d -p 12345:12345 oddrationale/docker-shadowsocks -s 0.0.0.0 -p 12345 -k 12345 -m aes-256-cfb`

where the first `-p` specifies the port mapping between the host and the container, the second `-p` specifies the port of the container, `-k` specifies the password, `-m` specifies the method.

Now you can use [shadowsocks client](https://shadowsocks.org/en/download/clients.html){:target=_blank} to get out of the fire wall.

其中第一个`-p`指定host和container的端口映射，第二个`-p`指定container的端口，`-k`指定密码，`-m`指定加密方法。







