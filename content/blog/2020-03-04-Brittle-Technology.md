---
layout: post
title: The Brittle Nature of Technology
catagories: [tech,software]
---
# Software is brittle
A change of a single character in the source code can cause a failure.
When debugging these type brittle errors are fixes.
It is only with testing to address the brittle points that software can become useful.

# Software systems can be brittle

The inspiration for this post is the difficulties I am having using SBCL on Windows 10.
I have viewed SBCL as a unix product with limited support for the Windows port.
Code has been contributed that assumes "the unix way" of thinking (should I say the New Jersey way?)

## The SBCL brittle points

My problem is that some foreign function and object conversions functions is SBCL give me problems on Windows 10. While I am focused on a possible deep problem of contribs overly focused on unix conventions is at the root of my problems, it could be that do not under stand the compiler technology well enough.

### Here is my unix focused convention outline.

SBCL has a concept called the grovel in sb-grovel, which is focused on foreign interfacing. The brittle points concern the binary interfacing done by SBCL itself and the layout of the foreign typed objects.

SBCL is largely written in LISP with binary sections written in C, the C conventions for binary layout are specified in C. Some C binary conventions are deterined by the C compiler.

LISP has elements that implement many low level binary constructs with fussy details that differ from C conventions.

Windows 10 has different OS structure vrs unix and these are the main focus of SBCL porting issues. When you add optimization to porting on differnt OS.

### LLVM focused tools

Some in the unix world have focused on the LLVM compiler technology, as a solution for automatic function definition. This approach has it's own brittle pointed related to changed in the version by version changes in AST format of the parsed code. In addition it fails to deals with the preprocessor problems inherent in with C code. On Windows this is a whole separate problem.