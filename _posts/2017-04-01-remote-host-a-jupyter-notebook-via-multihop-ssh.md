---
layout: post
title: Remote host a Jupyter Notebook via multihop ssh
---

The [Jupyter Notebook](http://jupyter.readthedocs.io/en/latest/install.html) is my main tool for research. Among the benefits of using it, the remote hosting is one of my favorites because I can set up the Notebook on my work computer and have access to all my files via a web browser and do research without using the processing power of my home computer (whitch is slower).

But the problem is the following:
I have a computer at the University witch I can access via ssh, but I have to pass through a login host before I can connect to my computer. Because of that extra step setting up the remote Notebook is not trivial. So, after some online search and testing I found the solution for me. I will list the steps:

1. First, open two terminals.

2. In the first, we are going to make a tunneling between the `work-computer` and the `login-host`:

        $ ssh - L 9999:work-computer:22 user@login-host

3. On the second terminal, connect to `work-computer` and star the Notebook:

        $ ssh -L 7777:localhost:7777 -p9999 localhost
        $ ### Type your password ###
        $ jupyter notebook --no-browser --port=7777

4. Finally, open your web browser and access to `localhost:7777`. If everything went right, you are going to connect to the remote Notebook.

## References:
* <http://www.hydro.washington.edu/~jhamman/hydro-logic/blog/2013/10/04/pybook-remote/>
* <https://superuser.com/questions/96489/an-ssh-tunnel-via-multiple-hops>


<!-- 1. No primeiro terminal, fazer o tunel entre o servidor de acesso o pc no IF:
   > ssh - L 9999:alejandra-h61m-ds2-ds2:22 glauffer@lief.if.ufrgs.br

2. No segundo terminal, conectar no pc do IF e iniciar o ipython notebook
    > ssh -p9999 localhost
    > # Navegar até a pasta em que será iniciado o ipython notebook
    > cd /path/to/notebooks
    > ipython notebook --no-browser --port=7777

3. No terceiro terminal (talvez esta etapa pode ser o inicio da segunta etapa):
    **esta etapa pode ser a segunda. Testei e deu certo**
    > ssh -L 7777:localhost:7777 -p9999 localhost

4. No computador de casa acessar a pagina http://localhost:7777/ pelo navegador

referencias:

http://www.hydro.washington.edu/~jhamman/hydro-logic/blog/2013/10/04/pybook-remote/

http://cominf.if.ufrgs.br/index.php/Linux_acessando_Linux

(ler)
https://chamibuddhika.wordpress.com/2012/03/21/ssh-tunnelling-explained/
https://superuser.com/questions/96489/an-ssh-tunnel-via-multiple-hops

 -->
