# Sentry Lab

## Verify user priviliges

```
    [root@ip-172-31-2-135 ec2-user]# kinit hdfs_jovv@JOVV.HADOOP.COM
    Password for hdfs_jovv@JOVV.HADOOP.COM:
    [root@ip-172-31-2-135 ec2-user]# klist -ef
    Ticket cache: FILE:/tmp/krb5cc_0
    Default principal: hdfs_jovv@JOVV.HADOOP.COM

    Valid starting       Expires              Service principal
    03/15/2018 07:48:57  03/16/2018 07:48:57  krbtgt/JOVV.HADOOP.COM@JOVV.HADOOP.COM
            renew until 03/22/2018 07:48:57, Flags: FRI
            Etype (skey, tkt): arcfour-hmac, aes256-cts-hmac-sha1-96
    [root@ip-172-31-2-135 ec2-user]# beeline
    Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
    Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
    Beeline version 1.1.0-cdh5.9.3 by Apache Hive
    beeline> !connect jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-15-191.eu-west-1.compute.internal@JOVV.HADOOP.COM
    Connecting to jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-15-191.eu-west-1.compute.internal@JOVV.HADOOP.COM
    Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
    Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
    Transaction isolation: TRANSACTION_REPEATABLE_READ
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> SHOW TABLES;
    INFO  : Compiling command(queryId=hive_20180315080303_a8c1a657-b4bf-4dca-88fe-59513116f9e1): SHOW TABLES
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315080303_a8c1a657-b4bf-4dca-88fe-59513116f9e1); Time taken: 0.941 seconds
    INFO  : Executing command(queryId=hive_20180315080303_a8c1a657-b4bf-4dca-88fe-59513116f9e1): SHOW TABLES
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315080303_a8c1a657-b4bf-4dca-88fe-59513116f9e1); Time taken: 0.39 seconds
    INFO  : OK
    +-----------+--+
    | tab_name  |
    +-----------+--+
    +-----------+--+
    No rows selected (2.733 seconds)        
```

## Create a Sentry role with full authorization

```
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> CREATE ROLE sentry_admin;
    INFO  : Compiling command(queryId=hive_20180315081111_71cb3af5-e254-49c9-bfaa-222ff3b1bb1f): CREATE ROLE sentry_admin
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315081111_71cb3af5-e254-49c9-bfaa-222ff3b1bb1f); Time taken: 0.134 seconds
    INFO  : Executing command(queryId=hive_20180315081111_71cb3af5-e254-49c9-bfaa-222ff3b1bb1f): CREATE ROLE sentry_admin
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315081111_71cb3af5-e254-49c9-bfaa-222ff3b1bb1f); Time taken: 0.518 seconds
    INFO  : OK
    No rows affected (0.667 seconds)
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
    INFO  : Compiling command(queryId=hive_20180315081212_3435dd2d-b466-4867-af19-2d34ffda68be): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315081212_3435dd2d-b466-4867-af19-2d34ffda68be); Time taken: 0.082 seconds
    INFO  : Executing command(queryId=hive_20180315081212_3435dd2d-b466-4867-af19-2d34ffda68be): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315081212_3435dd2d-b466-4867-af19-2d34ffda68be); Time taken: 0.083 seconds
    INFO  : OK
    No rows affected (0.179 seconds)
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> GRANT ROLE sentry_admin TO GROUP hdfs_super;
    INFO  : Compiling command(queryId=hive_20180315081212_de645cc8-b8a7-4bb5-bacd-a6d69ff29d85): GRANT ROLE sentry_admin TO GROUP hdfs_super
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315081212_de645cc8-b8a7-4bb5-bacd-a6d69ff29d85); Time taken: 0.071 seconds
    INFO  : Executing command(queryId=hive_20180315081212_de645cc8-b8a7-4bb5-bacd-a6d69ff29d85): GRANT ROLE sentry_admin TO GROUP hdfs_super
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315081212_de645cc8-b8a7-4bb5-bacd-a6d69ff29d85); Time taken: 0.076 seconds
    INFO  : OK
    No rows affected (0.159 seconds)
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> SHOW TABLES;
    INFO  : Compiling command(queryId=hive_20180315081313_4bee4916-24ca-4369-a5c4-5660a8a8a8c8): SHOW TABLES
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315081313_4bee4916-24ca-4369-a5c4-5660a8a8a8c8); Time taken: 0.066 seconds
    INFO  : Executing command(queryId=hive_20180315081313_4bee4916-24ca-4369-a5c4-5660a8a8a8c8): SHOW TABLES
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315081313_4bee4916-24ca-4369-a5c4-5660a8a8a8c8); Time taken: 0.148 seconds
    INFO  : OK
    +------------+--+
    |  tab_name  |
    +------------+--+
    | customers  |
    | sample_07  |
    | sample_08  |
    | web_logs   |
    +------------+--+
    4 rows selected (0.275 seconds)
```

## George and Ferdinand

### George

```
    [root@ip-172-31-2-135 ec2-user]# kinit george@JOVV.HADOOP.COM
    Password for george@JOVV.HADOOP.COM:
    [root@ip-172-31-2-135 ec2-user]# beeline
    Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
    Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
    Beeline version 1.1.0-cdh5.9.3 by Apache Hive
    beeline> SHOW TABLES;
    No current connection
    beeline> !connect jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-2-135.eu-west-1.compute.internal@JOVV.HADOOP.COM
    scan complete in 3ms
    Connecting to jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-2-135.eu-west-1.compute.internal@JOVV.HADOOP.COM
    HS2 may be unavailable, check server status
    Error: Could not open client transport with JDBC Uri: jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-2-135.eu-west-1.compute.internal@JOVV.HADOOP.COM: Peer indicated failure: GSS initiate failed (state=08S01,code=0)
    beeline> !connect jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-15-191.eu-west-1.compute.internal@JOVV.HADOOP.COM
    Connecting to jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-15-191.eu-west-1.compute.internal@JOVV.HADOOP.COM
    Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
    Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
    Transaction isolation: TRANSACTION_REPEATABLE_READ
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> SHOW TABLES;
    INFO  : Compiling command(queryId=hive_20180315082929_102d6d48-a93c-480a-9f51-c0b321ee69a3): SHOW TABLES
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315082929_102d6d48-a93c-480a-9f51-c0b321ee69a3); Time taken: 0.068 seconds
    INFO  : Executing command(queryId=hive_20180315082929_102d6d48-a93c-480a-9f51-c0b321ee69a3): SHOW TABLES
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315082929_102d6d48-a93c-480a-9f51-c0b321ee69a3); Time taken: 0.241 seconds
    INFO  : OK
    +------------+--+
    |  tab_name  |
    +------------+--+
    | customers  |
    | sample_07  |
    | sample_08  |
    | web_logs   |
    +------------+--+
    4 rows selected (0.428 seconds)
```

### Ferdinand

```
    [root@ip-172-31-2-135 ec2-user]# kinit ferdinand@JOVV.HADOOP.COM
    Password for ferdinand@JOVV.HADOOP.COM:
    [root@ip-172-31-2-135 ec2-user]# beeline
    Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
    Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
    Beeline version 1.1.0-cdh5.9.3 by Apache Hive
    beeline> !connect jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-15-191.eu-west-1.compute.internal@JOVV.HADOOP.COM
    scan complete in 2ms
    Connecting to jdbc:hive2://ip-172-31-15-191.eu-west-1.compute.internal:10000/default;principal=hive/ip-172-31-15-191.eu-west-1.compute.internal@JOVV.HADOOP.COM
    Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
    Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
    Transaction isolation: TRANSACTION_REPEATABLE_READ
    0: jdbc:hive2://ip-172-31-15-191.eu-west-1.co> SHOW TABLES;
    INFO  : Compiling command(queryId=hive_20180315083636_9b12e847-c15c-454f-bff2-e9514915c6d7): SHOW TABLES
    INFO  : Semantic Analysis Completed
    INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
    INFO  : Completed compiling command(queryId=hive_20180315083636_9b12e847-c15c-454f-bff2-e9514915c6d7); Time taken: 0.061 seconds
    INFO  : Executing command(queryId=hive_20180315083636_9b12e847-c15c-454f-bff2-e9514915c6d7): SHOW TABLES
    INFO  : Starting task [Stage-0:DDL] in serial mode
    INFO  : Completed executing command(queryId=hive_20180315083636_9b12e847-c15c-454f-bff2-e9514915c6d7); Time taken: 0.243 seconds
    INFO  : OK
    +------------+--+
    |  tab_name  |
    +------------+--+
    | sample_07  |
    +------------+--+
    1 row selected (0.419 seconds)
```