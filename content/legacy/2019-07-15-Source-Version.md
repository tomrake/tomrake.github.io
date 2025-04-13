---
layout: post
title: Report on source containers
catagories: [report, source, git, gitlab]
---

# Report on source updating.

A gitlab rebuild is in response to a branch push.

# Report on building prototype

An example prototype of a CLISP build system could be libsigsegv

* Prerequisite to CLISP
* Multi platform - release artifacts are
* Git hosted on savanah


# How the build(s) are structured

* There is a build interface
* There are instances of Runner for each artifact target.
* Each runner has a tag - the tag is platform/artifact type.

