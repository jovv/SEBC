# Challenge 1: Install a database server

Hostname:

```
    MariaDB [(none)]> SELECT @@hostname;
    +---------------------------------------------+
    | @@hostname                                  |
    +---------------------------------------------+
    | ip-172-31-12-170.eu-west-1.compute.internal |
    +---------------------------------------------+
    1 row in set (0.00 sec)
```

Databases:

```
    MariaDB [(none)]> show databases;
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | hive               |
    | hue                |
    | mysql              |
    | oozie              |
    | performance_schema |
    | rman               |
    | scm                |
    +--------------------+
```

Version:

```
    MariaDB [(none)]> select VERSION();
    +----------------+
    | VERSION()      |
    +----------------+
    | 5.5.59-MariaDB |
    +----------------+
    1 row in set (0.00 sec)
```