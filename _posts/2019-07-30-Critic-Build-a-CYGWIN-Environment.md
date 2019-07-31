---
title: Critic of Build a Cygwin Environment - Cycle 1
layout: post
catagories: [cygwin, docker, base-environment, critic]
---
# Critic of Build a CYGWIN environment in docker.

## AddUser needs debgging fails to work as expected

## Build the base CYGWIN environment.

### UI Automation

[UI Automation](https://docs.microsoft.com/en-us/windows/win32/winauto/uiauto-usefortesting) is an automation tools for Windows UI. Can a powershell script build the base CYGWIN image?

* Can this be done in the docker windows image? likely no.
* Can cygwin install be automated? likely yes.