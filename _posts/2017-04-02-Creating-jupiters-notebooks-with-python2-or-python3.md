---
layout: post
title: Creating Jupyter`s Notebooks with Python2 or Python3
---

If you have Python2 and Python3 installed on your computer but just one of them appears a an option on Jupyter Notebook, the problem is that only one version of ipykernel is installed. To solve that, after installing Jupyter Notebook by:

```bash
pip install jupyter
```

or

```bash
pip3 install jupyter
```

You just have to install the ipykernel that is missing:

* For Python2:

        ```
        $ sudo python2 -m ipykernel install
        ```

* For Python3:

        ```
        $ sudo python3 -m ipykernel install
        ```

That`s all!

In my case, the ipykernel for python2 was missing, so after I did the steps above now I can choose the python version for my new notebooks.

## Reference

* <https://ipython.readthedocs.io/en/latest/install/kernel_install.html>
