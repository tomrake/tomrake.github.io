---
title: Appium, WinAppDriver design considerations
layout: post
catagories: [appium, winappdriver, windows, docker, cygwin]
---
In the redesign process for automation for cygwin in a docker container
the following needs to be considered.

## Considerations

- Appium or WinAppDriver based scripts
- The inclusion of WinAppDriver in target container.
- Configuration of WinAppDriver ports
- A developer language - Can I use common lisp?
- Scripting of automation

## Terms

- A Task a specified activity
- A Documented Structure a solution to Task.
- A Coded Structure a completely coded solution to a Task.

## Thoughts

- Proof of concepts demostrates how to perform a certain activity leading to
documentation and/or coding of a Task.
- Issues about ports and appium for direct WebAppDriver relate to "the stucture" of the proposed solution to a task.
- A Coded Structure is prefered over a Documented Structure.


## Resources

- [WinAppDriver Docs page](https://github.com/microsoft/WinAppDriver/tree/master/Docs)
- [WebAppDriver Docs on Appium or WebAppDriver](https://github.com/microsoft/WinAppDriver/blob/master/Docs/UsingAppium.md)
- [Common Lisp Selenium Tutorial](https://common-lisp.net/project/cl-selenium/tutorial.html)
