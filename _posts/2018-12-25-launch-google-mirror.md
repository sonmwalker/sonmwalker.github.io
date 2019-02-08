---
title: Launch a google-mirror using SONM platform
layout: article
key: 20181215
tags: Google-mirror, SONM, docker
---

Hello everyone! In this tutorial, sonmwalker will show how to launch a google mirror using the [SONM platform](https://docs.sonm.com/){:target=_blank}.

<!--more-->

### 1. [Install SONM platform for customers and get a deal](https://sonmwalker.github.io/2018/12/12/sonm-intro.html){:target=_blank}

>>
- In the bid order, the `income` flag should be turned on.
- Consumer’s wallet should replaced by the one which has SONM tokens.

### 2. Start the google-mirror docker container

`sonmcli task start dealid  task-google-mirror.yaml`

The `task-google-mirror.yaml` file can be downloaded [here](https://github.com/sonmwalker/ss/blob/master/sonm/task-google-mirror.yaml){:target=_blank}, it reads:

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



