---
title: How to use SONM platform
layout: article
key: 20181212
tags: SONM, Tutorial
---

Hello everyone! In this tutorial, sonmwalker will show the basic operations in SONM platform.

## How to install SONM

<!--more-->

### As a consumer

`sudo bash -c "$(curl -s https://raw.githubusercontent.com/sonm-io/autodeploy/master/sonm-auto-deploy-consumer.sh)"`

Consumer's wallet should replaced by the one which has SONM tokens.
1. Replace the key (ETH address) in the keystore /etc/sonm/sonm-keystore.
2. sudo nano /etc/sonm/node-default.yaml look for the "pass_phrase" - replace with your password.
3. sonmcli login <your address>
4. sudo service sonm-node restart
  

### As a supplier

`sudo bash -c "$(curl -s https://raw.githubusercontent.com/sonm-io/autodeploy/master/sonm-auto-deploy-supplier.sh)" -s YOUR_MASTER_ADDRESS`


key stored in /etc/sonm/key-store

## Create ask-plan

`sonmcli worker ask-plan create ask.yaml`


## Quick-buy ask-plan

`sonmcli deal quick-buy orderid`

## Start task

`sonmcli tast start dealid  task.yaml`

## Logs

`sonmcli logs dealid taskid`

## Close deal 

`sonmcli deal close dealid`
