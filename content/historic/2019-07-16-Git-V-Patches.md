---
layout: post
title: git V the Patch
catagories: [git, patch, mingw-64, git-for-windows,impedence-missmatch]
---
# How to well meaning team got into a conflict

Git for Windows is based on it's own code on the msys2/mingw-64 code base.
The msys2/mingw-64 team uses a patched based contribution system to rebuild it's system.
The msys2/mingw-64 system is built as a series of packages, by a recipe which includes patching of the source code at build time.

Git for windows includes many of the same tool but builds them from a single git repository.
