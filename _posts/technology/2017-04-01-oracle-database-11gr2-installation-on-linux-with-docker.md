---
title: Oracle Database 11g R2 installation on Linux with Docker
date: 2017-04-01
categories:
- technology
layout: post
description: Installing Oracle Database 11g R2 with Docker on Linux is pretty easy and saves time and effort. In a matter of few minutes, you will have your Oracle database up and running and you can use it at your ease.
image: "/assets/docker.jpg"
---
<img src="/assets/docker.jpg" alt="Docker and Oracle 11gr2">

Recently, I came to know about **Docker** from my friends and I tried installing Oracle Database through Docker, this blog post is a small note on installing Oracle database 11gR2 on Linux machine. I am writing this thinking it would be easy for myself for future references and others who seek for such blog posts.

Installing **Oracle Database 11g R2** with Docker on Linux is pretty easy and saves time and effort. In a matter of few minutes, you will have your Oracle database up and running and you can use it at your ease.

I did this installation on Fedora 25, and no matter what distro you are using it is totally same across all.

To install Oracle Database 11g R2 with Docker, proceed with following steps:


## A. Docker Installation##
Installing docker is easy and quick. I installed Docker Community Edition (CE) on Fedora. You can find the installation instruction step by step for your system in Docker's official documentation. <a href="https://docs.docker.com/engine/installation/" target="blank"> Click here</a>

In my case, I followed the following steps for fedora:

### setting up the repository###

install the `dnf-plugins-core` package as it provides commands to manage repositories

	sudo dnf -y install dnf-plugins-core

lets setup the stable repository

	sudo dnf config-manager \
    --add-repo \
    https://download.docker.com/linux/fedora/docker-ce.repo

enable egde repository(optional)

	sudo dnf config-manager --enable docker-ce-edge

### Installing Docker CE###

first, lets **update the dnf package index**

	sudo dnf makecache fast

now, lets proceed by **installing latest version of Docker**

	sudo dnf install docker-ce

### Starting Docker###

	sudo systemctl start docker

### Verifying Installation ###
We can verify if Docker CE is installed correctly by running the `hello-world` image.

	sudo docker run hello-world

By now, we will have Docker installed in our system. We need to use `sudo` to run Docker Commands. If you have any errors or need full details please refer to Docker's official [site](https://docs.docker.com/engine/installation/linux/fedora/#install-using-the-repository).

## B. Oracle Database 11g R2 Installation##

 For installing Oracle Database on Docker, I followed [these](https://github.com/wnameless/docker-oracle-xe-11g) instruction from Github repo.

**installation**

	docker pull wnameless/oracle-xe-11g

 or for older Ubuntu 14.04.4
	
	docker pull wnameless/oracle-xe-11g:14.04.4

and,

	docker run -d -p 49160:22 -p 49161:1521 wnameless/oracle-xe-11g

to make ports 22 and 1521 opened

You might need to stop running Docker while proceeding installing Oracle installation commands

	docker stop [OPTIONS] CONTAINER [CONTAINER...]

example:
	 
	 docker stop container_name

to **list containers**

	sudo docker container ls

 if wanted to connect remotely,

	docker run -d -p 49160:22 -p 49161:1521 -e ORACLE_ALLOW_REMOTE=true wnameless/oracle-xe-11g

Now, **start your Docker**,

	sudo systemctl start docker

**Loging with SSH**

	ssh root@localhost -p 49160
	password: admin

**Connecting with Database**
	
	hostname: localhost
	port: 49161
	sid: xe
	username: system
	password: oracle

Password for SYS and SYSTEM

	 oracle



And now, your are good to go, and start using Oracle Database 11g R2 on your linux machine with Docker.

To access database, you need to login with

	ssh root@localhost -p 49160

in new session.

`sqlplus` command can be used to start doing database operations.

<small>I am learning Oracle recently, I might write more about Oracle Databases and some useful notes. Do check back later. :)</small>