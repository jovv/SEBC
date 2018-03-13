# Storage Labs

## HDFS Lab: Replicate to another cluster

```
    sudo su hdfs -
    hdfs dfs -mkdir /user/ec2-user
    hdfs dfs -chown ec2-user:ec2-user /user/ec2-user
    hdfs dfs -ls /user
    hdfs dfs -mkdir /user/ec2-user/JeKuOrdina
    hdfs dfs -chown ec2-user:ec2-user /user/ec2-user/JeKuOrdina
    exit

    hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen 5242880 /user/jovv/
    hdfs dfs -ls -h /user/ec2-user/jovv
```

Partner will try to replicate with distCp.
Datanodes of different clusters cannot reach each other.

Alternatively, copy to own cluster.

Setup BDR in Cloudera Manager.
Backups -> Replication Schedules
Create Schedule
Source: HDFS (jovv)
Source path: /user/ec2-user/jovv/
Destination: HDFS(jovv)
Destination path: /user/ec2-user/JeKuOrdina
Schedule: Once

Verify replication:

```
    hdfs dfs -ls -h /user/ec2-user/JeKuOrdina/jovv
```

Verify files and blocks of source directory.

```
    hdfs fsck /user/ec2-user/jovv/ -files -blocks
```

Output:

```
    Connecting to namenode via http://ip-172-31-15-191.eu-west-1.compute.internal:50070
    FSCK started by ec2-user (auth:SIMPLE) from /172.31.2.135 for path /user/ec2-user/jovv/ at Tue Mar 13 10:28:14 UTC 2018
    /user/ec2-user/jovv/ <dir>
    /user/ec2-user/jovv/_SUCCESS 0 bytes, 0 block(s):  OK

    /user/ec2-user/jovv/part-m-00000 262144000 bytes, 2 block(s):  OK
    0. BP-916825808-172.31.15.191-1520872339081:blk_1073742741_1917 len=134217728 Live_repl=3
    1. BP-916825808-172.31.15.191-1520872339081:blk_1073742744_1920 len=127926272 Live_repl=3

    /user/ec2-user/jovv/part-m-00001 262144000 bytes, 2 block(s):  OK
    0. BP-916825808-172.31.15.191-1520872339081:blk_1073742742_1918 len=134217728 Live_repl=3
    1. BP-916825808-172.31.15.191-1520872339081:blk_1073742743_1919 len=127926272 Live_repl=3

    Status: HEALTHY
    Total size:    524288000 B
    Total dirs:    1
    Total files:   3
    Total symlinks:                0
    Total blocks (validated):      4 (avg. block size 131072000 B)
    Minimally replicated blocks:   4 (100.0 %)
    Over-replicated blocks:        0 (0.0 %)
    Under-replicated blocks:       0 (0.0 %)
    Mis-replicated blocks:         0 (0.0 %)
    Default replication factor:    3
    Average block replication:     3.0
    Corrupt blocks:                0
    Missing replicas:              0 (0.0 %)
    Number of data-nodes:          3
    Number of racks:               1
    FSCK ended at Tue Mar 13 10:28:14 UTC 2018 in 2 milliseconds


    The filesystem under path '/user/ec2-user/jovv/' is HEALTHY
```

Verify files and blocks of target directory.

```
    hdfs fsck /user/ec2-user/JeKuOrdina/jovv/ -files -blocks
```

Output:

```
    Connecting to namenode via http://ip-172-31-15-191.eu-west-1.compute.internal:50070
    FSCK started by ec2-user (auth:SIMPLE) from /172.31.2.135 for path /user/ec2-user/JeKuOrdina/jovv/ at Tue Mar 13 10:29:18 UTC 2018
    /user/ec2-user/JeKuOrdina/jovv/ <dir>
    /user/ec2-user/JeKuOrdina/jovv/_SUCCESS 0 bytes, 0 block(s):  OK

    /user/ec2-user/JeKuOrdina/jovv/part-m-00000 262144000 bytes, 2 block(s):  OK
    0. BP-916825808-172.31.15.191-1520872339081:blk_1073742783_1959 len=134217728 Live_repl=3
    1. BP-916825808-172.31.15.191-1520872339081:blk_1073742785_1961 len=127926272 Live_repl=3

    /user/ec2-user/JeKuOrdina/jovv/part-m-00001 262144000 bytes, 2 block(s):  OK
    0. BP-916825808-172.31.15.191-1520872339081:blk_1073742781_1957 len=134217728 Live_repl=3
    1. BP-916825808-172.31.15.191-1520872339081:blk_1073742784_1960 len=127926272 Live_repl=3

    Status: HEALTHY
    Total size:    524288000 B
    Total dirs:    1
    Total files:   3
    Total symlinks:                0
    Total blocks (validated):      4 (avg. block size 131072000 B)
    Minimally replicated blocks:   4 (100.0 %)
    Over-replicated blocks:        0 (0.0 %)
    Under-replicated blocks:       0 (0.0 %)
    Mis-replicated blocks:         0 (0.0 %)
    Default replication factor:    3
    Average block replication:     3.0
    Corrupt blocks:                0
    Missing replicas:              0 (0.0 %)
    Number of data-nodes:          3
    Number of racks:               1
    FSCK ended at Tue Mar 13 10:29:18 UTC 2018 in 1 milliseconds


    The filesystem under path '/user/ec2-user/JeKuOrdina/jovv/' is HEALTHY
```
