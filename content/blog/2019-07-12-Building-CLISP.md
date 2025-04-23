
---
layout: post
title: building CLISP
tags: ['clisp','compiling-clisp']
catagories: [CLISP, building, gitlab]
---
# Building CLISP on gitlab

Attempt to build CLISP on gitlab as a CI project.

## Multiple platform support.

CLISP can be built on many platforms. Among them are

* Windows
    *	MSC
    *   mingw64 - a Unix
    *   cygwin  - a Unix
* MacOS - I don't have this.
* Unix
    *   Linux
    *   FreeBDS

## CLISP documentation

### For Windows - install.WINDOWS
### For UNIX - unix/INSTALL
### For Porting general - unix/PLATFORMS

## General Approach for docker build

* Create a base platform with all needed dependecies
* Do the configure and build
* Do the tests.
* Export the build artifacts

## Each platform is defined by a key string

The build tools are a large case statement based on the key string, or perhaps there is a key.platform statement which tells the specific build conditions and methods.
