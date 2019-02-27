---
title: Launch a google-mirror using SONM platform / 使用SONM平台建立一个谷歌镜像网站
layout: article
key: 20181225
tags: Google-mirror, SONM, docker
---

This tutorial  will show how to launch a google mirror using the [SONM platform](https://docs.sonm.com/){:target=_blank}.

本教程说明如何使用SONM平台建设一个google 镜像网站。
<!--more-->

### 1. [Install SONM platform for customers and get a deal](https://sonmwalker.github.io/2018/12/12/sonm-intro.html){:target=_blank}
/ [安装SONM平台并购买交易](https://sonmwalker.github.io/2018/12/12/sonm-intro.html){:target=_blank}

>
- In the bid order, the `income` flag should be turned on.
- Consumer’s wallet should replaced by the one which has SONM tokens.

>
- 在`bid order`中要指定`income`标签;
- 客户的ETH钱包里要有SONM代币。

### 2. Start the google-mirror docker container / 启动google-mirror docker 镜像

`sonmcli task start dealid  task-google-mirror.yaml`

The `task-google-mirror.yaml` file can be downloaded [here](https://github.com/sonmwalker/ss/blob/master/sonm/task-google-mirror.yaml){:target=_blank}, it reads:

`task-google-mirror.yaml`文件在在[此处](https://github.com/sonmwalker/ss/blob/master/sonm/task-google-mirror.yaml){:target=_blank}下载，内容如下：

```
# docker image settings, required section
container:
  # Image name to start on worker, required param.
  image: jim3ma/google-mirror
  container_name: google-mirror
  expose:
    - 80:80
```



Now you can access the google-mirror using the IP of the deal supplier.
现在可以使用服务提供商的IP访问谷歌镜像了。



