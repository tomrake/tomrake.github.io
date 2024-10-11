---
layout: post
title: Run sbcl, mingw64 version, from emacs slime.
---
## Make mingw64/sbcl run from slime.

In a previous post I created a sbcl which runs from the mingw64 shell. When I run sbcl from the ming64 prompt all works as expected but running it from CMD causes sbcl to complain that the core was built for another runtime.

This problem has two potential solutions:

* 1) Compile sbcl with CMD runtime.
* 2) Start a bash login shell and run sbcl programatically.

Option 1) requires I study the make process and possible build SBCL under MSYS2 by directing make to use mingw64 gcc.

Here is my current solution for option 2)

```lisp
(defun lisp-mingw64-implementation-4 (tag)
  `(,tag (,(concat +msys64-base-path+ "usr/bin/env.exe") "MSYSTEM=MINGW64"
	  ,(concat +msys64-base-path+ "usr/bin/bash.exe") "-l" "-c" "/usr/local/bin/sbcl" "--noinform")))


(setq slime-lisp-implementations
      `(,(when (file-exists-p (concat +msys64-base-path+ "/usr/local/bin/sbcl.exe"))
	   (lisp-mingw64-implementation-4 'mingw64-sbcl))))

```

lisp-mingw-implementation-4 where env create an enviroment with MSYSTEM=MINGW64 in that enviroment bash is created as a login shell, which initialized a series of things. next sbcl is launched by that bash shell with appropriate parameters.