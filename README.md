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
advantages of octohook. See sections 3 and 4 for detailed instructions and
examples.

## Overview

By default, the Git hooks are living in the ``$GIT_DIR/hooks``. By default,
Git populates this directory with a bunch of example scripts, many of which
are useful by themselves; but they also document the input values of each
script. All the examples are written as shell scripts, with some Perl thrown
in, but any properly named executable scripts will work fine — you can write
them in Ruby or Python or what have you.

The idea behind octohook is to substitute default git hooks with itself and
let the user manage and customized which hook have to run when. To be more
evil than evil, octohook allow to set hooks for hooks — more details on that
later.

### Directory layout

Octohook will look for hooks in ``$OCTOHOOK_FOLDER``, which by default point to
``$XDG_CONFIG_HOME`` (which by default should point to ``$HOME``). Then the
directory structure will look like :

    $HOME
    |-- $XDG_CONFIG_HOME (defaults to $HOME/.config)
    |   |-- git
    |   |   |-- hooks.d
    |   |   |   |-- pre-commit
    |   |   |   |   |-- mvn-test.sh
    |   |   |   |   `-- some-ruby-script.rb
    |   |   |   |-- prepare-commit-msg
    |   |   |   |-- post-checkout
    |   |   |   |-- post-commit
    |   |   |   |-- post-merge
    |   |   |   `-- […]
    |   |   `-- […]
    |   `-- octohook
    |       `-- config
    ˙-- […]


