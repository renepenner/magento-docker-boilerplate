# Magento-Docker-Boilerplate

A very basic docker/composer Infrastructure Setup to start a develop machine in seconds.

## Install

follow the instructions below:

```
git clone https://bitbucket.org/renepenner/magento-boilerplate
cd magento-boilerplate
composer install
docker-compose up -d
# wait some seconds mysql need to startup fist time

echo "192.168.99.100 magento-boilerplate.local" >> /etc/hosts
```

Check your Browser on http://magento-boilerplate.local/ ... at the fist time
Magento needs to create the database from upgrade scripts. This can take some
seconds. In my case (Mac Book Pro late 2011) it takes 23 seconds.


## Requirements

following tools should be installed on the host machine.

- docker
- docker-machine
- docker-compose
- php
- composer

### mac os x

  download and install [docker](http://docs.docker.com/engine/installation/mac/)

#### docker-machine-nfs

Use NFS instead of VirtualBoxShares.

- install [github/docker-machine-nfs](https://github.com/adlogix/docker-machine-nfs)
- create docker-machine-nfs follow instructions
- Open ``/etc/exports`` and replace ``-mapall=$uid:$gid`` with ``-maproot=0``
- ``sudo nfsd restart``
