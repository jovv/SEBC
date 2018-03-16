# Challenge 2: Install Cloudera Manager 5.13.x (latest)

```
    [root@ip-172-31-0-159 tmp]# ls /etc/yum.repos.d
    cloudera-manager.repo  mariadb.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhui-load-balancers.conf
```

```
    [root@ip-172-31-0-159 ec2-user]# /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm_password -hip-172-31-12-170.eu-west-1.compute.internal
    JAVA_HOME=/usr/java/latest
    Verifying that we can write to /etc/cloudera-scm-server
    Creating SCM configuration file in /etc/cloudera-scm-server
    Executing:  /usr/java/latest/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
    [                          main] DbCommandExecutor              INFO  Successfully connected to database.
    All done, your SCM database is configured correctly!
```