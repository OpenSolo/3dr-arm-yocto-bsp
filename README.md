WARNING - WORK IN PROGRESS

```
This code is known to be broken and/or incomplete. IT DOES NOT WORK. 

We are actively working on fixing it, and we really, really do not recommend you download it just yet.

We will remove this warning from the repository when it is no longer required.
```


This manifest is used to download an i.MX Yocto Project manifest.

Requires gcc-arm-none-eabi, tup, and python-pillow for building:
sudo add-apt-repository 'deb http://ppa.launchpad.net/anatol/tup/ubuntu precise main'
sudo add-apt-repository 'ppa:terry.guo/gcc-arm-embedded'
sudo apt-get update
sudo apt-get install tup gcc-arm-none-eabi python-pillow

To download:

repo init -u git@github.com:3drobotics/3dr-arm-yocto-bsp.git -b imx-3.10.17-1.0.0_ga
repo sync

This will download both Yocto Project community and the meta-fsl-bsp-release layer, as well as the 3DR layer.

To set up your build environment:

source ./setup-environment build

To build the 3dr image:

    MACHINE=imx6solo-3dr-artoo bitbake 3dr-controller

or 

    MACHINE=imx6solo-3dr-1080p bitbake 3dr-solo

NOTES: 
The only difference between this and other ( unreleased) branches of 3dr-arm-yocto-bsp is the branch of the `meta-3dr` repo that is referenced.
The tarball is from the `imx-3.10.17-1.0.0_ga` branch other/s say:
`<project remote="3dr" revision="sololink_v2.1.0-2" name="meta-3dr" path="sources/meta-3dr"/>`
`<project remote="3dr" revision="sololink_v2.0.0-5" name="meta-3dr" path="sources/meta-3dr"/>`
