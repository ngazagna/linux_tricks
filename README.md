# Linux at TPT
_Work in progress_

This is a list of practical links and tricks in Unix environments in Telecom ParisTech.

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
