# Terasort

```
    [root@ip-172-31-0-159 tmp]# klist -ef
    Ticket cache: FILE:/tmp/krb5cc_0
    Default principal: hilary@JOVV.NL

    Valid starting       Expires              Service principal
    03/16/2018 10:29:17  03/17/2018 10:29:17  krbtgt/JOVV.NL@JOVV.NL
            renew until 03/23/2018 10:29:17, Flags: FRI
            Etype (skey, tkt): arcfour-hmac, aes256-cts-hmac-sha1-96
    [root@ip-172-31-0-159 tmp]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/hilary/tgen /user/hilary/tsort
    18/03/16 10:37:57 INFO terasort.TeraSort: starting
    18/03/16 10:37:59 INFO hdfs.DFSClient: Created token for hilary: HDFS_DELEGATION_TOKEN owner=hilary@JOVV.NL, renewer=yarn, realUser=, issueDate=1521196679484, maxDate=1521801479484, sequenceNumber=1, masterKeyId=2 on 172.31.0.159:8020
    18/03/16 10:37:59 INFO security.TokenCache: Got dt for hdfs://ip-172-31-0-159.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.0.159:8020, Ident: (token for hilary: HDFS_DELEGATION_TOKEN owner=hilary@JOVV.NL, renewer=yarn, realUser=, issueDate=1521196679484, maxDate=1521801479484, sequenceNumber=1, masterKeyId=2)
    18/03/16 10:37:59 INFO input.FileInputFormat: Total input paths to process : 16
    Spent 481ms computing base-splits.
    Spent 5ms computing TeraScheduler splits.
    Computing input splits took 488ms
    Sampling 10 splits of 112
    Making 6 from 100000 sampled records
    Computing parititions took 791ms
    Spent 1281ms computing partitions.
    18/03/16 10:38:00 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-0-159.eu-west-1.compute.internal/172.31.0.159:8032
    18/03/16 10:38:01 INFO mapreduce.JobSubmitter: number of splits:112
    18/03/16 10:38:01 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1521196414031_0001
    18/03/16 10:38:01 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.0.159:8020, Ident: (token for hilary: HDFS_DELEGATION_TOKEN owner=hilary@JOVV.NL, renewer=yarn, realUser=, issueDate=1521196679484, maxDate=1521801479484, sequenceNumber=1, masterKeyId=2)
    18/03/16 10:38:02 INFO impl.YarnClientImpl: Submitted application application_1521196414031_0001
    18/03/16 10:38:02 INFO mapreduce.Job: The url to track the job: http://ip-172-31-0-159.eu-west-1.compute.internal:8088/proxy/application_1521196414031_0001/
    18/03/16 10:38:02 INFO mapreduce.Job: Running job: job_1521196414031_0001
    18/03/16 10:38:13 INFO mapreduce.Job: Job job_1521196414031_0001 running in uber mode : false
    18/03/16 10:38:13 INFO mapreduce.Job:  map 0% reduce 0%
    18/03/16 10:38:22 INFO mapreduce.Job:  map 1% reduce 0%
    18/03/16 10:38:28 INFO mapreduce.Job:  map 5% reduce 0%
    18/03/16 10:38:34 INFO mapreduce.Job:  map 6% reduce 0%
    18/03/16 10:38:36 INFO mapreduce.Job:  map 10% reduce 0%
    18/03/16 10:38:40 INFO mapreduce.Job:  map 11% reduce 0%
    18/03/16 10:38:44 INFO mapreduce.Job:  map 13% reduce 0%
    18/03/16 10:38:45 INFO mapreduce.Job:  map 14% reduce 0%
    18/03/16 10:38:46 INFO mapreduce.Job:  map 15% reduce 0%
    18/03/16 10:38:52 INFO mapreduce.Job:  map 16% reduce 0%
    18/03/16 10:38:53 INFO mapreduce.Job:  map 20% reduce 0%
    18/03/16 10:38:58 INFO mapreduce.Job:  map 21% reduce 0%
    18/03/16 10:39:01 INFO mapreduce.Job:  map 23% reduce 0%
    18/03/16 10:39:02 INFO mapreduce.Job:  map 24% reduce 0%
    18/03/16 10:39:04 INFO mapreduce.Job:  map 25% reduce 0%
    18/03/16 10:39:09 INFO mapreduce.Job:  map 26% reduce 0%
    18/03/16 10:39:10 INFO mapreduce.Job:  map 29% reduce 0%
    18/03/16 10:39:16 INFO mapreduce.Job:  map 30% reduce 0%
    18/03/16 10:39:17 INFO mapreduce.Job:  map 31% reduce 0%
    18/03/16 10:39:18 INFO mapreduce.Job:  map 33% reduce 0%
    18/03/16 10:39:19 INFO mapreduce.Job:  map 34% reduce 0%
    18/03/16 10:39:22 INFO mapreduce.Job:  map 35% reduce 0%
    18/03/16 10:39:25 INFO mapreduce.Job:  map 36% reduce 0%
    18/03/16 10:39:26 INFO mapreduce.Job:  map 38% reduce 0%
    18/03/16 10:39:28 INFO mapreduce.Job:  map 39% reduce 0%
    18/03/16 10:39:33 INFO mapreduce.Job:  map 40% reduce 0%
    18/03/16 10:39:34 INFO mapreduce.Job:  map 43% reduce 0%
    18/03/16 10:39:35 INFO mapreduce.Job:  map 44% reduce 0%
    18/03/16 10:39:40 INFO mapreduce.Job:  map 45% reduce 0%
    18/03/16 10:39:41 INFO mapreduce.Job:  map 46% reduce 0%
    18/03/16 10:39:42 INFO mapreduce.Job:  map 47% reduce 0%
    18/03/16 10:39:43 INFO mapreduce.Job:  map 48% reduce 0%
    18/03/16 10:39:46 INFO mapreduce.Job:  map 49% reduce 0%
    18/03/16 10:39:50 INFO mapreduce.Job:  map 51% reduce 0%
    18/03/16 10:39:51 INFO mapreduce.Job:  map 53% reduce 0%
    18/03/16 10:39:52 INFO mapreduce.Job:  map 54% reduce 0%
    18/03/16 10:39:59 INFO mapreduce.Job:  map 58% reduce 0%
    18/03/16 10:40:05 INFO mapreduce.Job:  map 59% reduce 0%
    18/03/16 10:40:06 INFO mapreduce.Job:  map 60% reduce 0%
    18/03/16 10:40:07 INFO mapreduce.Job:  map 62% reduce 0%
    18/03/16 10:40:08 INFO mapreduce.Job:  map 63% reduce 0%
    18/03/16 10:40:14 INFO mapreduce.Job:  map 65% reduce 0%
    18/03/16 10:40:15 INFO mapreduce.Job:  map 66% reduce 0%
    18/03/16 10:40:16 INFO mapreduce.Job:  map 67% reduce 0%
    18/03/16 10:40:17 INFO mapreduce.Job:  map 68% reduce 0%
    18/03/16 10:40:22 INFO mapreduce.Job:  map 69% reduce 0%
    18/03/16 10:40:23 INFO mapreduce.Job:  map 71% reduce 0%
    18/03/16 10:40:24 INFO mapreduce.Job:  map 72% reduce 0%
    18/03/16 10:40:29 INFO mapreduce.Job:  map 73% reduce 0%
    18/03/16 10:40:30 INFO mapreduce.Job:  map 74% reduce 0%
    18/03/16 10:40:31 INFO mapreduce.Job:  map 76% reduce 0%
    18/03/16 10:40:32 INFO mapreduce.Job:  map 77% reduce 0%
    18/03/16 10:40:35 INFO mapreduce.Job:  map 78% reduce 0%
    18/03/16 10:40:38 INFO mapreduce.Job:  map 79% reduce 0%
    18/03/16 10:40:39 INFO mapreduce.Job:  map 80% reduce 0%
    18/03/16 10:40:40 INFO mapreduce.Job:  map 81% reduce 0%
    18/03/16 10:40:41 INFO mapreduce.Job:  map 82% reduce 0%
    18/03/16 10:40:45 INFO mapreduce.Job:  map 83% reduce 0%
    18/03/16 10:40:46 INFO mapreduce.Job:  map 84% reduce 0%
    18/03/16 10:40:47 INFO mapreduce.Job:  map 86% reduce 0%
    18/03/16 10:40:48 INFO mapreduce.Job:  map 87% reduce 0%
    18/03/16 10:40:52 INFO mapreduce.Job:  map 88% reduce 0%
    18/03/16 10:40:58 INFO mapreduce.Job:  map 89% reduce 0%
    18/03/16 10:41:00 INFO mapreduce.Job:  map 89% reduce 5%
    18/03/16 10:41:01 INFO mapreduce.Job:  map 90% reduce 5%
    18/03/16 10:41:03 INFO mapreduce.Job:  map 91% reduce 10%
    18/03/16 10:41:04 INFO mapreduce.Job:  map 91% reduce 15%
    18/03/16 10:41:05 INFO mapreduce.Job:  map 92% reduce 15%
    18/03/16 10:41:07 INFO mapreduce.Job:  map 93% reduce 15%
    18/03/16 10:41:10 INFO mapreduce.Job:  map 94% reduce 15%
    18/03/16 10:41:12 INFO mapreduce.Job:  map 95% reduce 16%
    18/03/16 10:41:16 INFO mapreduce.Job:  map 96% reduce 16%
    18/03/16 10:41:21 INFO mapreduce.Job:  map 97% reduce 16%
    18/03/16 10:41:23 INFO mapreduce.Job:  map 98% reduce 16%
    18/03/16 10:41:26 INFO mapreduce.Job:  map 99% reduce 16%
    18/03/16 10:41:28 INFO mapreduce.Job:  map 100% reduce 16%
    18/03/16 10:41:31 INFO mapreduce.Job:  map 100% reduce 23%
    18/03/16 10:41:34 INFO mapreduce.Job:  map 100% reduce 30%
    18/03/16 10:41:35 INFO mapreduce.Job:  map 100% reduce 37%
    18/03/16 10:41:37 INFO mapreduce.Job:  map 100% reduce 40%
    18/03/16 10:41:40 INFO mapreduce.Job:  map 100% reduce 42%
    18/03/16 10:41:41 INFO mapreduce.Job:  map 100% reduce 46%
    18/03/16 10:41:43 INFO mapreduce.Job:  map 100% reduce 52%
    18/03/16 10:41:45 INFO mapreduce.Job:  map 100% reduce 54%
    18/03/16 10:41:46 INFO mapreduce.Job:  map 100% reduce 65%
    18/03/16 10:41:49 INFO mapreduce.Job:  map 100% reduce 72%
    18/03/16 10:41:52 INFO mapreduce.Job:  map 100% reduce 76%
    18/03/16 10:41:55 INFO mapreduce.Job:  map 100% reduce 80%
    18/03/16 10:41:56 INFO mapreduce.Job:  map 100% reduce 91%
    18/03/16 10:41:58 INFO mapreduce.Job:  map 100% reduce 95%
    18/03/16 10:42:02 INFO mapreduce.Job:  map 100% reduce 97%
    18/03/16 10:42:08 INFO mapreduce.Job:  map 100% reduce 100%
    18/03/16 10:42:08 INFO mapreduce.Job: Job job_1521196414031_0001 completed successfully
    18/03/16 10:42:08 INFO mapreduce.Job: Counters: 49
            File System Counters
                    FILE: Number of bytes read=2911915286
                    FILE: Number of bytes written=5781422140
                    FILE: Number of read operations=0
                    FILE: Number of large read operations=0
                    FILE: Number of write operations=0
                    HDFS: Number of bytes read=6553616688
                    HDFS: Number of bytes written=6553600000
                    HDFS: Number of read operations=354
                    HDFS: Number of large read operations=0
                    HDFS: Number of write operations=12
            Job Counters
                    Launched map tasks=112
                    Launched reduce tasks=6
                    Data-local map tasks=112
                    Total time spent by all maps in occupied slots (ms)=724498
                    Total time spent by all reduces in occupied slots (ms)=251476
                    Total time spent by all map tasks (ms)=724498
                    Total time spent by all reduce tasks (ms)=251476
                    Total vcore-milliseconds taken by all map tasks=724498
                    Total vcore-milliseconds taken by all reduce tasks=251476
                    Total megabyte-milliseconds taken by all map tasks=741885952
                    Total megabyte-milliseconds taken by all reduce tasks=257511424
            Map-Reduce Framework
                    Map input records=65536000
                    Map output records=65536000
                    Map output bytes=6684672000
                    Map output materialized bytes=2851760024
                    Input split bytes=16688
                    Combine input records=0
                    Combine output records=0
                    Reduce input groups=65536000
                    Reduce shuffle bytes=2851760024
                    Reduce input records=65536000
                    Reduce output records=65536000
                    Spilled Records=131072000
                    Shuffled Maps =672
                    Failed Shuffles=0
                    Merged Map outputs=672
                    GC time elapsed (ms)=14152
                    CPU time spent (ms)=722230
                    Physical memory (bytes) snapshot=59274158080
                    Virtual memory (bytes) snapshot=329517965312
                    Total committed heap usage (bytes)=60472426496
            Shuffle Errors
                    BAD_ID=0
                    CONNECTION=0
                    IO_ERROR=0
                    WRONG_LENGTH=0
                    WRONG_MAP=0
                    WRONG_REDUCE=0
            File Input Format Counters
                    Bytes Read=6553600000
            File Output Format Counters
                    Bytes Written=6553600000
    18/03/16 10:42:08 INFO terasort.TeraSort: done

    real    4m11.867s
    user    0m12.768s
    sys     0m0.816s
```