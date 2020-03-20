# denarius-wiki
https://denarius.wiki  
using Hugo and Learn Theme https://themes.gohugo.io/hugo-theme-learn/  
## Install hugo (Linux)  
download latest https://github.com/gohugoio/hugo/releases  
```
wget https://github.com/gohugoio/hugo/releases/download/v0.67.1/hugo_0.67.1_Linux-64bit.tar.gz
tar -xzvf https://github.com/gohugoio/hugo/releases/download/v0.67.1/hugo_0.67.1_Linux-64bit.tar.gz
cp hugo /usr/local/bin
cd ~
```
## clone and build
```
git clone https://github.com/buzzkillb/denarius-wiki
cd ~/denarius-wiki
git submodule init
git submodule update
hugo
```
## run hugo local server  
https://gohugo.io/getting-started/quick-start/
```
hugo server -D
```
look at page on your local web browser (VM)  
`http://localhost:1313/`
