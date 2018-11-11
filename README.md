# Unix-Cheatsheet

## Setting Proxy

First of all,

#### Configure using GUI

Open the network settings and set the your system wide network proxy.
Network -> Network proxy -> Configure -> Apply system wide.

<br><br><br>

~ Denotes Home Folder

#### Add the following lines to _~/.bashrc_


export http_proxy=http://USERNAME:PASSWORD@SERVER:PORT/ <br>
export https_proxy=https://USERNAME:PASSWORD@SERVER:PORT/ <br>
  
#### Add the following lines to _/etc/apt/apt.conf_


Acquire::http::Proxy "http://USERNAME:PASSWORD@SERVER:PORT"; <br>
Acquire::https::Proxy "https://USERNAME:PASSWORD@SERVER:PORT"; <br>

#### Add the following lines to _/etc/bash.bashrc_


export http_proxy=http://USERNAME:PASSWORD@SERVER:PORT/ <br>
export https_proxy=https://USERNAME:PASSWORD@SERVER:PORT/ <br>

#### Add the following lines to _/etc/environment_


export http_proxy="http://USERNAME:PASSWORD@SERVER:PORT/" <br>
export https_proxy="https://USERNAME:PASSWORD@SERVER:PORT/" <br>

### If Ony Server and Port Given

Example especially for NIT Silchar LAN User's, thanks to CCC :D

SERVER: 172.16.20.20
PORT: 8080

#### Add the following lines to _~/.bashrc_


export http_proxy=http://172.16.20.20:8080/ <br>
export https_proxy=https://172.16.20.20:8080/ <br>
  
#### Add the following lines to _/etc/apt/apt.conf_


Acquire::http::Proxy "http://172.16.20.20:8080"; <br>
Acquire::https::Proxy "https://172.16.20.20:8080"; <br>

#### Add the following lines to _/etc/bash.bashrc_


export http_proxy=http://172.16.20.20:8080/ <br>
export https_proxy=https://172.16.20.20:8080/ <br>

#### Add the following lines to _/etc/environment_


export http_proxy="http://172.16.20.20:8080/" <br>
export https_proxy="https://172.16.20.20:8080/" <br>







<br><br><br>
Referred From:
1. https://askubuntu.com/questions/257290/configure-proxy-for-apt <br>
2. https://medium.com/@krish.raghuram/setting-up-proxy-in-ubuntu-95058da0b2d4 <br>


