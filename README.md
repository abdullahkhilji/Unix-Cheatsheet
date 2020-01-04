# Unix-Cheatsheet

# Setting Proxy

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

SERVER: 172.16.199.20
PORT: 8080

#### Add the following lines to _~/.bashrc_


export http_proxy=http://172.16.199.20:8080/ <br>
export https_proxy=https://172.16.199.20:8080/ <br>
  
#### Add the following lines to _/etc/apt/apt.conf_


Acquire::http::Proxy "http://172.16.199.20:8080"; <br>
Acquire::https::Proxy "https://172.16.199.20:8080"; <br>

#### Add the following lines to _/etc/bash.bashrc_


export http_proxy=http://172.16.199.20:8080/ <br>
export https_proxy=https://172.16.199.20:8080/ <br>

#### Add the following lines to _/etc/environment_


export http_proxy="http://172.16.199.20:8080/" <br>
export https_proxy="https://172.16.199.20:8080/" <br>

# Installation and Extraction of Packages

sudo dpkg -i DEB_PACKAGE
sudo apt-get install -f
tar -zxvf file.tar.gz



# Setting path in java:


gedit ~/.bashrc

JAVA_HOME=/opt/jdk-9.0.1/bin
export JAVA_HOME 
PATH=$PATH:$JAVA_HOME 
export PATH



# Version Check and Update

### Version Check
$ lsb_release -a

### Update
$ sudo apt install update-manager-core
$ sudo do-release-upgrade

### Update Key Ubuntu Repositories
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys KEY-HERE


sudo apt-key adv --keyserver-options http-proxy=http://USER:PASSWORD@PROXY_URL:PORT/ --keyserver keyserver.ubuntu.com --recv-keys GPG_KEY
