# HDFS Testing


Job output:

```
    [hilary@ip-172-31-0-159 ec2-user]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -D dfs.block.size=67108864 -D mapred.map.tasks=16 -D mapreduce.map.java.opts=-Xmx768m 65536000 /user/hilary/tgen
    18/03/16 10:04:20 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-0-159.eu-west-1.compute.internal/172.31.0.159:8032
    18/03/16 10:04:21 INFO terasort.TeraGen: Generating 65536000 using 16
    18/03/16 10:04:21 INFO mapreduce.JobSubmitter: number of splits:16
    18/03/16 10:04:21 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
    18/03/16 10:04:21 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
    18/03/16 10:04:21 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1521193591211_0001
    18/03/16 10:04:21 INFO impl.YarnClientImpl: Submitted application application_1521193591211_0001
    18/03/16 10:04:22 INFO mapreduce.Job: The url to track the job: http://ip-172-31-0-159.eu-west-1.compute.internal:8088/proxy/application_1521193591211_0001/
    18/03/16 10:04:22 INFO mapreduce.Job: Running job: job_1521193591211_0001
    18/03/16 10:04:30 INFO mapreduce.Job: Job job_1521193591211_0001 running in uber mode : false
    18/03/16 10:04:30 INFO mapreduce.Job:  map 0% reduce 0%
    18/03/16 10:04:43 INFO mapreduce.Job:  map 6% reduce 0%
    18/03/16 10:04:51 INFO mapreduce.Job:  map 26% reduce 0%
    18/03/16 10:04:57 INFO mapreduce.Job:  map 27% reduce 0%
    18/03/16 10:05:00 INFO mapreduce.Job:  map 29% reduce 0%
    18/03/16 10:05:02 INFO mapreduce.Job:  map 30% reduce 0%
    18/03/16 10:05:03 INFO mapreduce.Job:  map 33% reduce 0%
    18/03/16 10:05:06 INFO mapreduce.Job:  map 38% reduce 0%
    18/03/16 10:05:21 INFO mapreduce.Job:  map 52% reduce 0%
    18/03/16 10:05:27 INFO mapreduce.Job:  map 56% reduce 0%
    18/03/16 10:05:33 INFO mapreduce.Job:  map 66% reduce 0%
    18/03/16 10:05:34 INFO mapreduce.Job:  map 67% reduce 0%
    18/03/16 10:05:36 INFO mapreduce.Job:  map 69% reduce 0%
    18/03/16 10:05:49 INFO mapreduce.Job:  map 73% reduce 0%
    18/03/16 10:05:51 INFO mapreduce.Job:  map 78% reduce 0%
    18/03/16 10:05:53 INFO mapreduce.Job:  map 81% reduce 0%
    18/03/16 10:05:54 INFO mapreduce.Job:  map 83% reduce 0%
    18/03/16 10:05:55 INFO mapreduce.Job:  map 85% reduce 0%
    18/03/16 10:05:58 INFO mapreduce.Job:  map 88% reduce 0%
    18/03/16 10:06:00 INFO mapreduce.Job:  map 89% reduce 0%
    18/03/16 10:06:01 INFO mapreduce.Job:  map 91% reduce 0%
    18/03/16 10:06:02 INFO mapreduce.Job:  map 92% reduce 0%
    18/03/16 10:06:04 INFO mapreduce.Job:  map 93% reduce 0%
    18/03/16 10:06:06 INFO mapreduce.Job:  map 94% reduce 0%
    18/03/16 10:06:08 INFO mapreduce.Job:  map 95% reduce 0%
    18/03/16 10:06:10 INFO mapreduce.Job:  map 99% reduce 0%
    18/03/16 10:06:11 INFO mapreduce.Job:  map 100% reduce 0%
    18/03/16 10:06:11 INFO mapreduce.Job: Job job_1521193591211_0001 completed successfully
    18/03/16 10:06:11 INFO mapreduce.Job: Counters: 31
            File System Counters
                    FILE: Number of bytes read=0
                    FILE: Number of bytes written=2366550
                    FILE: Number of read operations=0
                    FILE: Number of large read operations=0
                    FILE: Number of write operations=0
                    HDFS: Number of bytes read=1368
                    HDFS: Number of bytes written=6553600000
                    HDFS: Number of read operations=64
                    HDFS: Number of large read operations=0
                    HDFS: Number of write operations=32
            Job Counters
                    Launched map tasks=16
                    Other local map tasks=16
                    Total time spent by all maps in occupied slots (ms)=462152
                    Total time spent by all reduces in occupied slots (ms)=0
                    Total time spent by all map tasks (ms)=462152
                    Total vcore-milliseconds taken by all map tasks=462152
                    Total megabyte-milliseconds taken by all map tasks=473243648
            Map-Reduce Framework
                    Map input records=65536000
                    Map output records=65536000
                    Input split bytes=1368
                    Spilled Records=0
                    Failed Shuffles=0
                    Merged Map outputs=0
                    GC time elapsed (ms)=1887
                    CPU time spent (ms)=161110
                    Physical memory (bytes) snapshot=5634019328
                    Virtual memory (bytes) snapshot=43801804800
                    Total committed heap usage (bytes)=5398069248
            org.apache.hadoop.examples.terasort.TeraGen$Counters
                    CHECKSUM=140750829423462787
            File Input Format Counters
                    Bytes Read=0
            File Output Format Counters
                    Bytes Written=6553600000
```

Time output:

```
    real    1m53.606s
    user    0m9.115s
    sys     0m0.639s
```

```
    [hilary@ip-172-31-0-159 ec2-user]$ hdfs dfs -ls /user/hilary/tgen
    Found 17 items
    -rw-r--r--   3 hilary datasci          0 2018-03-16 10:06 /user/hilary/tgen/_SUCCESS
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00000
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00001
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00002
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00003
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:04 /user/hilary/tgen/part-m-00004
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00005
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00006
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00007
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00008
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00009
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:05 /user/hilary/tgen/part-m-00010
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:06 /user/hilary/tgen/part-m-00011
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:06 /user/hilary/tgen/part-m-00012
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:06 /user/hilary/tgen/part-m-00013
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:06 /user/hilary/tgen/part-m-00014
    -rw-r--r--   3 hilary datasci  409600000 2018-03-16 10:06 /user/hilary/tgen/part-m-00015
```

```
    [hilary@ip-172-31-0-159 ec2-user]$ hadoop fsck -blocks /user/hilary
    DEPRECATED: Use of this script to execute hdfs command is deprecated.
    Instead use the hdfs command for it.

    Connecting to namenode via http://ip-172-31-0-159.eu-west-1.compute.internal:50070/fsck?ugi=hilary&blocks=1&path=%2Fuser%2Fhilary
    FSCK started by hilary (auth:SIMPLE) from /172.31.0.159 for path /user/hilary at Fri Mar 16 10:08:35 UTC 2018
    .................Status: HEALTHY
    Total size:    6553600000 B
    Total dirs:    3
    Total files:   17
    Total symlinks:                0
    Total blocks (validated):      112 (avg. block size 58514285 B)
    Minimally replicated blocks:   112 (100.0 %)
    Over-replicated blocks:        0 (0.0 %)
    Under-replicated blocks:       0 (0.0 %)
    Mis-replicated blocks:         0 (0.0 %)
    Default replication factor:    3
    Average block replication:     3.0
    Corrupt blocks:                0
    Missing replicas:              0 (0.0 %)
    Number of data-nodes:          3
    Number of racks:               1
    FSCK ended at Fri Mar 16 10:08:35 UTC 2018 in 10 milliseconds


    The filesystem under path '/user/hilary' is HEALTHY
```

