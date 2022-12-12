# ica0002
Repository for IT Infrastructure


# Helpful Commands

// When running playbook use --diff to show changes

- service 'service' status
- ps ax |grep 'service'
- sudo ss -ntlp |grep 'Id of service'
- journalctl -u 'service' --no-pager
- cat 'file_to_filter'.conf |grep -v  "^$\|^#\|^  #"

- nginx -t

### Special Combo for web
- service service status
- sudo ss -ntlp |grep Id of service
- curl -s localhost:'port'/'optional_redirectn'|grep 'something'

## Encrypt string

- ansible-vault encrypt_string 'string' --name 'var name'

## DNS

// Reloads Config file for zones
- sudo rndc reload 
- named-checonf // To check syntax of bind9: sudo named-checkconf /etc/bind/named.conf.local
- named_checkzone // For zone files: sudo named-checkzone alba.pz /var/cache/bind/db.alba.pz.j2

- dig AXFR alba.pz @192.168.42.94

## Backup

- sudo su -l backup -s /bin/bash

- su - backup
- ssh Al-x22@backup

## SQL

- sudo mysql -e "SELECT user,host from mysql.user"
- sudo mysql -e "SELECT * FROM agama.item" agama

- mysql -u 'user' -p 

