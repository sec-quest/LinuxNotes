# ssh
Not exhaustive, and still in build,  list of useful commands, options, etc.


### useful commands

- installs the OpenSSH server:
```sh
yum install openssh -y
```
- enables sshd service now and on boot:
```sh
systemctl enable --now sshd
```
- generates ssh keys:
```sh
ssh-keygen
```
- copies keys to a server with a given IP address:
```sh
ssh-copy-id 192.168.1.1
```

- local port forwarding:
```sh
ssh -4 -L 2233:remotehost-ip:22 localhost
```
- jumping to another host via known host:
```sh
ssh -4 -L 2233:target_ip:22 jumpserver
ssh -p 2233 localhost
```

- securely copies stuff:
```sh
scp user@ip:/what user@ip:/where
```
- copies and syncs a given folder:
```sh
rsync -av /what /where
rsync -av /what user@ip:/where
```
- deletes all files which are not present in /what folder:
```sh
rsync -av --delete /what /where
```

### important files

- config file: `/etc/ssh/sshd_config`
