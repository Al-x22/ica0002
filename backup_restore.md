Install and configure infrastructure with Ansible:

    ansible-playbook infra.yaml

Restore MySQL data from the backup:

    sudo -u backup rm -r /home/backup/restore/mysql
    sudo -u backup duplicity --no-encryption restore rsync://Al-x22@backup/mysql /home/backup/restore/mysql
    sudo su
    mysql agama < /home/backup/mysql/agama.sql

Finally, log into the agama webpage if you want to see your restoration results easily.
Restore can also be checked by logging into my SQL in the machine and checking the TABLE agama directly

    sudo mysql
    SHOW DATABASES;
    USE agama;
    SELECT * FROM agama.item;
    
    
Restore InfluxDB data from the backup:

    sudo -u backup rm -r /home/backup/restore/influxdb
    sudo -u backup duplicity --no-encryption restore rsync://Al-x22@backup/influxdb /home/backup/restore/influxdb
    sudo su
    service telegraf stop
    influx -execute 'DROP DATABASE telegraf'
    service pinger stop
    influx -execute 'DROP DATABASE latency'
    influxd restore -portable /home/backup/restore/influxdb
    
Note: Even if telegraf is the only one wanted to be restored, it is not going to work unless you also DROP latency and stop pinger.

To Check if this worked do the following:

    sudo su
    influx
    SHOW DATABASES
    
Check if the databases telegraf and latency are there. If they are, good.
