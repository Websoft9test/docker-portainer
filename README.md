# Portainer on Docker

![](https://libs.websoft9.com/common/websott9-cloud-installer.png) 

## Introduction

[English](/README.md) | [简体中文](/README-zh.md)  

This repository is an **Cloud Native solution** powered by [Websoft9](https://www.websoft9.com), it simplifies the complicated installation and initialization process.  

## System Requirements

The following are the minimal [recommended requirements](https://documentation.portainer.io/v2.0-be/deploy/requirements/):

* **OS**: Red Hat, CentOS, Debian, Ubuntu or other's Linux OS
* **Public Cloud**: More than 20+ major Cloud such as AWS, Azure, Google Cloud, Alibaba Cloud, HUAWEIClOUD, Tencent Cloud
* **Private Cloud**: KVM, VMware, VirtualBox, OpenStack
* **ARCH**:  Linux x86-64, ARM 32/64, Windows x86-64, IBM POWER8, x86/i686
* **RAM**: 4 GB or more
* **CPU**: 2 cores or higher
* **HDD**: at least 20 GB of free space
* **Swap file**: at least 2 GB
* **bandwidth**: more fluent experience over 100M  

## QuickStart

### All-in-one Installer

Use SSH to connect your instance and run the automatic installation script below

```
sudo wget -N https://raw.githubusercontent.com/Websoft9/StackHub/main/docker-installer.sh; sudo bash docker-installer.sh -r portainer
```
### package install

1.Make package
You can get the  package as following script
```
sudo wget -N https://raw.githubusercontent.com/Websoft9/StackHub/main/docker-installer.sh; sudo bash docker-installer.sh -r portainer -p
```

2.Install by package
Copy package to your server, Use SSH to connect your instance and run the automatic installation script below
```
sudo bash install-portainer
```

### Manual Installation

#### Preparation

If you have not install Docker and Docker-Compose, refer to the following commands to install it:

```
curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh
sudo systemctl enable docker
sudo systemctl start docker
alias docker-compose='docker compose'
echo "alias docker-compose='docker compose'" >> /etc/profile.d/docker-compose.sh
source /etc/profile.d/docker-compose.sh
```

#### Install Portainer

We assume that you are already familiar with Docker, and you can modify [docker-compose file](docker-compose.yml) by yourself

```
git clone --depth=1 https://github.com/Websoft9/docker-portainer
cd docker-portainer
docker network create websoft9 
docker compose  up -d
```

### FAQ

#### Do I need to change the password before docker-compose up?
Yes, you should modify all database password and application password at docker-compose file for production

#### Docker runing failed for the reason that port conflict?
You should modify ports at [docker-compose file](docker-compose-production.yml) and docker-compose again

### Usage instructions

You can point your browser to: *`http://Instance's Internet IP:port`*  

The following is the information that may be needed during use

#### Services and Ports

| Service | Port | Use |  Necessity |
| --- | --- | --- | --- |
| portainer | 9091 | Visit Portainer through browser | Y |
## Documentation

[Portainer Administrator Guide](https://support.websoft9.com/docs/portainer)

## Enterprise Support

If you want to get our Enterprise Support to ensure high availability of applications, you can subscribe our [Portainer Enterprise Support](https://apps.websoft9.com/portainer) 

What you get with a Enterprise Support subscription?

* Knowledge: Answers and guidance from product experts
* Support: Everything you need for technical support, e.g Enable HTTPS, Upgrade guide
* Security: Security services and tools to protect your software
