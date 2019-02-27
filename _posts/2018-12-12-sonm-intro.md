---
title: How to use SONM platform / 如何使用SONM平台
layout: article
key: 20181212
tags: SONM, Tutorial
---


## How to install SONM / SONM平台安装

<!--more-->

### As a consumer / 客户端

`sudo bash -c "$(curl -s https://raw.githubusercontent.com/sonm-io/autodeploy/master/sonm-auto-deploy-consumer.sh)"`

Consumer's wallet should be replaced by the one which has SONM tokens.
1. Replace the key (ETH address) in the keystore /etc/sonm/sonm-keystore.
2. sudo nano /etc/sonm/node-default.yaml look for the "pass_phrase" - replace with your password.
3. sonmcli login <your address>
4. sudo service sonm-node restart
  
客户端的ETH钱包可以使用如下方法替换：
1. 替换`/etc/sonm/sonm-keystore`文件夹里的ETH地址文件；
2. 修改`/etc/sonm/node-default.yaml`文件里的密码`pass_phrase`对应的字段为新钱包的密码；
3. 使用新地址登陆：`sonmcli login <your address`；
4. 重启`sonm-node`服务：`sudo service sonm-node restart`。
  

### As a supplier / 服务提供端

`sudo bash -c "$(curl -s https://raw.githubusercontent.com/sonm-io/autodeploy/master/sonm-auto-deploy-supplier.sh)" -s YOUR_MASTER_ADDRESS`

这一步将会为当前及其分配一个`worker address`,此地址会与`YOUR_MASTER_ADDRESS`关联，需要到SONM GUI WALLET确认`worker`。

## Create ask-plan / 服务提供端人工发布`ask-plan`

`sonmcli worker ask-plan create ask.yaml`


## Quick-buy ask-plan / 客户快速购买`ask-plan`

`sonmcli deal quick-buy orderid`

## Start task / 开始任务

`sonmcli tast start dealid  task.yaml`

## Check worker's status / 服务提供端检查`worker`的状态

`sonmcli worker status --worker-address=<worker address>`

## Logs / 记录

`sonmcli logs dealid taskid`

## Close deal / 客户端关闭交易

`sonmcli deal close dealid`
