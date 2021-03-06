---
title: Making zshell load faster on start
date: 2018-01-07T18:06:49-05:00
tags:
  - zsh
  - nvm
  - node
---
I spent two hours speeding up my Zsh's awful init time. After quite a bit of researching on both Zsh and some related plugins, I found the command `zsh -xv` could verbosely log all the loading files during a start. And the monster that was jamming this part is nvm, the node virtual machine manager.

Apparently, nvm needs to be loaded on every instance for referencing the commands and scripts, which is way more than other virtual environment managers like `rvm` or `pyenv`.

Though I found the reason, it was hard for me to uninstall nvm entirely since Node.js is now in many of my projects looking for a specific version controlled by nvm. But as a terminal guy, who probably open 50 terminals a day, 3s each is not acceptable.

My final solution is aliasing the loading commands by a short macro whenever I need Node to execute.

The start time now shortens to 1 second, which feels way more comfortable.