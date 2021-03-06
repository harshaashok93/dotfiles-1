********
DOTFILES
********

Welcome to my dotfiles.  You are very welcome to use them, but I recommend reading through each file before you try to setup your mac based on this setup.  What works for me, might not work for you.

Housekeeping
============

This setup is for OSX.  Tested on macOS 10.12 Sierra.

Before you run the install script, please make sure you complete the following steps:

**1.  Update macOS**

**2.  Install Xcode Command Line Tools**

.. code-block:: bash

    xcode-select --install

**3.  Setup diff-highlighter**

To use ``diff-highlighter`` you will have to reference the currently active global version of git.  This means, the path specified in the ``.gitconfig`` file may not be correct for your install of git.  To do this:

1.  Find diff-highlight

.. code-block:: bash

    find -L /usr -name diff-highlight -type f

2.  Choose the path with the larget git version

.. code-block:: bash

    /usr/local/Cellar/git/2.11.0/share/git-core/contrib/diff-highlight/diff-highlight

.. epigraph::

   You can tell by the number directly after git.  In the above path, it's `2.11.0`

3.  Replace the path on line 13 in the .gitconfig with the path from step 2.

.. code-block:: bash

    pager = /usr/local/Cellar/git/2.11.0/share/git-core/contrib/diff-highlight/diff-highlight | diff-so-fancy | less -r


**4.  .macOS paths**

step 3 is going to run the ``.macOS`` script which has preferences that this author prefers, the following is a list of paths that I use that you may want to change before you run the init script:

section - iterm2: where the preferences are located / if you don't want to use my preferences - comment it out

section - screen: where the screenshots are stored

Quickstart
==========

**1.  move into your home directory**

.. code-block:: bash

    cd ~/


**2.  clone this repo**

.. code-block:: bash

    git clone https://github.com/tkjone/dotfiles


**3.  run the setup script**

.. code-block:: bash

    source setup.sh


Post Setup
==========

After the above, be sure to setup the following additional items:

1.  git ssh keys

Setup Explained
===============

The `setup.sh` file is going to do all the heavy lifting and automate as many things as we can.  In order, it will:

- Install Brew
- Brew install everything in the Brewfile - https://robots.thoughtbot.com/brewfile-a-gemfile-but-for-homebrew
- Symlink dotfiles
- Set the default shell environment to zsh
- Setup Sublime Text - Specifically, setup ``subl`` and replace the default icon
- Setup preferred macOS settings

Customization
=============

There may be ``.zshrc`` aliases or configurations that you may want to keep private, you can create a file called ``.extras`` in the ``zsh`` directory and this will be picked up by ``.zsh_profile``.

Dev Environments
================

This section will outline different development languages / environments that this setup supports.  These are the languages that I tend to work with.  However, you will notice that the setups are usually package managers.  This is because I use vagrant or docker and do not need specific versions of the following languages installed.

Python
------

- virtualenvwrapper

Node
----

- nvm

Clojure
-------

- jenv
- basic java setup

iterm2
------

- I activate scroll functionality so you can just use the trackpad for long pieces of text - e.g. ``man defaults``
- solarized color scheme - well thought out color scheme
- ``command + d`` will bring up iterm2 when in the background - very handy when you are an active terminal user - something I picked up from linux, quake terminal


duti
----

- duti will set an application to open all filetypes with a specified application.  See the ``.duti`` file.

