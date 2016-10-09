Unofficial Autodesk Backburner
==============================
[![Docker Automated buil](https://img.shields.io/docker/automated/haysclark/backburner.svg?maxAge=2592000)](https://hub.docker.com/r/haysclark/backburner/builds/)

A simple Docker container that runs Autodesk Backburner.

The container is setup to support all or just one of the following services:
 - Backburner Manager
 - Backburner Server
 - Backburner Web

Usage
-----

    docker run -d haysclark/backburner

Typically you will want to append the following port forwarding information depending what service you are running:

 - Backburner Manager: ```-p 3234:3234```
 - Backburner Web ```-p 8080:80```
 - Backburner Server ```-p 3233:3233```

E.G. if you want to run the Manager and Monitor you would execute:

    docker run -d -p 3234:3234 -p 8080:80 haysclark/backburner

Setup
-----

Log into the docker container

    docker exec -it [CONTAINER_ID] /bin/bash

Setup Backburner

    ./backburnerConfig

Setup of Backburner Web Monitor

	./backburnerConfigWeb

Adding a user

	htpasswd /etc/httpd/auth/backburner.auth [USER_NAME]

Resources
------------
[Official backburner User Guide](http://download.autodesk.com/us/systemdocs/pdf/backburner2011_user_guide.pdf)
[Getting BackBurner Manager and Monitor Running on Linux](https://www.youtube.com/watch?v=UKOr1R6tO34)
