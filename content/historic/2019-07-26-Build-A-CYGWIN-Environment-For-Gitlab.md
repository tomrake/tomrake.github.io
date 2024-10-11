---
layout: post
title: Build a CYGWIN environment in docker.
catagories: [cygwin, docker, base-environment]
---
# Construct a base cygwin docker environment

The basic method is to choose a windows base environment, next
interactively install cygwin in a host directory, use `https://www.cygwin.com/setup-x86_64.exe`
Install apt-cyg from `https://github.com/ilatypov/apt-cyg/blob/master/apt-cyg` in the docker image.
Using docker create an image with the cygwin host directory copied to the guest docker image: use `docker cp`

## Using this process an image was created

[https://cloud.docker.com/u/tomrake/repository/docker/tomrake/cygwin](https://cloud.docker.com/u/tomrake/repository/docker/tomrake/cygwin)

## Next iteration

Need to add a normal user.