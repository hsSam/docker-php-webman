[![Build status](https://github.com/Tinywan/docker-php-webman/workflows/Docker/badge.svg)]()
[![license](https://img.shields.io/github/license/Tinywan/docker-php-webman)]()
[![nacos-sdk-php](https://img.shields.io/github/last-commit/tinywan/docker-php-webman/main)]()
[![nacos-sdk-php](https://img.shields.io/github/v/tag/tinywan/docker-php-webman?color=ff69b4)]()

## Build

```
docker build -t tinywan/docker-php-webman:7.4.29 .
```

```
podman build -t tinywan/docker-php-webman:8.1.10 .
```

## Usage

Start the Docker container:

### Linux

```shell
docker run --rm -it -p 8787:8787 -e TZ=Asia/Shanghai -v /home/www/webman:/app tinywan/docker-php-webman
```

```shell
sudo podman run --rm -it -p 8787:8787 -e TZ=Asia/Shanghai --name webman -v /data/workerman/start:/app tinywan/docker-php-webman:8.1.10
```

### port range

```shell
sudo podman run --rm -it -p 8787-8888:8787-8888 -e TZ=Asia/Shanghai --name webman -v /data/workerman/start:/app tinywan/docker-php-webman:8.1.10
```

### deamon run

```shell
sudo podman run -d -it --restart=always -e TZ=Asia/Shanghai -p 8787:8787 --name webman -v /data/workerman/start:/app tinywan/docker-php-webman:8.1.10
```

### php info

```shell
 sudo podman exec -it webman /bin/sh
 php -i |grep php.ini
 php -i |grep opcache
 php -m                                                                                                           
```

### Windows

```
docker run --rm -it -p 8787:8787 -v e:/dnmp/www/webman:/app tinywan/docker-php-webman
```

Test Run

![docker-run.png](./docker-run.png)

> PHP Version **8.1.4**

![image](https://user-images.githubusercontent.com/14959876/159652489-7df26dcb-b5e7-4f31-be96-3ecb63f3f7c5.png)

> **status**

![image](https://user-images.githubusercontent.com/14959876/159652735-86540cab-33c3-4b75-a0b7-41071300ee75.png)

## Extensions

```
bash-5.1# php -m
[PHP Modules]
bcmath       
bz2
calendar     
Core
ctype        
curl
date
dom
event        
fileinfo     
filter       
ftp
gd
hash
iconv        
json
libxml       
mbstring     
mysqli       
mysqlnd      
openssl      
pcntl        
pcre
PDO
pdo_mysql    
pdo_sqlite   
Phar
posix        
readline     
redis        
Reflection   
session      
SimpleXML    
soap
sockets      
sodium       
SPL
sqlite3      
standard     
tokenizer
xml
xmlreader
xmlwriter
Zend OPcache
zip
zlib

[Zend Modules]
Zend OPcache
```

## Other

delete all container

```
docker rm `docker ps -a -q`
```

delete all images

```
docker rmi -f $(docker images -qa)
```
