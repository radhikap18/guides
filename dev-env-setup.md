# Setting up your Linux development environment

This guide will walk you through the process of setting up a useable development environment on your DragonBoard 410c. The purpose of going through this instruction set it to make sure your DragonBoard 410c possesses the appropriate dependencies needed for development.

## Update your source.list

The following commands will ensure your DragonBoard has access to all appropriate repositories when attempting to download packages using the `apt-get` command.

```shell
$ echo "deb http://deb.debian.org/debian jessie main" | sudo tee -a /etc/apt/sources.list
$ echo "deb-src http://deb.debian.org/debian jessie main" | sudo tee -a /etc/apt/sources.list
```

Now that you have modified your `source.list`, you are ready to update and upgrade the package list in all your registered repositories.

## Update and upgrade

The image on your board might be out of date. This is possible even when using the stock image (the operating system your board was shipped with), or a newly flashed version from the 96Boards.org website.

A few useful commands will help us make sure everything on the board is current:

- **apt-get update**: Downloads package lists from online repositories and "updates" them to get information on the newest versions of packages and their dependencies.
- **apt-get upgrade**: Fetches and installs newest package versions which currently exist on the system. APT must know about these new versions by way of 'apt-get update'
- **apt-get dist-upgrade**: In addition to performing the function of upgrade, this option also intelligently handles changing dependencies with new versions of packages

**Commands:**

```shell
$ sudo apt-get update

$ sudo apt-get upgrade

$ sudo apt-get dist-upgrade
```

Note: If at any point during this process you are prompted with a 'Y/N', select Y and press Enter.

Congratulation! Your DragonBoard 410c should now be running the most current development environment.