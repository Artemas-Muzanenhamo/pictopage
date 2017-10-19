# [Pictopage](http://pictopage.com)

[![Docker Automated buil](https://img.shields.io/docker/automated/artemas/pictopage.svg)](https://hub.docker.com/r/artemas/pictopage/)
[![Docker Build Statu](https://img.shields.io/docker/build/artemas/pictopage.svg)](https://hub.docker.com/r/artemas/pictopage/)
[![Build Status](https://travis-ci.org/Artemas-Muzanenhamo/pictopage.svg?branch=develop)](https://travis-ci.org/Artemas-Muzanenhamo/pictopage)
[![Docker Pulls](https://img.shields.io/docker/pulls/artemas/pictopage.svg?style=plastic)](https://hub.docker.com/r/artemas/pictopage/)

# About
This is a simple website for my [Pictopage](http://pictopage.com/) website.

## Deployment

I made up a simple Deployement workflow as below:
![image][deployment]

[deployment]: public-html/vendor/images/Pictopage.png

1. A push SCM **Github** triggers **DockerHub** to start testing and building the image.
2. Jenkins will poll **DockerHub** (Since I don't want to use Dockerhub's webhook because it communicates via HTTP only).
3. Jenkins will then run **Docker** on the server.
4. Docker will pull **image(s)** from **Dockerhub**.
5. Docker will stop the existing **image** and start up a new **container** instance of the new **image**.
6 The webpage will be rendering content of the new container instance !! :smirk:
