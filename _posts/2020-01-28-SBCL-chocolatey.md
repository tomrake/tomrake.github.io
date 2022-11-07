---
layout: post
title: SBCL on Windows, where is chocolatey package?
catagories: [lisp, sbcl, windows, chocolatey]
---
## There is no current Chocolatey package from SBCL!

SBCL 2.0.0 on 12/29/2019 which include a windows installer.
There is a homebrew package for SBCL (see https://formulae.brew.sh/formula/sbcl#default ) so MacOS has a current SBCL.
When you check for Chocolatey package from SBCL (see https://chocolatey.org/packages/sbcl ) you find a package had a error 5 years ago.

## The old chocolatey package is not maintained.

A new chocolatey package should be created and a maintence procedure should be created.
The best strategy is to introduce a script chocolatey release script into the SBCL release code in the SBCL build source code.

