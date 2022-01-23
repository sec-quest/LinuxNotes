# ssh
Not exhaustive list of useful commands, options, etc. \
</br>

### useful commands

**yum install openssh -y** - installs openssh server \
**systemctl enable --now sshd** - enables sshd service now and on boot \
**ssh-keygen** - generates ssh keys \
**ssh-copy-id 192.168.1.1** - copies keys to given server \
</br>
**ssh -4 -L 2233:remotehost-ip:22 localhost** - local port forwarding \
**ssh -4 -L 2233:target_ip:22 jumpserver** - jumping to another host via known host \
**ssh -p 2233 localhost** \
</br>
**scp user@ip:/what user@ip:/where** - secure copy of stuff \
**rsync -av /what /where** - copy and sync given folder \
**rsync -av /what user@ip:/where** \
**rsync -av --delete /what /where** - deletes all files which are not present in /what folder \
</br>

### important files

**/etc/ssh/sshd_config** - config file
