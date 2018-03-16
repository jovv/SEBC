# Pi

```
    [root@ip-172-31-0-159 tmp]# kinit anupam@JOVV.NL
    Password for anupam@JOVV.NL:
    [root@ip-172-31-0-159 tmp]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi 50 100
    Number of Maps  = 50
    Samples per Map = 100
    Wrote input for Map #0
    Wrote input for Map #1
    Wrote input for Map #2
    Wrote input for Map #3
    Wrote input for Map #4
    Wrote input for Map #5
    Wrote input for Map #6
    Wrote input for Map #7
    Wrote input for Map #8
    Wrote input for Map #9
    Wrote input for Map #10
    Wrote input for Map #11
    Wrote input for Map #12
    Wrote input for Map #13
    Wrote input for Map #14
    Wrote input for Map #15
    Wrote input for Map #16
    Wrote input for Map #17
    Wrote input for Map #18
    Wrote input for Map #19
    Wrote input for Map #20
    Wrote input for Map #21
    Wrote input for Map #22
    Wrote input for Map #23
    Wrote input for Map #24
    Wrote input for Map #25
    Wrote input for Map #26
    Wrote input for Map #27
    Wrote input for Map #28
    Wrote input for Map #29
    Wrote input for Map #30
    Wrote input for Map #31
    Wrote input for Map #32
    Wrote input for Map #33
    Wrote input for Map #34
    Wrote input for Map #35
    Wrote input for Map #36
    Wrote input for Map #37
    Wrote input for Map #38
    Wrote input for Map #39
    Wrote input for Map #40
    Wrote input for Map #41
    Wrote input for Map #42
    Wrote input for Map #43
    Wrote input for Map #44
    Wrote input for Map #45
    Wrote input for Map #46
    Wrote input for Map #47
    Wrote input for Map #48
    Wrote input for Map #49
    Starting Job
    18/03/16 10:44:53 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-0-159.eu-west-1.compute.internal/172.31.0.159:8032
    18/03/16 10:44:53 INFO hdfs.DFSClient: Created token for anupam: HDFS_DELEGATION_TOKEN owner=anupam@JOVV.NL, renewer=yarn, realUser=, issueDate=1521197093969, maxDate=1521801893969, sequenceNumber=2, masterKeyId=2 on 172.31.0.159:8020
    18/03/16 10:44:53 INFO security.TokenCache: Got dt for hdfs://ip-172-31-0-159.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.0.159:8020, Ident: (token for anupam: HDFS_DELEGATION_TOKEN owner=anupam@JOVV.NL, renewer=yarn, realUser=, issueDate=1521197093969, maxDate=1521801893969, sequenceNumber=2, masterKeyId=2)
    18/03/16 10:44:54 INFO input.FileInputFormat: Total input paths to process : 50
    18/03/16 10:44:54 INFO mapreduce.JobSubmitter: number of splits:50
    18/03/16 10:44:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1521196414031_0002
    18/03/16 10:44:54 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.0.159:8020, Ident: (token for anupam: HDFS_DELEGATION_TOKEN owner=anupam@JOVV.NL, renewer=yarn, realUser=, issueDate=1521197093969, maxDate=1521801893969, sequenceNumber=2, masterKeyId=2)
    18/03/16 10:44:54 INFO impl.YarnClientImpl: Submitted application application_1521196414031_0002
    18/03/16 10:44:54 INFO mapreduce.Job: The url to track the job: http://ip-172-31-0-159.eu-west-1.compute.internal:8088/proxy/application_1521196414031_0002/
    18/03/16 10:44:54 INFO mapreduce.Job: Running job: job_1521196414031_0002
    18/03/16 10:45:04 INFO mapreduce.Job: Job job_1521196414031_0002 running in uber mode : false
    18/03/16 10:45:04 INFO mapreduce.Job:  map 0% reduce 0%
    18/03/16 10:45:09 INFO mapreduce.Job:  map 2% reduce 0%
    18/03/16 10:45:14 INFO mapreduce.Job:  map 12% reduce 0%
    18/03/16 10:45:18 INFO mapreduce.Job:  map 14% reduce 0%
    18/03/16 10:45:19 INFO mapreduce.Job:  map 20% reduce 0%
    18/03/16 10:45:20 INFO mapreduce.Job:  map 22% reduce 0%
    18/03/16 10:45:22 INFO mapreduce.Job:  map 24% reduce 0%
    18/03/16 10:45:24 INFO mapreduce.Job:  map 30% reduce 0%
    18/03/16 10:45:25 INFO mapreduce.Job:  map 32% reduce 0%
    18/03/16 10:45:26 INFO mapreduce.Job:  map 34% reduce 0%
    18/03/16 10:45:29 INFO mapreduce.Job:  map 38% reduce 0%
    18/03/16 10:45:30 INFO mapreduce.Job:  map 44% reduce 0%
    18/03/16 10:45:34 INFO mapreduce.Job:  map 50% reduce 0%
    18/03/16 10:45:35 INFO mapreduce.Job:  map 54% reduce 0%
    18/03/16 10:45:38 INFO mapreduce.Job:  map 56% reduce 0%
    18/03/16 10:45:39 INFO mapreduce.Job:  map 60% reduce 0%
    18/03/16 10:45:40 INFO mapreduce.Job:  map 64% reduce 0%
    18/03/16 10:45:42 INFO mapreduce.Job:  map 66% reduce 0%
    18/03/16 10:45:44 INFO mapreduce.Job:  map 70% reduce 0%
    18/03/16 10:45:45 INFO mapreduce.Job:  map 74% reduce 0%
    18/03/16 10:45:46 INFO mapreduce.Job:  map 76% reduce 0%
    18/03/16 10:45:49 INFO mapreduce.Job:  map 80% reduce 0%
    18/03/16 10:45:50 INFO mapreduce.Job:  map 86% reduce 0%
    18/03/16 10:45:54 INFO mapreduce.Job:  map 90% reduce 0%
    18/03/16 10:45:55 INFO mapreduce.Job:  map 96% reduce 0%
    18/03/16 10:45:59 INFO mapreduce.Job:  map 98% reduce 0%
    18/03/16 10:46:00 INFO mapreduce.Job:  map 100% reduce 0%
    18/03/16 10:46:01 INFO mapreduce.Job:  map 100% reduce 100%
    18/03/16 10:46:01 INFO mapreduce.Job: Job job_1521196414031_0002 completed successfully
    18/03/16 10:46:01 INFO mapreduce.Job: Counters: 49
            File System Counters
                    FILE: Number of bytes read=259
                    FILE: Number of bytes written=7627362
                    FILE: Number of read operations=0
                    FILE: Number of large read operations=0
                    FILE: Number of write operations=0
                    HDFS: Number of bytes read=14990
                    HDFS: Number of bytes written=215
                    HDFS: Number of read operations=203
                    HDFS: Number of large read operations=0
                    HDFS: Number of write operations=3
            Job Counters
                    Launched map tasks=50
                    Launched reduce tasks=1
                    Data-local map tasks=50
                    Total time spent by all maps in occupied slots (ms)=210762
                    Total time spent by all reduces in occupied slots (ms)=6142
                    Total time spent by all map tasks (ms)=210762
                    Total time spent by all reduce tasks (ms)=6142
                    Total vcore-milliseconds taken by all map tasks=210762
                    Total vcore-milliseconds taken by all reduce tasks=6142
                    Total megabyte-milliseconds taken by all map tasks=215820288
                    Total megabyte-milliseconds taken by all reduce tasks=6289408
            Map-Reduce Framework
                    Map input records=50
                    Map output records=100
                    Map output bytes=900
                    Map output materialized bytes=1700
                    Input split bytes=9090
                    Combine input records=0
                    Combine output records=0
                    Reduce input groups=2
                    Reduce shuffle bytes=1700
                    Reduce input records=100
                    Reduce output records=0
                    Spilled Records=200
                    Shuffled Maps =50
                    Failed Shuffles=0
                    Merged Map outputs=50
                    GC time elapsed (ms)=3491
                    CPU time spent (ms)=39460
                    Physical memory (bytes) snapshot=22803021824
                    Virtual memory (bytes) snapshot=142312153088
                    Total committed heap usage (bytes)=23621795840
            Shuffle Errors
                    BAD_ID=0
                    CONNECTION=0
                    IO_ERROR=0
                    WRONG_LENGTH=0
                    WRONG_MAP=0
                    WRONG_REDUCE=0
            File Input Format Counters
                    Bytes Read=5900
            File Output Format Counters
                    Bytes Written=97
    Job Finished in 67.85 seconds
    Estimated value of Pi is 3.14160000000000000000

    real    1m12.212s
    user    0m9.923s
    sys     0m0.705s
```