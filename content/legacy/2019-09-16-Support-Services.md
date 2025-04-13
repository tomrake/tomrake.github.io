---
title: Local Support Services Design
layout: post
catagories: [support, virtualization, docker]
---

# Redesign for reliablity

## Current useage

- Main Client uses a FileHistoryHost volumn and a Bugzilla server
- FileHistoryHost is a shared Windows Volumn from the host.
- FileHistoryHost also run a VirtualBox.
- A VM debian is run on the VirualBox.
- VM debian runs a Bugzilla service.
- VM debian runs a MariaDB service.
- Bugzilla service uses MariaDB as a store.
- VM debian does backup the Bugzilla database to FileHistory Host.
- Former Main Client needs Fan Repair.

## BlueSky Wishes

- Backup as a service with switchable archive servers
- MariaDB in separate VM or container
- Bugzilla in separate VM or container
- A development build service - likely [Gitlab Runner](https://docs.gitlab.com/runner/) based.