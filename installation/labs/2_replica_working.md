# MySQL/MariaDB Installation Lab

If you are using RHEL/CentOS 7.x, use MariaDB.

## Configure MariaDB with a replica server

```
    yum install -y mariadb-server

    sudo service mariadb start
    sudo service mariadb stop
    sudo service mariadb status
    ls -lAh /var/lib/mysql/
    mv /var/lib/mysql/ib_logfile0 /tmp
    mv /var/lib/mysql/ib_logfile1 /tmp
    ls -lAh /var/lib/mysql/

    less /etc/my.cnf
    cp /etc/my.cnf /etc/my.cnf.bkp
    vi /etc/my.cnf
```    

Add recommended CLoudera options:

```
    [mysqld]
    transaction-isolation = READ-COMMITTED
    # Disabling symbolic-links is recommended to prevent assorted security risks;
    # to do so, uncomment this line:
    # symbolic-links = 0

    key_buffer = 16M
    key_buffer_size = 32M
    max_allowed_packet = 32M
    thread_stack = 256K
    thread_cache_size = 64
    query_cache_limit = 8M
    query_cache_size = 64M
    query_cache_type = 1

    max_connections = 550
    #expire_logs_days = 10
    #max_binlog_size = 100M

    #log_bin should be on a disk with enough free space. Replace '/var/lib/mysql/mysql_binary_log' with an appropriate path for your system
    #and chown the specified folder to the mysql user.
    log_bin=/var/lib/mysql/mysql_binary_log

    binlog_format = mixed

    read_buffer_size = 2M
    read_rnd_buffer_size = 16M
    sort_buffer_size = 8M
    join_buffer_size = 8M

    # InnoDB settings
    innodb_file_per_table = 1
    innodb_flush_log_at_trx_commit  = 2
    innodb_log_buffer_size = 64M
    innodb_buffer_pool_size = 4G
    innodb_thread_concurrency = 8
    innodb_flush_method = O_DIRECT
    innodb_log_file_size = 512M

    [mysqld_safe]
    log-error=/var/log/mariadb/mariadb.log
    pid-file=/var/run/mariadb/mariadb.pid
```

Start at boot:

```
    systemctl enable mariadb
```

Install JDK

```
    wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u161-b12/2f38c3b165be4555a1fa6e98c45e0808/jdk-8u161-linux-x64.rpm"
    rpm -ivh jdk-8u161-linux-x64.rpm
    java -version
    echo "export JAVA_HOME=/usr/java/latest" >> /root/.bashrc
    source /root/.bashrc
    printenv JAVA_HOME
```

Install JDBC driver

```
    yum install -y wget
    wget -c https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.45.tar.gz
    tar xzvf mysql-connector-java-5.1.45.tar.gz
    mkdir -p /usr/share/java/
    cp mysql-connector-java-5.1.45/mysql-connector-java-5.1.45-bin.jar /usr/share/java/mysql-connector-java.jar
```

Secure db install:

```
    systemctl start mariadb
    /usr/bin/mysql_secure_installation
```

Setup replication

```
    vi /etc/my.cnf
```

Add under [mysqld]

```
log-bin
server_id=1
log-basename=master1
bind-address=ip-172-31-2-135.eu-west-1.compute.internal
```

Restart db

```
    systemctl restart mariadb
    mysql -uroot -p

    GRANT REPLICATION SLAVE ON *.* TO 'root'@'ip-172-31-15-191.eu-west-1.compute.internal' IDENTIFIED BY 'jovv';
    SET GLOBAL binlog_format = 'ROW';
    FLUSH TABLES WITH READ LOCK;
```

In a second teerminal session:

```
    mysql -uroot -p
    SHOW MASTER STATUS;
```

Close the second session.
In the first session:

```
    UNLOCK TABLES;
    exit
```

On the replica server:

```
    vi /etc/my.cnf
```

Add under [mysqld]

```
log-bin
server_id=2
```

Save the file.

```
    mysql -uroot -p
    CHANGE MASTER TO MASTER_HOST='ip-172-31-2-135.eu-west-1.compute.internal', MASTER_USER='root', MASTER_PASSWORD='jovv', MASTER_LOG_FILE='mysql_binary_log.000002', MASTER_LOG_POS=427;
    START SLAVE;
    SHOW SLAVE STATUS \G
```

Output:

```
MariaDB [(none)]> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: ip-172-31-2-135.eu-west-1.compute.internal
                  Master_User: root
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000003
          Read_Master_Log_Pos: 315
               Relay_Log_File: mariadb-relay-bin.000003
                Relay_Log_Pos: 606
        Relay_Master_Log_File: mysql_binary_log.000003
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 315
              Relay_Log_Space: 1193
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 1
1 row in set (0.00 sec)    
```

# Cloudera Manager Install Lab

```
    cd /tmp
    wget -c https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo
    vi cloudera-manager.repo    
```

Replace the base url

```
    baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.9.3/
```

Save the file

```
    cp cloudera-manager.repo /etc/yum.repos.d/
    yum install -y cloudera-manager-daemons cloudera-manager-server
```

Create databases

```
    mysql -uroot -p

    create database amon DEFAULT CHARACTER SET utf8;
    grant all on amon.* TO "amon"@"%" IDENTIFIED BY "amon_password";

    create database rman DEFAULT CHARACTER SET utf8;
    grant all on rman.* TO "rman"@"%" IDENTIFIED BY "rman_password";

    create database metastore DEFAULT CHARACTER SET utf8;
    grant all on metastore.* TO "hive"@"%" IDENTIFIED BY "hive_password";

    create database scm DEFAULT CHARACTER SET utf8;
    grant all on scm.* TO "scm"@"%" IDENTIFIED BY "scm_password";

    show databases;
    exit
```

Prepare CM database:

```
    /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm_password -hip-172-31-2-135.eu-west-1.compute.internal
    systemctl start cloudera-scm-server
```