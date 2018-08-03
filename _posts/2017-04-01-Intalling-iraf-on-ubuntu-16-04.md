---
layout: post
title: Installing IRAF on Ubuntu 16.04
---


*Check this [post](https://glauffer.github.io/2018-08-03-the-easy-way-to-install-iraf/) for a better and easier way to install IRAF.*

**This is outdated**

The [IRAF](http://iraf.noao.edu/) (Image Reduction and Analysis Facility) is a general purpose software system for the reduction and analysis of astronomical data. I had to use it for a class project on my masters and I discovery that  the installing instructions on its website are elusive. After some googling I figured out how to properly install on Ubuntu 16.04.

The only package I had to install before starting the installation was the C-Shell, which can be installed by:

```bash
$ sudo apt-get install csh
```

Then, download the IRAF installation .tar file on its web page: <http://iraf.noao.edu/>

After downloaded the .tar file, create a directory for IRAF and extract the .tar file:

```bash
$ mkdir /iraf
$ tar -zxf iraf.lnux.x86_64.tar.gz -C /iraf
```

Change directory to your new iraf folder and install it:

```bash
$ cd /iraf
$ sudo ./install
```

Keep hitting enter for all prompts. After the installation, is necessary to install the `xgterm` to visualize the data on IRAF. So, inside the iraf directory:

```bash
$ cd /iraf/vendor/x11iraf
$ sudo ./install
```

Last, add the `IRAF` variable to your `.bashrc` file:

```bash
export IRAF=/iraf
```

Now, you can star IRAF from every folder by typing on terminal"

```bash
$ IRAF
```

## Reference:
* <http://www.astronomy.ohio-state.edu/~khan/iraf/iraf_step_by_step_installation_64bit>
