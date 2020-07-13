# Update


## elrepo
```
yum install yum-plugin-fastestmirror
rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org
rpm -Uvh http://www.elrepo.org/elrepo-release-7.0-2.el7.elrepo.noarch.rpm
```

## latest kernel
```
yum --enablerepo=elrepo-kernel install kernel-ml
grub2-set-default 0
grub2-mkconfig -o /boot/grub2/grub.cfg
```

## ssh
### disable root login
Edit `/etc/ssh/sshd_config`:
```
..
PermitRootLogin no
..
```
restart service:
```
systemctl restart sshd
```

### change port
Edit `/etc/ssh/sshd_config`:
```
..
Port YOUR_PORT
..
```
open port:
```
firewall-cmd --permanent --zone=public --add-port=YOUR_PORT/tcp
```
pass rule to selinux:
```
semanage port -a -t ssh_port_t -p tcp YOUR_PORT
```
reload firewalld rules:
```
firewall-cmd --reloadsudo systemctl restart sshd
```
