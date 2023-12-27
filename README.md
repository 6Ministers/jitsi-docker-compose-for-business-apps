# Installing Jitsi with docker-compose.

## Quick Installation

**Before starting the instance, direct the domain (subdomain) to the ip of the server where Jitsi will be installed!**

## 1. Jitsi Server Requirements
From and more
- 2 CPUs
- 2 RAM 
- 10 Gb 

Run for Ubuntu 22.04

``` bash
sudo apt-get purge needrestart
```

Install docker and docker-compose:

``` bash
curl -s https://raw.githubusercontent.com/6Ministers/jitsi-docker-compose-for-business-apps/master/setup.sh | sudo bash -s
```

If `curl` is not found, install it:

``` bash
$ sudo apt-get install curl
# or
$ sudo yum install curl
```


Download Jitsi instance:

``` bash
git clone https://github.com/jitsi/docker-jitsi-meet jitsi
```

Go to the catalog
``` bash
cd jitsi
```

Download Jitsi `.env`:
``` bash
wget  https://raw.githubusercontent.com/6Ministers/jitsi-docker-compose-for-business-apps/master/.env
```

In the configuration file `.env`, set the following parameters:

Install what you need, documentation:

https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker/

https://github.com/jitsi/docker-jitsi-meet/blob/master/env.example

``` bash
HTTP_PORT=80
HTTPS_PORT=443
CONFIG=/opt/jitsi-meet-cfg
ENABLE_LETSENCRYPT=1
LETSENCRYPT_DOMAIN=https://www.yourdomain.com
TZ=Europe/Moscow
PUBLIC_URL=https://www.yourdomain.com
JVB_ADVERTISE_IPS=127.0.0.1
ENABLE_HTTP_REDIRECT=1
ENABLE_HSTS=1 
```
and other...

``` bash
docker-compose up -d
```

**Run Jitsi:**

``` bash
docker-compose up -d
```

Then open `https://jitsi.domain.com:` to access Jitsi


## Jitsi container management

**Run Jitsi**:

``` bash
docker-compose up -d
```

**Restart**:

``` bash
docker-compose restart
```

**Restart**:

``` bash
sudo docker-compose down && sudo docker-compose up -d
```

**Stop**:

``` bash
docker-compose down
```

## Documentation

https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker/

https://github.com/jitsi/docker-jitsi-meet/blob/master/env.example

https://linuxhandbook.com/self-host-jitsi-meet/
