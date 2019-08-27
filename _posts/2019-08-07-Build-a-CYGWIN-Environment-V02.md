---
layout: post
title: Build a CYGWIN environment in docker Rev 02.
catagories: [cygwin, docker, base-environment, appium]
---
# Construct a base cygwin docker environment


## Appium install method

Using Appium and inspect.exe script can be written to automate the cygwin download and install.

Phase one is to test that a target can be build, where the source is my machine the appium host. The cygwin image is copied to the target machine from my build host.

Phase two is to see if the build can be done on the target machine directly.

Phase three is to have the appium host in a separate docker container.

### systems needed for Appium install method.

- appium host - Node.js host which includes the Appium server.
- target - the docker container being built.
- cygwin install host - this may be the target host or a separate host.

## The base docker image is use to build up the base cygwin image.

The basic method is to choose a windows base environment, next
interactively install cygwin in a host directory, use `https://www.cygwin.com/setup-x86_64.exe`. This image can be downloaded by `System.Net.WebClient` see [https://blog.jourdant.me/post/3-ways-to-download-files-with-powershell](https://blog.jourdant.me/post/3-ways-to-download-files-with-powershell).
Appium is used to execute and install the cygwin base packages plus any other desired packages.

Install apt-cyg from `https://github.com/ilatypov/apt-cyg/blob/master/apt-cyg` in the docker image. The powershell method used to download the cygwin installer can be used to get the apt-cyg fils.
Using docker create an image with the cygwin host directory copied to the guest docker image: use `docker cp`

## Using this process an image was created

[https://cloud.docker.com/u/tomrake/repository/docker/tomrake/cygwin](https://cloud.docker.com/u/tomrake/repository/docker/tomrake/cygwin)

## Next iteration

Need to add a normal user.