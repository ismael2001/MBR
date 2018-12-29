# Installing Steam on Fedora

Before you follow these, make sure you have [RPM Fusion](http://rpmfusion.org/Configuration) installed.

## Open a terminal
Press the <kbd>Win/Super</kbd> key, type `terminal` and press <kbd>Enter</kbd>.

## Upgrade to super user
```sh
su -
```
Then type your password and hit <kbd>Enter</kbd>.

## Make sure your system is up to date
```
dnf update --refresh
```
Also it doesn't hurt to reboot to make sure you're on the latest linux kernel.

## Add the negativo17 repo
```sh
dnf config-manager --add-repo=http://negativo17.org/repos/fedora-steam.repo
```
More information about this repo is on their [website](http://negativo17.org/steam/).

## Install the steam package
```sh
dnf install steam -y
```


