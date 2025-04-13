---
layout: post
title: Update SBCL to 1.4.14
catagories: [sbcl, slime, emacs, update]
---
## Updating SBCL on Windows

Download the new installer, [http://prdownloads.sourceforge.net/sbcl/sbcl-1.4.14-x86-64-windows-binary.msi](http://prdownloads.sourceforge.net/sbcl/sbcl-1.4.14-x86-64-windows-binary.msi). Run the installer, the old SBCL is removed and the new one is installed. I had a few dll which I placed next to my sbcl.exe which remained in the old location. I moved these to the new location. The SBCL_HOME was also reset to the new location.

My .emacs file slime-lisp-implemenations is written in terms of SBCL_HOME so it, just works.

```cl
(setq slime-lisp-implementations
    `(  
	;; Add SBCL if present
	,(when (getenv "SBCL_HOME")
	   (cond ((eq system-type 'windows-nt)
		  `(sbcl  (,(convert-standard-filename (concat (getenv "SBCL_HOME") "sbcl.exe"))
			   "--noinform")))
		 (t nil)))
	;; Add more LISPs here..

	 ))
```