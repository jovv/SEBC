# Storage Labs

## HDFS Lab: Test HDFS throughput

Create new linux user on all nodes

```
    sudo su root -
    useradd -m jovv
    passwd jovv
    exit
    ls -lAh /home
```

Create an HDFS directory for the new user

```
    sudo su hdfs -
    hdfs dfs -mkdir /user/jovv
    hdfs dfs -chown jovv:jovv /user/jovv
    exit
```

Generate teragen data

```
    su jovv
    time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -D dfs.block.size=33554432 -D mapred.map.tasks=4 107374182 /user/jovv/terasort-test
```

Job Output:
```
    File System Counters
            FILE: Number of bytes read=0
            FILE: Number of bytes written=494120
            FILE: Number of read operations=0
            FILE: Number of large read operations=0
            FILE: Number of write operations=0
            HDFS: Number of bytes read=344
            HDFS: Number of bytes written=10737418200
            HDFS: Number of read operations=16
            HDFS: Number of large read operations=0
            HDFS: Number of write operations=8
    Job Counters
            Launched map tasks=4
            Other local map tasks=4
            Total time spent by all maps in occupied slots (ms)=601021
            Total time spent by all reduces in occupied slots (ms)=0
            Total time spent by all map tasks (ms)=601021
            Total vcore-seconds taken by all map tasks=601021
            Total megabyte-seconds taken by all map tasks=615445504
    Map-Reduce Framework
            Map input records=107374182
            Map output records=107374182
            Input split bytes=344
            Spilled Records=0
            Failed Shuffles=0
            Merged Map outputs=0
            GC time elapsed (ms)=726
            CPU time spent (ms)=177190
            Physical memory (bytes) snapshot=1410240512
            Virtual memory (bytes) snapshot=11152736256
            Total committed heap usage (bytes)=829947904
    org.apache.hadoop.examples.terasort.TeraGen$Counters
            CHECKSUM=230593859918397906
    File Input Format Counters
            Bytes Read=0
    File Output Format Counters
            Bytes Written=10737418200

```

Time output:

```
    real    2m43.944s
    user    0m7.718s
    sys     0m0.600s
```

Verify files:

```
    hdfs dfs -ls -h /user/jovv/terasort-test
```

Output:

```
    Found 5 items
    -rw-r--r--   3 jovv jovv          0 2018-03-13 11:08 /user/jovv/terasort-test/_SUCCESS
    -rw-r--r--   3 jovv jovv      2.5 G 2018-03-13 11:08 /user/jovv/terasort-test/part-m-00000
    -rw-r--r--   3 jovv jovv      2.5 G 2018-03-13 11:08 /user/jovv/terasort-test/part-m-00001
    -rw-r--r--   3 jovv jovv      2.5 G 2018-03-13 11:08 /user/jovv/terasort-test/part-m-00002
    -rw-r--r--   3 jovv jovv      2.5 G 2018-03-13 11:08 /user/jovv/terasort-test/part-m-00003
```

Run terasort

```
    time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/jovv/terasort-test /user/jovv/terasort-output
```

Output:

```
    File System Counters
            FILE: Number of bytes read=4781338100
            FILE: Number of bytes written=9484880586
            FILE: Number of read operations=0
            FILE: Number of large read operations=0
            FILE: Number of write operations=0
            HDFS: Number of bytes read=10737468440
            HDFS: Number of bytes written=10737418200
            HDFS: Number of read operations=978
            HDFS: Number of large read operations=0
            HDFS: Number of write operations=12
    Job Counters
            Launched map tasks=320
            Launched reduce tasks=6
            Data-local map tasks=320
            Total time spent by all maps in occupied slots (ms)=2182200
            Total time spent by all reduces in occupied slots (ms)=713865
            Total time spent by all map tasks (ms)=2182200
            Total time spent by all reduce tasks (ms)=713865
            Total vcore-seconds taken by all map tasks=2182200
            Total vcore-seconds taken by all reduce tasks=713865
            Total megabyte-seconds taken by all map tasks=2234572800
            Total megabyte-seconds taken by all reduce tasks=730997760
    Map-Reduce Framework
            Map input records=107374182
            Map output records=107374182
            Map output bytes=10952166564
            Map output materialized bytes=4662784852
            Input split bytes=50240
            Combine input records=0
            Combine output records=0
            Reduce input groups=107374182
            Reduce shuffle bytes=4662784852
            Reduce input records=107374182
            Reduce output records=107374182
            Spilled Records=214748364
            Shuffled Maps =1920
            Failed Shuffles=0
            Merged Map outputs=1920
            GC time elapsed (ms)=37712
            CPU time spent (ms)=1601530
            Physical memory (bytes) snapshot=151411564544
            Virtual memory (bytes) snapshot=908313755648
            Total committed heap usage (bytes)=155767013376
    Shuffle Errors
            BAD_ID=0
            CONNECTION=0
            IO_ERROR=0
            WRONG_LENGTH=0
            WRONG_MAP=0
            WRONG_REDUCE=0
    File Input Format Counters
            Bytes Read=10737418200
    File Output Format Counters
            Bytes Written=10737418200
    18/03/13 11:20:56 INFO terasort.TeraSort: done
```

Time output:

```
    real    7m27.239s
    user    0m11.178s
    sys     0m0.735s
```

