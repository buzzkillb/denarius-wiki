---
title: "Setup"
date: 2020-03-04T23:16:51-08:00
---
### How to Setup a FortunaStake (masternode)
#### Minimum Requirements

| CPU | RAM | HD | IP Address |
| ------ | ----------- | ------- | ------- |
| 1 Core | 2GB | 20GB | IPv4 / IPv6 / Onion |

This will take 500 confirms before being able to start, so do the send first, then read through the guide. Send exactly 5000 D to an address and give that address a label like FS01.

Script for VPS Portion Located Here
This will pull master branch and compile the latest wallet. And add a cronjob to restart wallet every hour to make sure things stay in sync.

https://github.com/buzzkillb/d-fortunastake

#### QT Wallet PC - Hot Wallet
After sending 5000 D to a labelled address, we need the following; transaction hash and index of the 5000 send, fortunastake private key, and your VPS IP address.

```
FS01 VPSIPADDRESS:9999 FORTUNASTAKEPRIVKEY TRANSACTIONHASH INDEXNUMBER
```  
Sample **fortunastake.conf**  

```
FS01 11.11.12.13:9999 6J8tAUsVhXBgfdeewqsdghySWEQEeb4XGSC251sM7bYQgEXh7 f08d926f92cc4c65321344828f6394f41121903502459ffde4ef7aef39e6392b 0
```  
fortunastake private key  

```
fortunastake genkey
```  
fortunastake transaction hash and id  

```
fortunastake outputs
```  
VPS of your ip should be somewhat obvious. After creating your fortunastake.conf, save and restart the QT wallet.  

Sample QT **denarius.conf**  

```
fsconflock=1
staking=1
```  
Now that address has locked the 5000 D collateral.

#### VPS - Cold Wallet
Get a VPS from somewhere like Vultr, make note of its IP address for the above fortunastake.conf creation for the QT wallet. The guide is using Ubuntu 16.04 as the example. **Log into VPS using an SSH client, Putty on Windows**.

Update Ubuntu

```
sudo apt-get update && apt-get upgrade -y
```
Install Dependencies
 

```
sudo apt-get install -y git unzip build-essential libssl-dev libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libgmp-dev libevent-dev autogen automake  libtool
```
Install Fail2Ban

```
sudo apt install fail2ban
```
Create Swap File
```
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```
Install Firewall
```
sudo apt install ufw -y
ufw default deny incoming
ufw default allow outgoing
ufw allow ssh/tcp
ufw limit ssh/tcp
ufw allow 33369/tcp
ufw allow 9999/tcp
ufw logging on
ufw --force enable
```
Compile and Install Wallet (most likely need to add swapfile below).
```
git clone https://github.com/carsenk/denarius
cd denarius
git checkout master
cd src
make -f makefile.unix
strip denariusd
sudo mv ~/denarius/src/denariusd /usr/local/bin/denariusd
``` 

Install Chaindata
```
apt-get -y install unzip
mkdir ~/.denarius
cd ~/.denarius
rm -rf database txleveldb smsgDB
wget https://denarii.cloud/chaindata.zip
unzip chaindata.zip
```
Create denarius.conf in the .denarius folder. Notice the . in the folder name.

**denarius.conf**
```
rpcuser=USEARANDOMNAME
rpcpassword=USEARANDOMPASSWORD
daemon=1
port=9999
fortunastakeprivkey=6J8tAUsVhXBgfdeewqsdghySWEQEeb4XGSC251sM7bYQgEXh7
```
run denariusd by typing
```
denariusd
```
**Start**

Go back to your QT, go to debug console and type.
```
fortunastake start-alias FS01
```
In the My Denarius Fortuna Stakes tab in your QT collateral wallet, the QT will show Registered once you start your FortunaStake and then Verified, then Online, then Active. Wait 1 complete round for rewards. 1 round is roughly how many ForTunaStakes are up, and that's how many blocks a round will last.

**Status Check**

masternode status still works for specific reasons, but fortunastake status gives info in English instead of numbers and gibberish.

```
fortunastake status
```

reference: https://denariustalk.org/index.php?/topic/233-d-fortunastake-setup-guide-hot-cold-wallet/
