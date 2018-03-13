# Storage Labs

## Test HDFS Snapshots

```
    su jovv
    hdfs dfs -mkdir /user/jovv/precious
```

Uploaded SEBC.zip to /tmp via MobaXterm FTP.

```
    hdfs dfs -copyFromLocal /tmp/SEBC.zip /user/jovv/precious/
    hdfs dfs -ls -h /user/jovv/precious
```

Enable snapshot for /user/jovv/precious
Take a snaphot of /user/jovv/precious

Try to delete the directory:

```
    hdfs dfs -rm -r /user/jovv/precious
```

Output:

```
    rm: Failed to move to trash: hdfs://ip-172-31-15-191.eu-west-1.compute.internal:8020/user/jovv/precious: The directory /user/jovv/precious cannot be deleted since /user/jovv/precious is snapshottable and already has snapshots    
```

Delete the file:

```
    hdfs dfs -rm /user/jovv/precious/SEBC.zip
```

Output:

```
    18/03/13 12:23:02 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-15-191.eu-west-1.compute.internal:8020/user/jovv/precious/SEBC.zip' to trash at: hdfs://ip-172-31-15-191.eu-west-1.compute.internal:8020/user/jovv/.Trash/Current/user/jovv/precious/SEBC.zip
```

Restore directory from snapshot via Cloudera Manager.
