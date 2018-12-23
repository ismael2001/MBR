**How to install mixxxdj**

In Fedora, enable the RPMFusion package repository to install the DJ Mixxx software using the following commands.

The first step get root: su -

2- # dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

3- # dnf groupinstall "Development Tools"

4- # dnf install gcc-c++ upower-devel lilv-devel

5- # dnf builddep mixxx

And the end install the program with this comand:

6- # dnf install mixxx
