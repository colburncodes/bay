---
layout: post
title: "Build YOUR OWN Dockerfile, Image, and Container"
date: 2023-11-07 10:00:40
blurb: "A look at an example post using Bay Jekyll theme."
og_image: /assets/img/content/post-example/Banner.jpg
---

The goal is build our very own custom Docker container image.
And it will be from scratch, bare bones, with an empty Dockerfile, and
we will create, build, and run our very own custom Docker Image.

By doing so, My goal is to introduce you to some commands
when building and maintaining images with Docker.

But first let's understand:

- What is Docker?
- What is a Container?
- What is an Image?

### Install Docker

To install docker, see [Install Guide](https://docs.docker.com/engine/)

1. <b>What is a Container?</b> A Docker container is like a special box that contains everything a computer program needs to run, so it can work the same way on any computer. It's like a
   portable play-kit for software.

2. <b>What is an Image?</b> A Docker image is like a recipe or blueprint for a Docker container,
   telling it what to include and how it should behave. It's like having instructions for
   building a specific lego set.

### Docker commands

build image

```shell
docker build
```

build image with tag

```shell
docker build -t hello-web
```

list docker images

```shell
docker images
```

list docker containers

```shell
docker ps
```

list docker containers including stopped

```shell
docker ps -a
```

create container from image

```shell
docker run -d -p 80:80 <image id>
```

exec into running container

```shell
docker exec -it <container id> /bin/sh
```

stop running container

```shell
docker stop <container id>
```

remove a container

```shell
docker rm <container id>
```

remove an image

```shell
docker rmi <image id>
```
