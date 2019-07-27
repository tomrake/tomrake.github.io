---
layout: post
title: Build a CYGWIN environment in docker.
catagories: [cygwin, docker, base-environment]
---
# Construct a base cygwin docker environment

The basic method is to choose a windows base environment, next
interactively install cygwin in a host directory, use `https://www.cygwin.com/setup-x86_64.exe`
Using docker create an image with the cygwin host directory copied to the guest docker image: use `docker cp`
Install apt-cyg from https://github.com/ilatypov/apt-cyg/blob/master/apt-cyg in the docker image.