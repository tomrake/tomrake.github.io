---
title: Scope and Extent of LISP Bindings
layout: post
catagoies: [Common LISP,specification]
---
## Dynamic variables

Early versions of LISP had Dynamic variables.
This distinguished those variable from the Static ones which are largely fixed.
Things were fairly simple under this scheme but more complex for the programmers.

## Lexical variable and Closures

Later LISPs developed "lexical" bindings where the scope of the variables was limited by enclosing forms with in the text of LISP code, lexical is borrowed from the lexical analsys phase of compilers.

## Scope
Scope defines how a symbol defined in the code text can be referenced.
LISP though *LET* forms bind symbol within the body of the LET.