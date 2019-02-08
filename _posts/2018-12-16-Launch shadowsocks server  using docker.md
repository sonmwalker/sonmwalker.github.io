---
title: Launch a shadowsocks server using docker
layout: article
key: 20181216
tags: shadowsocks, docker
---

Hello everyone! In this tutorial, sonmwalker will show how to launch a shadowsocks server using docker.

<!--more-->

### 1. Install docker.io

`apt install docker.io`

### 2. Run docker-shadowsocks 

`docker run -d -p 12345:12345 oddrationale/docker-shadowsocks -s 0.0.0.0 -p 12345 -k 12345 -m aes-256-cfb`

Now you can use [shadowsocks client](https://shadowsocks.org/en/download/clients.html){:target=_blank} to get out of the fire wall.






