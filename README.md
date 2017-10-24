
# Installation of Docker

Installation of docker on Ubuntu 16.04
---

Add the repository to Ubuntu:

```sh
$ sudo apt-get install apt-transport-https ca-certificates


$ sudo apt-key adv \
                --keyserver hkp://ha.pool.sks-keyservers.net:80 \
                --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
$ sudo apt-get update
```

Add another repository by editing this file `$ sudo gedit /etc/apt/sources.list`

```sh
# for ubuntu 16.04
deb https://apt.dockerproject.org/repo ubuntu-xenial main

# for ubuntu 15.10
deb https://apt.dockerproject.org/repo ubuntu-wily main
```

**PS:** Please be noted that if a run of `sudo apt-get update` returns errors, so please delete that line `deb https://apt.dockerproject.org/repo ubuntu-xenial main` in `/etc/apt/sources.list`.

Install docker:

```sh
$ sudo apt-get update
$ sudo apt-get install docker docker-engine
# the package docker-compose will not be installed through apt-get since the latest available version on ubuntu 16.04 is the version 1.5
# the minimum needed version for docker-compose 1.8
```

Test if docker is working correctly?
---

```sh
$ sudo docker run hello-world
# Unable to find image 'hello-world:latest' locally
# latest: Pulling from library/hello-world
# c04b14da8d14: Pull complete
# Digest: sha256:0256e8a36e2070f7bf2d0b0763dbabdd67798512411de4cdcf9431a1feb60fd9
# Status: Downloaded newer image for hello-world:latest
#
#
# Hello from Docker!
# This message shows that your installation appears to be working correctly.
#
#
# To generate this message, Docker took the following steps:
#  1. The Docker client contacted the Docker daemon.
#  2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
#  3. The Docker daemon created a new container from that image which runs the
#     executable that produces the output you are currently reading.
#  4. The Docker daemon streamed that output to the Docker client, which sent it
#     to your terminal.
#
#
# To try something more ambitious, you can run an Ubuntu container with:
#  $ docker run -it ubuntu bash
#
#
# Share images, automate workflows, and more with a free Docker Hub account:
#  https://hub.docker.com
#
#
# For more examples and ideas, visit:
#  https://docs.docker.com/engine/userguide/
```

Start the docker service under ubuntu 16.04
---

```sh
$ sudo service docker start
# for the version of linux older 14.04, starting the service will be as follows:
# $ sudo /etc/init.d/docker start
```
Give the privilege to create docker image and run it
---

```sh
$ sudo usermod -aG docker $(whoami)
```

Restart the session or restart the computer to finalize the activation of the privilege
---

Create the simplest project on Docker
---

Create a directory for the docker projects:



Commands to know
---

```sh
# getting the list of the images
$ docker images
#REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
#hello-docker        latest              3dcf8710657f        4 minutes ago       402.6 MB
#php                 7.0-apache          336e2be8a343        2 weeks ago         402.6 MB

# getting the list of the images IDs only
$ docker images -q
#3dcf8710657f
#336e2be8a343

# getting the list of containers (active and non active containers)
$ docker ps -a

# getting the list of containers IDs (active and non active containers)
$ docker ps -a -q

# getting the list of containers (active only)
$ docker ps

# deleting an image
$ docker rmi <image-id>

# deleting an container
$ docker rm <container-id>
```
