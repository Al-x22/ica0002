# Backup Service Level Agreement

### ICA002
### Alejandro Ballesteros Perez


This document provides backup information concerning the IT infrastructure developed during the course.

## Backup Coverage

- Database servers
- InfluxDB
- Ansible Repository

## Recovery Point Objective (RPO)


```sh
Backup update frequency: 24h
Backup creation time: 12:00am
```

## Versioning and Retention


```sh
Retention Time: 30 days (720h)
Versions: 30
```


## Usability checks

Usability tests are done every 3 days. Tests include:

- Backup creation was on time
- Is backup readable
- Is backup enough to restore the service
- Could service be restored to needed state?

## Restoration criteria


Backup restoration should be the last resort. Restoration should be implemented only in two scenarios:

- The service has been down for more than 2 days
- Monetary value currently losing surpasses monetary value of data that will be lost with backup.


## Recovery Time Objective (RTO)


Service Recovery Time: 2h
