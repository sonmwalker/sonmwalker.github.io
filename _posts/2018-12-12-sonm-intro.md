---
title: How to use SONM platform
layout: article
key: 20181212
tags: SONM, Tutorial
---

Hello everyone! In this tutorial, sonmwalker will show the basic operations in SONM platform.

## How to install SONM

### As a consumer

`sudo bash -c "$(curl -s https://raw.githubusercontent.com/sonm-io/autodeploy/master/sonm-auto-deploy-consumer.sh)"`

Consumer's wallet should replaced by the one which has SONM tokens.

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
