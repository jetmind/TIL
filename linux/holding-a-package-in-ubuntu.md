# Holding a Package in Ubuntu

Sometimes a new version of a package breaks some app you need to use and you
don't want to update it until the app is fixed. Unfortunately Ubuntu's update
manager will periodically ask you to update this package (among others) and it
can be tedious to manually unselect it every time you update your system.

I've tripped on this using Upwork team app, which
[does not work with libnss > 3.19.x][upwork-bug].

The solution is to put the package on hold. It basically means that package
manager will keep the current installed version of the package no matter what
(you can always update it manually if you want).

Doing so is easy:

```sh
› sudo apt-mark hold libnss3 libnss3-1d libnss3-nssdb
```

and you can undo it later:

```sh
› sudo apt-mark unhold libnss3 libnss3-1d libnss3-nssdb
```

See [Ubuntu docs][ubuntu-help] for more info.

[upwork-bug]: https://support.upwork.com/hc/en-us/articles/211064108-Linux-troubleshooting-for-Upwork-Team-App#library
[ubuntu-help]: https://help.ubuntu.com/community/PinningHowto#Introduction_to_Holding_Packages
