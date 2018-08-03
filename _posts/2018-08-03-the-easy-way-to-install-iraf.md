---
layout: post
title: The easy way to install IRAF
---

The IRAF (Image Reduction and Analysis Facility) is a general purpose software system for the reduction and analysis of astronomical data. 

It can be easily installed via the [astroconda](http://astroconda.readthedocs.io/en/latest/index.html) channel of the STScI (Space Telescope Science Institute). The only dependencies are the [conda](https://conda.io/docs/) package manager by Continuum Analytics and some 32 bits packages for IRAF.

# Installation

First, let's install the 32 bits dependencies. On Ubuntu (or any other Debian based system), run the following commandos in a terminal window:
```
$ dpkg --add-architecture i386
$ sudo apt-get update
$ sudo apt-get install libc6:i386 libz1:i386 libncurses5:i386 libbz2-1.0:i386 libuuid1:i386 libxcb1:i386 libxmu6:i386
```

Now, let's download and install the conda package manager via the miniconda software:
```
$ wget -c https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
$ bash Miniconda3-latest-Linux-x86_64.sh
```
*Say yes or just hit `Enter` to the questions asked during the miniconda installation*

Finally, let's add the astroconda channel on conda and install iraf:
```
$ conda config --add channels http://ssb.stsci.edu/astroconda
$ conda create -n iraf27 python=2.7 iraf-all pyraf-all stsci
```
It will search for all packages and ask if you want to proceed with installation. Type `y` and wait a little. Done! IRAF and pyRAF are installed.

# Starting IRAF or pyRAF

To start working with IRAF we have to activate the iraf environment we installed with conda. This can be done typing in terminal:
```
$ source activate iraf27
```

Now, `cd` to your working directory and create the `login.cl` file with the `mkiraf` command and choose the `xterm` terminal type:
```
(iraf27)$ mkiraf

-- creating a new uparm directory
Terminal types: xgterm,xterm,gterm,vt640,vt100,etc.
Enter terminal type [default xterm-256color]:xterm
```

Finally, we can start IRAF with:
```
(iraf27)$ cl
```
or pyRAF:
```
(iraf27)$ pyraf
```

# Additional Software

To visualize fits images I like to use the [SAOImage DS9](http://ds9.si.edu/site/Home.html):
```
sudo apt install saods9
```
The DS9 software can be used together with iraf. For this, *before* starting iraf type:
```
& ds9 &
```
The fits images can be visualized in DS9 via the `display` command on iraf.

## References:
* <http://astro.if.ufrgs.br/rad/ccd/ccd.htm>
* <http://astroconda.readthedocs.io/en/latest/index.html>
* <http://astroconda.readthedocs.io/en/latest/faq.html#in-linux-how-do-i-install-iraf-s-32-bit-dependencies>
* <https://conda.io/docs/user-guide/install/linux.html#installing-on-linux>