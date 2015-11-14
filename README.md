# Docker Alphine Harp

[![Docker Repository on Quay.io](https://quay.io/repository/technotycoon/alpine-harp/status "Docker Repository on Quay.io")](https://quay.io/repository/technotycoon/alpine-harp)

Minimal 125mb [HarpJS](http://harpjs.com) Microcontainer leveraging the [Alphine Linux](https://github.com/gliderlabs/docker-alpine)

## Base Docker Image

* [ficusio/nodejs-base](https://registry.hub.docker.com/u/ficusio/nodejs-base/)
* [alphine](https://registry.hub.docker.com/_/alpine/)

## Usage

From Quay.io

    docker run --rm quay.io/technotycoon/alphine-harp:latest harp --version

or Docker Hub

    docker run --rm technotycoon/alphine-harp:latest harp --version

## Why Squash?

Due to this Node-Sass/Alphine Linux issue https://github.com/sass/node-sass/issues/808, node-sass binary needs to be re-compiled.
Dependency packages such as `python, make and g++` are pulled down to build `node-sass`, therefore they need to be cleaned up and squashed using:

    docker export <layered container> | docker import – <squashed image>
