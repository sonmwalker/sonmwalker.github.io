---
title: Mining ETH (Ethreum) using SONM platform
layout: article
key: 20180721
tags: mining, ETH, Ethreum
---

Hello everyone! In this tutorial, sonmwalker will show how to mine [ETH (Ethreum)](https://www.ethereum.org/) using the [SONM platform](https://docs.sonm.com/) in VirtualBox environment. 

### 1. Install VirtualBox on host and install Ubuntu 64-bit (version >= 16.04) using VirtualBox

- To install VirtualBox on host, please follow this [tutorial](https://www.wikihow.com/Install-VirtualBox).

- To install Ubuntu (version >= 16.04) in VirtualBox please first download [Ubuntu Desktop 64bit](https://www.ubuntu.com/download/desktop), then follow this [tutorial](https://medium.com/@tushar0618/install-ubuntu-16-04-lts-on-virtual-box-desktop-version-30dc6f1958d0).


### 2. Create Ethreum accounts using SONM GUI Wallet

Since SONM is based on ETH blockchain and we also need to mine ETH using SONM platform, thus we will need to create two ETH accounts, one to use on SONM platform, and the other one to receive the mined ETH. (Customers could also choose to use one account to do this.) 


- To create a wallet and ETH accounts please follow [SONM GUI Wallet guide](https://docs.sonm.com/guides/sonm-gui-guide/sonm-wallet-guide).


We denote the ETH account which will be used on SONM platform as ETH1, and the one to receive mined ETH as ETH2.

### 3. Install SONM platform in Ubuntu 16.04

- To get started as a consumer please follow these [steps](https://docs.sonm.com/getting-started/as-a-consumer).

In this step, customers have to deposit some ETH and SONM tokens to their ETH1 acount. Customer could consider buy ETH and SONM following this [tutorial on Changenow](https://blog.sonm.io/5-steps-to-buy-snm-on-changenow-75a4d0be12e0) or this [tutorial on Binance](https://medium.com/wespostdotcom/the-ultimate-beginners-guide-to-binance-exchange-buy-sell-cryptocurrency-fadb91d1fb09).

### 4. Buy resource from SONM Market

There are two ways to buy resource from SONM Market:
- Buy resource using SONM Gui Market, follow this [instruction](https://docs.sonm.com/guides/sonm-gui-guide/market-guide#How-to-buy-resourses).

- Buy resource using `sonmcli deal quick-buy <ask_id> [duration] [flags]` command line interface, follow this [instruction](https://docs.sonm.com/guides/sonm-cli-guide#deal_quick-buy).

Now we will get a `deal_id` which will be used in the next step to start a ETH mining task.

### 5. Start a Ethreum mining task on the deal

From the [whitelist](https://github.com/sonm-io/allowed-list) of SONM platform we can find eth-claymore docker image which supports both AMD and Nvidia GPUs is in the whitelist. 

##### Ethereum Claymore miner (Both AMD and NVidia)

Docker image: [sonm/eth-claymore:latest](https://hub.docker.com/r/sonm/eth-claymore/)

Enviroment variables:
```
WALLET - your ethereum address for mined funds, required
POOL   - ethereum mining pool, default: "eth-eu1.nanopool.org:9999"
WORKER - worker name, default: "sonm_worker"
EMAIL  - your email, optional
```

Customers need to create a file called [`task.yaml`](task.yaml) to start the mining:

`task.yaml`
```
# docker image settings, required section
container:
  # Image name to start on worker, required param.
  image: sonm/eth-claymore:latest
  # Env variables that will be passed to container on start.
  env:
    WALLET: # Put ETH2 address here
    # optional params
    # POOL: ethereum mining pool, default: "eth-eu1.nanopool.org:9999"
    # WORKER: my_sonm_worker
```

Now we can start the mining task on deal `deal_id` using the command:

`sonmcli task start deal_id task.yaml`


<!--more-->


