# Home

Welcome to the RIFT documentation, here you will find how to use the program, and how to create your very own repository! Ready?

**I will remake the documentation for the rewrite soon.**

## Table of Contents

* Home: Starting place and Table of Contents
* Dependencies: What you need before you start
* Introduction: Learn the basics
* Repositories: Learn how to make a repo
* Plugins: Learn how to install and create plugins

<hr>

# Installation

You may skip this if you are reading this in the program.

Before you start, you will need a couple things installed:

* Python 3+ (No Python 2 support)
* Colorama (Installed automatically with `run.sh`)
* Windows, MacOS, or Linux

Once you have all of those, you can start using RIFT! To install RIFT, download either the stable release from Github or clone the unstable version and run the `run.sh` file if you're on Linux/MacOS which will also install it to your system, or use `run.bat` if you're on Windows.

<hr>

# Introduction

To start, you're probably here because you don't know how to do anything. Don't worry, this guide will teach you all the basics of how to use RIFT. From how to download your first file to navigating RIFT.

You'll see something like this

`Welcome to RIFT [VERSION]`
`Please provide file repo:`

![RIFT URL Screen](rift/docs/welcomescreen.png)

If you need an example, try `0hstormy.github.io` and press enter.

Now that you're in the main part of the program, here are the follow commands that are available to use.

### Commands

* i: Choose a file to download
* dl: Downloads the chosen file
* exit: Exits the program
* rf: Refreshes the screen
* conf: Edit config file, Vim is the default editor (Built-in interface planned)
* edit: Enters the repository editor
* play: Plays a specified file or the last file you downloaded (VLC used by default)
* about: Shows README.md file
* help: Shows this documentation

Main UI looks something like below:

![RIFT UI](rift/docs/mainui.png)

<hr>

# Repositories

So, you want to create a repository now huh? Well you're in luck because creating file repositories in RIFT is pretty simple, there are 2 ways to do it currently. You can use the editor plugin, or edit a `repo.rift` file manually.

## Repository Edtior Plugin

First, you will need to install the repository editor with [rpk](https://github.com/openRIFT/rpk), which you can download from Github. and then install with `python3 rpk.py install repo-editor` or if installed to a PATH you can do `rpk install repo-editor`.

Using the built-in editor is very simple, open up rift, you can either clear out your current `repo.rift` file or you can simply just work off the on you last opened by typing `local` into the URL input. From there you can just type `edit` and it will open up the editor mode. Use `append` to create a new entry, or use `del` to remove an entry at a specific index. All download URL's must be direct file downloads.

![RIFT UI](rift/docs/editorui.png)

### Editor specific commands

* append: creates a new repository entry
* del: removes an entry at a specific index

## Manually editing

You may choose the manually edit the `repo.rift` file, this way isn't recommend but is possible. First, you want find where RIFT is installed, then go into the `rift/` folder, there you will find `repo.rift`. You want to open the file and clear it out. After that you can add entries like this: `[LABEL];[URL]`. All download URL's must be direct file downloads.

<hr>

# Plugins

You can also create and install user made plugins for RIFT that act as extra commands to provide additional functionality that may not need to be in the program by default, such as the RIFT Repository editor.

## Installing Plugins

To install plugins you will need [rpk](https://github.com/openRIFT/rpk), which you can download from Github. To install rpk, use the `install.sh` script on Linux/MacOS, and if you're on Windows you're kind of out of luck for now unless you manually copy the assets folder to your user folder and rename it to `.rpk`

Now with rpk installed, you can run `rpk install [PLUGIN]` to install a desired plugin or package.

### Commands

* install: installs a given package
* remove: uninstalls a given package
* search: query for all packages with a specific keyword

## Creating Plugins

To create a plugin, create one or more Python files in your plugins directory (usually `/home/user/.rift/plugins` or `C:\Users\user\.rift\plugins\`). You should be able to run them by typing the name of the file minus `.py` into RIFT, boom! Your first plugin.

### Packaging

Now how the heck do I upload these so anyone can download them? Just follow the steps I will explain.

1: Have [Git](https://git-scm.com/) installed.

2: Clone the plugins repository with `git clone https://github.com/openRIFT/plugins`

3: If your plugin has multiple files, zip them with a unique file name like `neoedit.zip` or something like that

4: Edit the `plugins.rift` file and add your plugin into there with a direct download link from GitHub. Ex: `neoeditor;https://raw.githubusercontent.com/openRIFT/plugins/main/neoedit.zip` or `neoeditor;https://raw.githubusercontent.com/openRIFT/plugins/main/neoedit.py` if it's a single Python file

5: Commit and push your plugin to the plugins repository with `git commit` and `git push`

You made it! Good job, now just wait a few minutes for the `plugins.rift` file to update and install it with `rpk`.

*RIFT documentation created by 0Stormy, edited 11/20/24*