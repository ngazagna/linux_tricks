# Linux
This is a list of practical links and tricks in Unix environments.

## Remote acces
- Connect to a remote acces: `ssh [user]@[machine]` (for instance [login]@ssh.enst.fr for TPT).
- ssh login without password: well explained [here](http://www.linuxproblem.org/art_9.html).
- Mount files for remote acces: with sshfs to be done (for instance to print from a remote computer). Well explained [here](https://doc.ubuntu-fr.org/sshfs).
- Double-hop ssh: This can be usefull if you need to do 2 ssh in a row. First, download the _ssh_multi_hop_config_ file and save it in _~/.ssh/config_. Then, from a local non-DSI managed computer, one can access his TPT session by launching:
```console
ssh tdsilinuxd103
```

## Managing printers
_Work in progress_
