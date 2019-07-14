---
layout: post
title: building CLISP - Dependencies
catagories: [CLISP, building, docker, dependencies]
---
# Building CLISP dependencies.

## Design a general build process.
* Specify requirements
* build a prototype
* report considerations
* is it suffiencent?
    * Yes - move to a release build
    * No - Report; modify requirement and iterate


### Requirements

* artifacts in a docker volume

    * Where docker can find it.
    * Can gitlab find it too?

* source in a docker volume
    * source means current source
    * The source is updatable
    * The source is versionable
    * docker issues ??
    * gitlab issues ??

* build log is accessable
    * This is for the build level
        * Success - for deep debug
	* Failure - for debug

* docker considerations
    * research
    * report    

* gitlab considerations
    * research
    * report

* versioning considerations
    * research
    * report

* multi-platform considerations
    * Just try and then unify
    * report
