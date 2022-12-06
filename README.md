# ica0002
Repository for IT Infrastructure

Creating commit to see if Virtual Machine Works.


# Helpful Commands

// When running playbook use --diff to show changes

- service <service> status
- ps ax |grep <service>
- sudo ss -ntlp |grep <Id of service>
- journalctl -u <service> --no-pager
- cat <file_to_filter>.conf |grep -v  "^$\|^#\|^  #"

### Special Combo for web
- service <service> status
- sudo ss -ntlp |grep <Id of service>
- curl -s localhost:<port>/<optional_redirect> |grep <something>

# Encrypt string

- ansible-vault encrypt_string <string> --name <var name>

# DNS

// Reloads Config file for zones
- sudo rndc reload 
- named-checonf // To check syntax of bind9
- named_checkzone // For zone files

- dig AXFR alba.pz @192.168.42.94

sudo su -l backup -s /bin/bash

su - backup
ssh Al-x22@backup


