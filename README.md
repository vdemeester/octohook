# octohook

An advanced git hooks system.

## Introduction

Git offers a cool thing call [Git Hooks](http://git-scm.com/book/en/Customizing-Git-Git-Hooks). 
It's useful on servers (using [Gitolite](https://github.com/sitaramc/gitolite/)
for example), but it should be the same on the client side. This is where
octohook enters.

Octohook aims to be a powerful advanced hook system for git while being simple
to use and flexible. The first inspiration of octohooks comes from
[git-hooks](https://github.com/endorama/git-hooks).

Read INSTALL.md for detailed setup instructions.

The following overview will try to give you an idea of the use cases and
advantages of vcsh. See sections 3 and 4 for detailed instructions and
examples.

## Overview

By default, the Git hooks are living in the ``$GIT_DIR/hooks``.
