---
title: Launch a shadow-socks server using SONM platform / 使用SONM平台启动shadow-socks服务器
layout: article
key: 20181231
tags: Shadowsocks, SONM, docker
---

This will show how to launch a shadowsocks server using the [SONM platform](https://docs.sonm.com/){:target=_blank}.

本教程展示如何使用SONM平台启动shadowsocks服务器[SONM platform](https://docs.sonm.com/){:target=_blank}.
<!--more-->

### 1. [Install SONM platform for customers and get a deal](https://sonmwalker.github.io/2018/12/12/sonm-intro.html){:target=_blank} / [安装SONM平台并获得交易](https://sonmwalker.github.io/2018/12/12/sonm-intro.html){:target=_blank}

> 
- In the bid order, the `income` flag should be turned on.
- Consumer’s wallet should replaced by the one which has SONM tokens.

>
- 在bid order中要指定income标签;
- 客户的ETH钱包里要有SONM代币

### 2. Start the shadowsocks docker container / 启动shadowsocks docker容器

`sonmcli task start dealid  task-shadowsocks.yaml`

The `task-shadowsocks.yaml` file can be downloaded [here](https://github.com/sonmwalker/ss/blob/master/sonm/task-shadowsocks.yaml){:target=_blank}, it reads:

`task-shadowsocks.yaml`文件在[此处下载](https://github.com/sonmwalker/ss/blob/master/sonm/task-shadowsocks.yaml){:target=_blank}, 内容如下：

```
shadowsocks:
  image: shadowsocks/shadowsocks-libev
  ports:
    - "12345:12345/tcp"
    - "12345:12345/udp"
  environment:
    - SERVER_PORT="12345"
    - METHOD=aes-256-cfb
    - PASSWORD=12345
  restart: always
```

Some environment variables can be found [here](https://github.com/sonmwalker/shadowsocks-libev/blob/master/docker/alpine/Dockerfile){:target=_blank}, include

其他可以自行指定环境变量可以在[这里](https://github.com/sonmwalker/shadowsocks-libev/blob/master/docker/alpine/Dockerfile){:target=_blank}找到，内容如下：
```
ENV SERVER_ADDR 0.0.0.0
ENV SERVER_ADDR_IPV6 ::0
ENV SERVER_PORT 12345
ENV PASSWORD=
ENV METHOD      aes-256-gcm
ENV TIMEOUT     300
ENV DNS_ADDRS    8.8.8.8,8.8.4.4
ENV ARGS=
```
Now you can use this shadowsocks sever by specifying the IP of the supplier.

下载可以通过指定shadowsocks服务器的IP，端口，加密方法来搭梯子了。



