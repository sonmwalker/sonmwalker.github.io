---
title: Launch a shadow-socks server using SONM platform
layout: article
key: 20181231
tags: Shadowsocks, SONM, docker
---

Hello everyone! In this tutorial, sonmwalker will show how to launch a shadowsocks server using the [SONM platform](https://docs.sonm.com/){:target=_blank}.

<!--more-->

### 1. [Install SONM platform for customers and get a deal](https://sonmwalker.github.io/2018/12/12/sonm-intro.html){:target=_blank}

>
- In the bid order, the `income` flag should be turned on.
- Consumer’s wallet should replaced by the one which has SONM tokens.

### 2. Start the shadowsocks docker container

`sonmcli task start dealid  task-shadowsocks.yaml`

The `task-shadowsocks.yaml` file can be downloaded [here](https://github.com/sonmwalker/ss/blob/master/shadow-socks/task-shadowsocks.yaml){:target=_blank}, it reads:

```
shadowsocks:
  image: shadowsocks/shadowsocks-libev
  ports:
    - "8388:8388/tcp"
    - "8388:8388/udp"
  environment:
    - METHOD=aes-256-cfb
    - PASSWORD=12345
  restart: always
```

Now you can use this shadowsocks sever by specifying the IP of the supplier.



