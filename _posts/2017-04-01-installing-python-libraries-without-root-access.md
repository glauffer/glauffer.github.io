---
layout: post
title: Installing Python libraries without root access
---

Work on a computer without sudo priveleges is pretty anoying. But if you have the Python Package Index (pip) installed on the computer you can contour the sudo permission to install python libraries by installing then only for your user. For example, I need to install Ipython and Jupyter Notebook. In order to perform the installation I need to use `pip` with the `--user` flag.

First, I check if pip needs to upgrade:

```bash
$ pip install --user --upgrade pip
```

Then, the installation is done by:

```bash
$ pip install --user ipython
$ pip install --user jupyter
```

In the end is necessary to reset your session. The way I do is to source my .bashrc file:

```bash
source ~/.bashrc
```

And it is Done!
Enjoy your new python libraries!
