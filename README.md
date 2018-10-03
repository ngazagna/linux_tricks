# Linux at TPT
_Work in progress_

This is a list of practical links and tricks in Unix environments in Telecom ParisTech.

You can also have a look at [here](https://github.com/TomDLT/TPT) for more information.

## Remote acces
- Connect to a remote acces: 
````console
ssh [user]@[hostname]
````
For instance at TPT: `[login]@ssh.enst.fr`.
- ssh login without password: well explained [here](http://www.linuxproblem.org/art_9.html).
- Mount files for remote acces: with sshfs to be done (for instance to print from a remote computer). Basic configuration is well explained [here](https://doc.ubuntu-fr.org/sshfs). Then it works exactly lke a Dropbox.
- Double-hop ssh: This can be usefull if you need to do 2 ssh in a row. First, download the _ssh_multi_hop_config_ file and save it in _~/.ssh/config_. Then, from a local non-DSI managed computer, one can access his TPT session by launching:
```console
ssh tdsilinuxd103
```

## Managing printers
- First of all have a look at the [TPT help about printers](https://www.telecom-paristech.fr/vivre-ecole/services-numeriques-dsi/imprimantes-multifonctions/impression-centralisee/imprimer-depuis-gnulinux.html).
- Try to install printers manually. For instance on Ubuntu 18.04 LTS : `Settings -> Devices -> Printers -> Additional Printer Settings`. Then, try to fill in information and config files by using the _Central_N_B.ppd_ and _Central_Couleur.ppd_ files provided by TPT (see previous link).

## Creating your personal website with jemdoc
I recommend to use [jemdoc](http://jemdoc.jaboc.net/) which creates a very sober website.
- 1) Download jemdoc.py at:
http://jemdoc.jaboc.net/download.html

WARNING: if default python on your computer is not a 2.x version you may need to precise a python version in the first line of jemdoc.py. For instance:
#!/usr/bin/env python2.7

- 2) Make it executable by running
chmod +x jemdoc.py

- 3) Put it into your PATH for ease of use:
sudo cp jemdoc.py /usr/bin/jemdoc

- 4) Download the example css and index page respectively at 
http://jemdoc.jaboc.net/dist/jemdoc.css
 and 
http://jemdoc.jaboc.net/index.jemdoc

For more detailed information you can check:
http://jemdoc.jaboc.net/


## Hosting your page at TPT
In order to host your website on your personal Télécom ParisTech page.
- 1) Activate your personal webpage from your account. Go on 
https://moncompte.telecom-paristech.fr/mon_compte/
In section "Page web personnelle", under "Service page perso" click on the drop-down menu and select "Service Web Apache 2.4 avec PHP 7 (basé sur Débian 9)"
Your website is now available at:
https://perso.telecom-paristech.fr/<login>

- 2) Now you may want to put your website files (HTML, CSS, etc) into the dedicated folder. The easiest way to proceed is to mount the remote repository.
Open a terminal on a computer at TPT and run:
mkdir ~/perso_www
sshfs <login>@perso-<login>.lxc.enst.fr:/home/<login>/www/ ~/perso_www

- 3) Put all your website files and subfolders into perso_www on your local machine and your done!

WARNING: you may face a problem deleting the previous "index.html" file from your local computer. I solved this issue by connecting to my remote website repo /home/<login>/www/ by ssh running
ssh <login>@perso-<login>.lxc.enst.fr
cd www
And then deleted the symbolic link
rm index.html


