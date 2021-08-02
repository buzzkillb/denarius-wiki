---
title: "Compile"
date: 2020-03-05T00:17:05-08:00
---
## How to compile QT and daemon on Ubuntu and Fedora

### Ubuntu 16.04

#### Ubuntu 16.04 Daemon
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
#### Ubuntu 16.04 QT
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

#### Ubuntu 18.04 Daemon
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libgmp-dev libevent-dev autogen automake  libtool zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1j.tar.gz
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

#### Ubuntu 18.04 QT
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libevent-dev autogen automake  libtool libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1j.tar.gz
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

### Ubuntu 20.04

#### Ubuntu 20.04 Daemon
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libgmp-dev libevent-dev autogen automake  libtool zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1j.tar.gz
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
cd src
OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib make -f makefile.unix
sudo mv ~/denarius/src/denariusd /usr/local/bin/denariusd
denariusd
```

#### Ubuntu 20.04 QT
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libevent-dev autogen automake  libtool libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default zlib1g-dev jq libcurl4-openssl-dev

sudo apt-get install make
wget https://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1j.tar.gz
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
qmake "USE_UPNP=1" "USE_QRCODE=1" OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib denarius-qt.pro
make
./Denarius
```

#### Ubuntu 20.04 QT (secp256k1 branch) 
```
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y git unzip build-essential libdb++-dev libboost-all-dev libqrencode-dev libminiupnpc-dev libevent-dev autogen automake  libtool libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools qt5-default zlib1g-dev jq libcurl4-openssl-dev libgmp-dev libsecp256k1-dev

git clone https://github.com/carsenk/denarius
cd denarius
git checkout secp256k1
qmake "USE_UPNP=1" "USE_QRCODE=1" "USE_NATIVETOR=-" denarius-qt.pro
make
./Denarius
```

### Fedora

#### Fedora Daemon
```
sudo dnf update
sudo dnf install make automake gcc gcc-c++ kernel-devel boost-devel libtool zlib-devel libevent-devel libcurl-devel libdb-devel libdb-cxx-devel miniupnpc miniupnpc-devel

wget https://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1j.tar.gz
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
cd src
OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib make -f makefile.unix
sudo mv ~/denarius/src/denariusd /usr/local/bin/denariusd
denariusd
```

#### Fedora QT
```
sudo dnf update
sudo dnf install make automake gcc gcc-c++ kernel-devel boost-devel libtool zlib-devel libevent-devel libcurl-devel libdb-devel libdb-cxx-devel miniupnpc miniupnpc-devel qt5-qtbase qt5-qtbase-devel qt5-qttools qt5-qttools-devel qt5-qttools-common qrencode-devel protobuf-devel

wget https://ftp.openssl.org/source/old/1.0.1/openssl-1.0.1j.tar.gz
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
qmake-qt5 "USE_UPNP=1" "USE_QRCODE=1" OPENSSL_INCLUDE_PATH=/usr/local/ssl/include OPENSSL_LIB_PATH=/usr/local/ssl/lib denarius-qt.pro
make
sudo mv ~/denarius/Denarius /usr/local/bin/Denarius
Denarius
```

#### Fedora QT (secp256k1 branch) 
```
sudo dnf update
sudo dnf install make automake gcc gcc-c++ kernel-devel boost-devel libtool zlib-devel libevent-devel libcurl-devel libdb-devel libdb-cxx-devel miniupnpc miniupnpc-devel qt5-qtbase qt5-qtbase-devel qt5-qttools qt5-qttools-devel qt5-qttools-common qrencode-devel protobuf-devel libsecp256k1 libsecp256k1-devel gmp-devel

git clone https://github.com/carsenk/denarius
cd denarius
git checkout secp256k1
qmake-qt5 "USE_UPNP=1" "USE_QRCODE=1" "USE_NATIVETOR=-" denarius-qt.pro
make
sudo mv ~/denarius/Denarius /usr/local/bin/Denarius
Denarius
```

### Arch Linux

#### Arch Linux Daemon
```
sudo pacman -Syu miniupnpc libevent openssl-1.0 boost boost-libs libcurl-compat

git clone https://github.com/carsenk/denarius
cd denarius
cd src
OPENSSL_LIB_PATH=/usr/lib/openssl-1.0 OPENSSL_INCLUDE_PATH=/usr/include/openssl-1.0 make "USE_NATIVETOR=-" -f makefile.unix
sudo mv ~/denarius/src/denariusd /usr/local/bin/denariusd
denariusd
```

#### Arch Linux QT  
```
sudo pacman -Syu miniupnpc libevent openssl-1.0 boost boost-libs libcurl-compat qt5-base qt5-tools protobuf qrencode miniupnpc

git clone https://github.com/carsenk/denarius
cd denarius
qmake "USE_UPNP=1" "USE_QRCODE=1" OPENSSL_LIB_PATH=/usr/lib/openssl-1.0 OPENSSL_INCLUDE_PATH=/usr/include/openssl-1.0 "USE_NATIVETOR=-" denarius-qt.pro
make
sudo mv ~/denarius/Denarius /usr/local/bin/Denarius
Denarius
```

#### Arch Linux QT (secp256k1 branch) 
```
sudo pacman -Syu miniupnpc libevent boost boost-libs libcurl-compat qt5-base qt5-tools protobuf qrencode miniupnpc libsecp256k1 libgmp-static

git clone https://github.com/carsenk/denarius
cd denarius
git checkout secp256k1
qmake "USE_UPNP=1" "USE_QRCODE=1" "USE_NATIVETOR=-" denarius-qt.pro
make
sudo mv ~/denarius/Denarius /usr/local/bin/Denarius
Denarius
```
