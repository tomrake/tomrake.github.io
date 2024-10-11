---
layout: post
title: Build a CYGWIN environment in docker Rev 03.
catagories: [cygwin, docker, base-environment, appium]
---
## This view is of a higher level

To allow docker **process isolation** of our target container we start with a specific version container. It is desired that this process will work for all relased OS versions.

## Using GUI Install of a component...

Large complexities of any scripted **GUI install**,
require a design period to create extract the necessary GUI element info,
an install method design and debug process,
an **orchestraion design** using **GUI install toolkit**.


## ... or not

Downloads of installers with command line execution using docker.
Copying of files and folders using docker.

# The Overview of the building process

### 1) Start with a base container.

Choose a container version that can be used with docker --isolation=process.
The derived containers will use less resources,
there is a security trade-off in this decision.

### 2) Create a WinAppDriver enabled container.

Using the **WinAppDriver Install Process** is expected to be non-GUI.

### 3) A docker container with a base CYGWIN installed

Download the base cygwin installer, a non-GUI operation.

Install cygwin base - a GUI operation.

## At this point decide on apt-cyg v. more GUI install

There is a choice to use a externally developed script to update installed cygwin packages. The trade-offs are depend on a large bash like shell script or invest  in time to construct a  complex javascript based GUI install. Or to furthor invest in a LISP based WinAppDriver client.

apt-cyg is a command line like cygwin updater given a package list and the install can is done.

The navigation of the CYGWIN GUI to install a package list could be a very complex script. This put the entire process under our control.


# Status of support methods


- orchestration design, still in exploration or **hacking** phase.
- GUI Install toolkit, about 70% hacked, javascript based.
- GUI Install toolkit, GUI element extraction had been in (POC) proof of concept for weeks.
- GUI Install toolki in LISP, about 10% hacked.
- apt-cyg install is an alpha product.
- docker, download and script install are 90% POC


# Update of design
`setup-x86_64.exe` has a the `-P package1,package2,package3, ... packageN` format, this can be used in CMD mode to install cygwin and additional packages.

Now `setup-x86_64.exe` needs to be downloaded from a website, `https://cygwin.com/setup-x86_64.exe`. Using Powershell and System.NetWebClient

```
$url = "https://cygwin.com/setup-x86_64.exe"
$output = "/setup-x86_64.exe"

$wc = New-Object System.Net.WebClient
$wc.DownloadFile($url, $output)
```


