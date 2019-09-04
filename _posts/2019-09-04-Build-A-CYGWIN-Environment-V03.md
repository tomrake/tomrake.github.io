---
layout: post
title: Build a CYGWIN environment in docker Rev 03.
catagories: [cygwin, docker, base-environment, appium]
---
## This view is of a higher level

To allow docker *process isolation* of our target container we start with a specific version container. It is desired that this process will work for all relased OS versions.

## Using GUI Install of a component...

Large complexities of any scripted **GUI install**, require a design period to create extract the necessary remote element info from the GUI, an install method design and debug process, an **orchestraion design** from the **GUI install toolkit**.


## ... or not

Downloads of installers with command line execution using docker.
Copying of files and folders using docker.


### 1) Start with a base container.

### 2) Crete a WinAppDriver enabled container.

Using the **WinAppDriver Install Process** is expected to be non-GUI.

### 3) A docker container with a base CYGWIN installed

Download the base cygwin installer, a non-GUI operation.

Install cygwin base - a GUI operation.

## At this point decide on apt-cyg v. more GUI install

There is a choice to use a externally developed script to update installed cygwin packages. The trade-offs are depend on a large bash like shell script or invest  in time to construct a  complex javascript based GUI install. Or to furthor invest in a LISP based WinAppDriver client.

apt-cyg is a command line like cygwin updater given a package list and the install can is done.

The navigation of the CYGWIN GUI to install a package list could be a very complex script. This put the entire process under our control.

