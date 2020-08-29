# Unix-Cheatsheet
[![GitHub](https://img.shields.io/github/license/abdullahkhilji/Unix-Cheatsheet)](https://github.com/abdullahkhilji/Unix-Cheatsheet/blob/master/LICENSE)
# Setting Proxy

First of all,

#### Configure using GUI

Open the network settings and set the your system wide network proxy.
Network -> Network proxy -> Configure -> Apply system wide.

<br><br><br>

~ Denotes Home Folder

Note that HTTPS proxies begin with `http` this is to prevent SSL error while accessing the HTTPS protocol from the command line.

#### Add the following lines to _~/.bashrc_

```
export http_proxy=http://USERNAME:PASSWORD@SERVER:PORT/ 
export https_proxy=http://USERNAME:PASSWORD@SERVER:PORT/ 
``` 
#### Add the following lines to _/etc/apt/apt.conf_

```
Acquire::http::Proxy "http://USERNAME:PASSWORD@SERVER:PORT"; 
Acquire::https::Proxy "http://USERNAME:PASSWORD@SERVER:PORT"; 
```
#### Add the following lines to _/etc/bash.bashrc_

```
export http_proxy=http://USERNAME:PASSWORD@SERVER:PORT/ 
export https_proxy=http://USERNAME:PASSWORD@SERVER:PORT/ 
```
#### Add the following lines to _/etc/environment_

```
export http_proxy="http://USERNAME:PASSWORD@SERVER:PORT/" 
export https_proxy="http://USERNAME:PASSWORD@SERVER:PORT/" 
```
### If Ony Server and Port Given

Example especially for NIT Silchar LAN User's, thanks to CCC :D
If you feel the process is too lengthy, I would better recommend to use Ubuntu 16.04 the most stable Ubuntu Release ever, as it allows system wide proxy application via GUI. Will be happy if someone proves me wrong here :)
<br><br>
Also, note that the HTTPS proxy also begin with `http` this is due to NITS PROXY, and to prevent SSL error while accessing HTTPS protocol from the command line.

SERVER: 172.16.199.20
PORT: 8080

#### Add the following lines to _~/.bashrc_

```
export http_proxy=http://172.16.199.20:8080/ 
export https_proxy=http://172.16.199.20:8080/ 
```

#### Add the following lines to _/etc/apt/apt.conf_

```
Acquire::http::Proxy "http://172.16.199.20:8080"; 
Acquire::https::Proxy "http://172.16.199.20:8080"; 
```

#### Add the following lines to _/etc/bash.bashrc_

```
export http_proxy=http://172.16.199.20:8080/ 
export https_proxy=http://172.16.199.20:8080/ 
```

#### Add the following lines to _/etc/environment_

```
export http_proxy="http://172.16.199.20:8080/"
export https_proxy="http://172.16.199.20:8080/"
```

# Installation and Extraction of Packages

```
sudo dpkg -i DEB_PACKAGE
sudo apt-get install -f
tar -zxvf file.tar.gz
```


# Setting path in java:

```
gedit ~/.bashrc

JAVA_HOME=/opt/jdk-9.0.1/bin
export JAVA_HOME 
PATH=$PATH:$JAVA_HOME 
export PATH
```


# Version Check and Update

### Version Check
```
$ lsb_release -a
```
### Ubuntu System Update (Upgrades are Recommended as a last resort, never update for fun)
```
$ sudo apt install update-manager-core
$ sudo do-release-upgrade
```
### Update Key Ubuntu Repositories
```
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys KEY-HERE


$ sudo apt-key adv --keyserver-options http-proxy=http://USER:PASSWORD@PROXY_URL:PORT/ --keyserver keyserver.ubuntu.com --recv-keys GPG_KEY

$ sudo apt-key adv --keyserver-options http-proxy=http://172.16.199.20:8080 --keyserver keyserver.ubuntu.com --recv-keys GPG_KEY

# Set up GPU for Machine Learning
```
### At every step update and upgrade using
```
$ sudo apt update
$ sudo apt upgrade

$ sudo ubuntu-drivers autoinstall
```

Do CUDA network install by visiting CUDA Install Website,
```
$ wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-ubuntu1604.pin
$ sudo mv cuda-ubuntu1604.pin /etc/apt/preferences.d/cuda-repository-pin-600
$ sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
$ sudo add-apt-repository "deb http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/ /"
$ sudo apt-get update
$ sudo apt-get -y install cuda
```


# RSync
```
$ rsync -a --numeric-ids --delete -d --progress -e "ssh -T"
```
# Create a sudo user

```
# adduser username
# usermod -aG sudo username
```

# Write terminal output to file
```
any_command 2>&1 | tee output_001.txt
```

# C++ build for UNIX based systems

```
{
	"shell_cmd": "g++ \"${file}\" -o \"${file_path}/${file_base_name}\"",
	"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	"working_dir": "${file_path}",
	"selector": "source.c++",

	"variants":
	[
		{
			"name": "Run",
			"shell_cmd": "g++ \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\" < cases.in > cases.out"
		}
	]
}
```

# Miscellaneous
```
for f in *.txt; do (cat "${f}"; printf "\n\n") >> finalfile.txt; done
xzcat -v $language.*.raw.xz | ~/GitHub/preprocess/build/bin/commoncrawl_dedupe /dev/null |xz > $language.deduped.xz

```
