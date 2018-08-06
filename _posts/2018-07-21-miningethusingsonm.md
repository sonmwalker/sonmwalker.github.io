---
title: Mining ETH (Ethreum) using SONM platform
layout: article
key: 20180721
tags: mining, ETH, Ethreum
---

Hello everyone! In this tutorial, sonmwalker will show how to mine [ETH (Ethreum)](https://www.ethereum.org/){:target=_blank} using the [SONM platform](https://docs.sonm.com/){:target=_blank} in VirtualBox environment. If you are already running Ubuntu (version >= 16.04) or other linux distribution, please skip Step 1.

<!--more-->

### 1. Install VirtualBox on host and install Ubuntu 64-bit (version >= 16.04) using VirtualBox

- To install VirtualBox on host, please follow this [tutorial](https://www.wikihow.com/Install-VirtualBox){:target=_blank}.

- To install Ubuntu (version >= 16.04) in VirtualBox please first download [Ubuntu Desktop 64bit](https://www.ubuntu.com/download/desktop){:target=_blank}, then follow this [tutorial](https://medium.com/@tushar0618/install-ubuntu-16-04-lts-on-virtual-box-desktop-version-30dc6f1958d0){:target=_blank}.


### 2. Create Ethreum accounts using SONM GUI Wallet

Since SONM is based on ETH blockchain and we also need to mine ETH using SONM platform, we will need to create two ETH accounts, one to use on SONM platform, and the other one to receive the mined ETH. (Customers could also choose to use the same ETH account to do both tasks.) 


- To create a wallet and ETH accounts please visit [SONM GUI Wallet](https://sonm-io.github.io/gui/#/){:target=_blank} and follow the [guide](https://docs.sonm.com/guides/sonm-gui-guide/sonm-wallet-guide){:target=_blank}.


We denote the ETH account which will be used on SONM platform as ETHADDRESS1, and the one to receive mined ETH as ETHADDRESS2.

### 3. Install SONM platform in Ubuntu 16.04

- To get started as a consumer please follow these [steps](https://docs.sonm.com/getting-started/as-a-consumer){:target=_blank}.

In this step, customers have to deposit some ETH and SONM tokens to their ETHADDRESS1 acount. Customer could consider buy ETH and SONM following this [tutorial on Changenow](https://blog.sonm.io/5-steps-to-buy-snm-on-changenow-75a4d0be12e0){:target=_blank} or this [tutorial on Binance](https://medium.com/wespostdotcom/the-ultimate-beginners-guide-to-binance-exchange-buy-sell-cryptocurrency-fadb91d1fb09){:target=_blank}.

### 4. Buy resource from SONM Market

There are two ways to buy resource from SONM Market:
- Buy resource using SONM Gui Market, follow this [instruction](https://docs.sonm.com/guides/sonm-gui-guide/market-guide#How-to-buy-resourses){:target=_blank}.

- Buy resource using `sonmcli deal quick-buy <ask_id> [duration] [flags]` command line interface, follow this [instruction](https://docs.sonm.com/guides/sonm-cli-guide#deal_quick-buy){:target=_blank}.

Now we will get a deal with `deal_id` which will be used in the next step to start a ETH mining task.

### 5. Start a Ethreum mining task on the deal

From the [whitelist](https://github.com/sonm-io/allowed-list){:target=_blank} of SONM platform we can find eth-claymore docker image which supports both AMD and Nvidia GPUs is in the whitelist. 

Below shows some information of the Ethereum Claymore miner (Both AMD and NVidia):

Docker image: [sonm/eth-claymore:latest](https://hub.docker.com/r/sonm/eth-claymore/){:target=_blank}

Enviroment variables:
```
WALLET - your ethereum address ETHADDRESS2 for mined funds, required
POOL   - ethereum mining pool, default: "eth-eu1.nanopool.org:9999"
WORKER - worker name, default: "sonm_worker"
EMAIL  - your email, optional
```

Before run a task, customers need to create a file called [`task.yaml`](./task.yaml){:target=_blank} to start the mining:

The file `task.yaml` reads
```
# docker image settings, required section
container:
  # Image name to start on worker, required param.
  image: sonm/eth-claymore:latest
  # Env variables that will be passed to container on start.
  env:
    WALLET: # Put ETHADDRESS2 here
    # optional params
    # POOL: ethereum mining pool, default: "eth-eu1.nanopool.org:9999"
    # WORKER: my_sonm_worker
```

Now we can start the mining task on deal `deal_id` using the command:

`sonmcli task start deal_id task.yaml`





