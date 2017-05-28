---
layout: post
title: Editing .bashrc from terminal
---

This is just a reminder I created after a non intentional overwrite of .bashrc file.

Ubuntu keeps a default `.bashrc` file at `/etc/skel/.bashrc`. So, if you replaced you .bashrc or for some reason you don`t have it anymore, you just have to type on terminal:

```
$ cat /etc/skel/.bashrc > ~/.bashrc
```


This is important to remember. To add directories to your PATH variable:

```
$ echo PATH=$PATH:/directory >> ~/.bashrc
```

or if I want to add the current directory:

```
$ echo PATH=$PATH:$(pwd) >> ~/.bashrc
```

And the most important information is:

** to append a string to the end of the file, I have to use `>>` instead of `>`. Because of this mistake that I wrote this post! ** :)
