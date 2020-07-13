# Update

## epel-release
```
yum install epel-release
```

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
