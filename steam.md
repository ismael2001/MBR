# Installing Steam on Fedora

These instructions are currently for Fedora 24. I'll update them over the releases if anything changes.

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
Press <kbd>y</kbd> when it asks you about installing the GPG key

## Open steam
You can either open it from **Activities** or press the <kbd>Win/Super</kbd> key, type `steam` and press <kbd>Enter</kbd>.

Accept the agreement and it'll download the latest version of Steam.

## Any problems?

I had a problem once where packages didn't install properly across diferent architectures (32 and 64bit) and discovered you need to reinstall them. Run the following:
```sh
dnf repoquery --duplicated | sed "1 d" > dupes
cat dupes | sed 's/^\(.*\)-[0-9]\+:.*/\1/' | sort | uniq | grep -v kernel > reinstall
package-cleanup --cleandupes # uses dnf via /bin/yum (now a passthrough + warning script)
# check only the dupes are being removed before confirming "y"
sudo dnf reinstall $(cat reinstall)
# try installing steam again
dnf install steam -y
```

Credit: jozxyqk http://superuser.com/questions/994151/conflicts-between-new-32-bit-and-old-64-bit-packages-when-installing-rpmfusions

Feel free to comment below.
