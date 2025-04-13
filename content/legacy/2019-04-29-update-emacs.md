---
layout: post
title: Update emacs to 26.2
catagories: [emacs, update, shortcuts]
---
## This is a Windows 10 system

My system is a Windows 10/64bit

## Download, expand and update EMACS_HOME

I downloaded the new emacs from the GNU ftp site. The file was [https://ftp.gnu.org/gnu/emacs/windows/emacs-26/emacs-26.2-x86_64.zip](https://ftp.gnu.org/gnu/emacs/windows/emacs-26/emacs-26.2-x86_64.zip)

The downloaded emacs zip was expanded into `C:\Program Files\Emacs\emacs-26.2-x86_64` this is my new `EMACS_HOME`.

## My shortcuts now all depend on EMACS_HOME

I have three shortcut for emacs, the daemon, the client and no-daemon.

For the daemon the shortcut target is:
```sh
 %EMACS_HOME%\bin\runemacs.exe --daemon 
```
and starts up in:
```sh
 %EMACS_HOME%
```
The client uses this target:
```sh
 %EMACS_HOME%\bin\emacsclientw.exe -na "%EMACS_HOME%\bin\emacsclientw.exe" -c -n
```
The non-daemon target is:
```sh
%EMACS_HOME%\bin\runemacs.exe --debug
```
