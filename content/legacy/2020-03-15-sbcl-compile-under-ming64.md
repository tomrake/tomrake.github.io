---
layout: post
title: Compile SBCL 2.0.0 under mingw64
---
## I am experimenting with a SBCL compiled for mingw64

I use [the Solarian Programmer's Guide](https://solarianprogrammer.com/2019/08/20/building-sbcl-steel-bank-common-lisp-windows/) to build SBCL under mingw64.
I am building the 2.0.0 from source.

I have MSYS2 installed at `C:\devel\msys64` which is `/c/devel/msys64` in MSYS2.

I have the binary windows distribution of SBCL 2.0.0 at `/c/devel/SBCL_2_0_0-bin` and I keep the sources at `/c/devel/SBCL_2_0_0-src` this includes the source.tar.bz2  the binary msi, as well as the expanded source.

I used these steps
at MSYS command line do:

```bash
pacman -Syu
```

Respond Y when asked for confirmation. When the updating is done close the MSYS2 window don't do an `exit`.

Restart a MSYS2 shell and do:

```bash
pacman -Syu


pacman -S mingw-w64-x86_64-toolchain

pacman -S bzip2

exit

```

I downloaded the binary `sbcl-2.0.0-x86-64-windows.msi` to `C:\devel\SBCL_2_0_0-src`. Next I installed the MSI at `C:\devel\SBCL_2_0_0-bin`, SBCL was not added to the PATH and SBCL_HOME was not set. 
I downloaded the raw source `sbcl-2.0.0-source.tar.bz2` to `C:\devel\SBCL_2_0_0-src`.


```bash
# SBCL 2.0.0 is used for compile
export PATH=/c/devel/SBCL_2_0_0:$PATH
export SBCL_HOME=/c/devel/SBCL_2_0_0

cd /c/devel/SBCL_2_0_0-src
tar xfj sbcl-2.0.0-source.tar.bz2

# Define GNUMAKE
export GNUMAKE=mingw32-make

# Enter the source directory and make

cd /c/devel/SBCL_2_0_0-src/sbcl-2.0.0
sh make.sh --prefix=/usr/local

# if no errors in build then install.

unset SBCL_HOME
sh install.sh
```

Use `sbcl` to start SBCL lisp on the mingw64 bash command line. You cannot launch sbcl directly from the CMD shell.