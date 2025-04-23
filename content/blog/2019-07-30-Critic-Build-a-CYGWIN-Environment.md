---
title: Critic of Build a Cygwin Environment - Cycle 1
layout: post
catagories: [cygwin, docker, base-environment, critic]
---
# This Critic closed see Cycle 2

# Critic of Build a CYGWIN environment in docker.

## AddUser needs debugging, fails to work as expected

## Build the base CYGWIN environment.

### UI Automation

[UI Automation](https://docs.microsoft.com/en-us/windows/win32/winauto/uiauto-usefortesting) is an automation tools for Windows UI. Can a powershell script build the base CYGWIN image?

* Can this be done in the docker windows image? likely no.
* Can cygwin install be automated? likely yes.

## UIAutomation.dll how to get it?

### Best Instructions

The UIAutomation.dll file is in a cryptic named file which need to be extracted.
The best instructions for how are at [https://community.spiceworks.com/how_to/160771-how-to-obtain-and-install-uiautomation-dll](https://community.spiceworks.com/how_to/160771-how-to-obtain-and-install-uiautomation-dll).

### Additional Instuctions for Unblocking Internet origin files.

Powershell will taint all internet origin files and refuse to execute them you must Unblock each file to use it.
Where every the downloaded files for UIAutomation are to be used, rather `Import-Module UIAutomaion.dll` you must do an `Unblock-File UIAutomaion.dll`. I actually expand the entire NET4.0 distribution into a `UIAutomation\NET40` and then
```
cd UIAutomation\NET40
dir | Unblock-File
```
to Unblock all files in the directory.

### How do I automate these the install process?

# The first iteration is over

- Set next interation.
- Restate the CYGWIN enviroment for testing and building
- Consider using Selenium / Appium tool
