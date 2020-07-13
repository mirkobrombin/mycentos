# Vesta

## Install
```
curl -O http://vestacp.com/pub/vst-install.sh
```
set params:
```
vesta_host="HOST"
vesta_mail="MAIL"
vesta_password="PASSWORD"
```
run installation:
```
bash vst-install.sh --nginx yes --phpfpm yes --apache no --named no --remi yes --vsftpd yes --proftpd no --iptables yes --fail2ban yes --quota no --exim yes --dovecot yes --spamassassin yes --clamav yes --softaculous no --mysql yes --postgresql no --hostname $vesta_host --email $vesta_mail --password $vesta_password
```
