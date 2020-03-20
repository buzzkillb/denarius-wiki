---
title: "SNAP"
date: 2020-03-05T00:17:05-08:00
---
## Run the Native QT and daemon from Most Linux Distributions
reference: https://snapcraft.io/denarius

#### Ubuntu

```
sudo apt update
sudo apt install snapd
sudo snap install denarius
```
#### Arch Linux
```
git clone https://aur.archlinux.org/snapd.git
cd snapd
makepkg -si
sudo systemctl enable --now snapd.socket
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install denarius
```
#### CentOS
```
sudo yum install epel-release
sudo yum install snapd
sudo systemctl enable --now snapd.socket
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install denarius
```
#### Debian
```
sudo apt update
sudo apt install snapd
sudo snap install denarius
````
#### elementary OS
```
sudo apt update
sudo apt install snapd
sudo snap install denarius
```
#### Fedora
```
sudo dnf install snapd
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install denarius
```
#### KDE Neon
```
sudo apt update
sudo apt install snapd
sudo snap install denarius
```
#### Kubuntu
```
sudo apt update
sudo apt install snapd
sudo snap install denarius
```
#### Manjaro
```
sudo pacman -S snapd
sudo systemctl enable --now snapd.socket
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install denarius
```
#### Linux Mint
```
sudo apt update
sudo apt install snapd
sudo snap install denarius
```
#### openSUSE
```
sudo zypper addrepo --refresh https://download.opensuse.org/repositories/system:/snappy/openSUSE_Leap_15.0 snappy
sudo zypper --gpg-auto-import-keys refresh
sudo zypper dup --from snappy
sudo zypper install snapd
sudo systemctl enable snapd
sudo systemctl start snapd
sudo systemctl enable snapd.apparmor
sudo systemctl start snapd.apparmor
sudo snap install denarius
```
#### Red Hat
```
sudo rpm -ivh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo subscription-manager repos --enable "rhel-*-optional-rpms" --enable "rhel-*-extras-rpms"
sudo yum update
sudo yum install snapd
sudo systemctl enable --now snapd.socket
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install denarius
```
