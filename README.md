# Re4son's Kernel Builder for Raspbery Pi
###### V 1.0.1
###### Created for kernel version 4.4 and newer
######             raspberry toolchain published 17-May-2016 and later
######             raspberry firmware released 4-May-2016 and later



## Compiling The Raspberry Pi Kernel

Clone the git repo to /opt/kernel-builder

```
$ sudo git clone https://github.com/Re4son/re4son-kernel-builder.git /opt/re4son-kernel-builder
$ cd kernel-builder
```

If running on a 64bit architecture, install additional 32bit packages required by the toolchain

```
$ sudo apt-get install lib32z1 lib32ncurses5 libc6-i386 lib32stdc++6
```

Setup the kernel-builder

```
$ sudo ./setup.sh
```
edit build.sh and set the variable KERNEL-BUILDER_DIR= to the kernel builder directory.
default is "/opt/kernel-builder"

```
~$ sudo re4sonbuild -h
usage: re4sonbuild [options]
 This will build the Raspberry Pi Kernel.
 OPTIONS:
    -h        Show this message
    -r        The remote github kernel repo to clone in user/repo format
              Default: raspberrypi/linux
    -b        The git branch to use
              Default: Default git branch of repo
    -1        The config file to use when compiling for Raspi v1
              Default: arch/arm/configs/bcmrpi_defconfig
    -2        The config file to use when compiling for Raspi v2
              Default: arch/arm/configs/bcm2709_defconfig
```

Compile with default options:

```
~$ sudo re4sonbuild
```

Compile [re4son-raspberrypi-linux][1] using the `rpi-4.4.y-re4son` branch:

```
~$ sudo re4son -r https://github.com/Re4son/re4son-raspberrypi-linux -b rpi-4.1.y-re4son
```

A `tar.gz` archive will be available in the kernel-builder folder
after the custom kernel has been built. Copy the archive to your Pi and extact the
contents. Installation instructions are included in the archive.


[1]: https://github.com/Re4son/re4son-raspberrypi-linux

