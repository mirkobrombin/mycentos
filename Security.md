# Security

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
