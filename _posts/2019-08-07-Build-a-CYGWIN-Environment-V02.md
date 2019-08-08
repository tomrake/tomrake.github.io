---
layout: post
title: Build a CYGWIN environment in docker Rev 02.
catagories: [cygwin, docker, base-environment, appium]
---
# Construct a base cygwin docker environment

## systems needed

- Node.js host which includes the Appium server.
- target - the docker container being built.
- cygwin install host - this may be the target host or a separate host.

The basic method is to choose a windows base environment, next
interactively install cygwin in a host directory, use `https://www.cygwin.com/setup-x86_64.exe`. This image can be downloaded by `System.Net.WebClient` see [https://blog.jourdant.me/post/3-ways-to-download-files-with-powershell](https://blog.jourdant.me/post/3-ways-to-download-files-with-powershell).
Appium is used to execute and install the cygwin base packages plus any other desired packages.

Install apt-cyg from `https://github.com/ilatypov/apt-cyg/blob/master/apt-cyg` in the docker image. The powershell method used to download the cygwin installer can be used to get the apt-cyg fils.
Using docker create an image with the cygwin host directory copied to the guest docker image: use `docker cp`

## Using this process an image was created

[https://cloud.docker.com/u/tomrake/repository/docker/tomrake/cygwin](https://cloud.docker.com/u/tomrake/repository/docker/tomrake/cygwin)

## Next iteration

Need to add a normal user.