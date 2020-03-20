---
title: "Compile"
date: 2020-03-05T00:17:05-08:00
---
## How to compile QT and daemon on various versions of Ubuntu.

### Ubuntu 16.04

#### Daemon
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libssl-dev libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libgmp-dev libevent-dev autogen automake  libtool libcurl4-openssl-dev
git clone https://github.com/carsenk/denarius
cd denarius
git checkout master
git pull
cd src
make -f makefile.unix
sudo mv ~/denarius/src/denariusd /usr/local/bin/denariusd
denariusd
```
#### QT
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libssl-dev libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libevent-dev autogen automake  libtool libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default libcurl4-openssl-dev
git clone https://github.com/carsenk/denarius
cd denarius || exit
git checkout master
git pull
qmake "USE_QRCODE=1" "USE_UPNP=1" denarius-qt.pro
make
./Denarius
```

### Ubuntu 18.04

#### Daemon
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libgmp-dev libevent-dev autogen automake  libtool zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://www.openssl.org/source/openssl-1.0.1j.tar.gz
tar -xzvf openssl-1.0.1j.tar.gz
cd openssl-1.0.1j
./config
make depend
make
sudo make install
sudo ln -sf /usr/local/ssl/bin/openssl `which openssl`
cd ~
openssl version -v

git clone https://github.com/carsenk/denarius
cd denarius
git checkout master
git pull
cd src
OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib make -f makefile.unix
sudo mv ~/denarius/src/denariusd /usr/local/bin/denariusd
denariusd
```

#### QT
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libevent-dev autogen automake  libtool libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://www.openssl.org/source/openssl-1.0.1j.tar.gz
tar -xzvf openssl-1.0.1j.tar.gz
cd openssl-1.0.1j
./config
make depend
make
sudo make install
sudo ln -sf /usr/local/ssl/bin/openssl `which openssl`
cd ~
openssl version -v

git clone https://github.com/carsenk/denarius
cd denarius
git checkout master
git pull
qmake "USE_UPNP=1" "USE_QRCODE=1" LIBS=-lboost_chrono OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib denarius-qt.pro
make
./Denarius
```

### Ubuntu 19.04

#### QT
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libevent-dev autogen automake  libtool libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://www.openssl.org/source/openssl-1.0.1j.tar.gz
tar -xzvf openssl-1.0.1j.tar.gz
cd openssl-1.0.1j
./config
make depend
make
sudo make install
sudo ln -sf /usr/local/ssl/bin/openssl `which openssl`
cd ~
openssl version -v

git clone https://github.com/carsenk/denarius
cd denarius
git checkout master
git pull
qmake "USE_UPNP=1" "USE_QRCODE=1" LIBS=-lboost_chrono OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib denarius-qt.pro
make
./Denarius
```
