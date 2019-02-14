#Output Teragen + Time

[julianjunge@ip-10-0-0-136 smoke]$ time hadoop jar /opt/cloudera/parcels/CDH/jar                                                    s/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 100                                                    000000 /user/julianjunge/teraout
19/02/14 18:08:15 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-                                                    0-128.ec2.internal/10.0.0.128:8032
19/02/14 18:08:15 INFO hdfs.DFSClient: Created token for julianjunge: HDFS_DELEG                                                    ATION_TOKEN owner=julianjunge@EXAMPLE.COM, renewer=yarn, realUser=, issueDate=15                                                    50167695224, maxDate=1550772495224, sequenceNumber=5, masterKeyId=12 on ha-hdfs:                                                    nameservice-ha
19/02/14 18:08:15 INFO security.TokenCache: Got dt for hdfs://nameservice-ha; Ki                                                    nd: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice-ha, Ident: (token for ju                                                    lianjunge: HDFS_DELEGATION_TOKEN owner=julianjunge@EXAMPLE.COM, renewer=yarn, re                                                    alUser=, issueDate=1550167695224, maxDate=1550772495224, sequenceNumber=5, maste                                                    rKeyId=12)
19/02/14 18:08:15 INFO terasort.TeraGen: Generating 100000000 using 4
19/02/14 18:08:15 INFO mapreduce.JobSubmitter: number of splits:4
19/02/14 18:08:15 INFO Configuration.deprecation: mapred.map.tasks is deprecated                                                    . Instead, use mapreduce.job.maps
19/02/14 18:08:15 INFO Configuration.deprecation: dfs.block.size is deprecated.                                                     Instead, use dfs.blocksize
19/02/14 18:08:15 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_15                                                    50163516356_0004
19/02/14 18:08:15 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Serv                                                    ice: ha-hdfs:nameservice-ha, Ident: (token for julianjunge: HDFS_DELEGATION_TOKE                                                    N owner=julianjunge@EXAMPLE.COM, renewer=yarn, realUser=, issueDate=155016769522                                                    4, maxDate=1550772495224, sequenceNumber=5, masterKeyId=12)
19/02/14 18:08:16 INFO impl.YarnClientImpl: Submitted application application_15                                                    50163516356_0004
19/02/14 18:08:16 INFO mapreduce.Job: The url to track the job: http://ip-10-0-0                                                    -128.ec2.internal:8088/proxy/application_1550163516356_0004/
19/02/14 18:08:16 INFO mapreduce.Job: Running job: job_1550163516356_0004
19/02/14 18:08:23 INFO mapreduce.Job: Job job_1550163516356_0004 running in uber                                                     mode : false
19/02/14 18:08:23 INFO mapreduce.Job:  map 0% reduce 0%
19/02/14 18:08:46 INFO mapreduce.Job:  map 13% reduce 0%
19/02/14 18:08:47 INFO mapreduce.Job:  map 25% reduce 0%
19/02/14 18:08:52 INFO mapreduce.Job:  map 32% reduce 0%
19/02/14 18:08:53 INFO mapreduce.Job:  map 38% reduce 0%
19/02/14 18:08:58 INFO mapreduce.Job:  map 46% reduce 0%
19/02/14 18:08:59 INFO mapreduce.Job:  map 53% reduce 0%
19/02/14 18:09:04 INFO mapreduce.Job:  map 60% reduce 0%
19/02/14 18:09:05 INFO mapreduce.Job:  map 67% reduce 0%
19/02/14 18:09:10 INFO mapreduce.Job:  map 71% reduce 0%
19/02/14 18:09:11 INFO mapreduce.Job:  map 74% reduce 0%
19/02/14 18:09:16 INFO mapreduce.Job:  map 77% reduce 0%
19/02/14 18:09:17 INFO mapreduce.Job:  map 81% reduce 0%
19/02/14 18:09:22 INFO mapreduce.Job:  map 84% reduce 0%
19/02/14 18:09:23 INFO mapreduce.Job:  map 88% reduce 0%
19/02/14 18:09:27 INFO mapreduce.Job:  map 94% reduce 0%
19/02/14 18:09:28 INFO mapreduce.Job:  map 100% reduce 0%
19/02/14 18:09:30 INFO mapreduce.Job: Job job_1550163516356_0004 completed successfully
19/02/14 18:09:30 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=608568
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=250218
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=250218
                Total vcore-milliseconds taken by all map tasks=250218
                Total megabyte-milliseconds taken by all map tasks=256223232
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2424
                CPU time spent (ms)=132850
                Physical memory (bytes) snapshot=1211453440
                Virtual memory (bytes) snapshot=6341804032
                Total committed heap usage (bytes)=1391460352
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    1m17.694s
user    0m4.641s
sys     0m0.187s


# Output Tersort + Time

* After completting teragen, my cluster turned inresponsive due to lack of diskvolume. After recovering the cluster, I ran another teragen job to produce a 10kb block.

* Below the results on the terasort job that I ran using this data.

[julianjunge@ip-10-0-0-136 /]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/julianjunge/teragen_output /user/julianjunge/terasort
19/02/14 21:38:21 INFO terasort.TeraSort: starting
19/02/14 21:38:22 INFO hdfs.DFSClient: Created token for julianjunge: HDFS_DELEGATION_TOKEN owner=julianjunge@EXAMPLE.COM, renewer=yarn, realUser=, issueDate=1550180302573, maxDate=1550785102573, sequenceNumber=11, masterKeyId=12 on ha-hdfs:nameservice-ha
19/02/14 21:38:22 INFO security.TokenCache: Got dt for hdfs://nameservice-ha; Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice-ha, Ident: (token for julianjunge: HDFS_DELEGATION_TOKEN owner=julianjunge@EXAMPLE.COM, renewer=yarn, realUser=, issueDate=1550180302573, maxDate=1550785102573, sequenceNumber=11, masterKeyId=12)
19/02/14 21:38:22 INFO input.FileInputFormat: Total input paths to process : 4
Spent 269ms computing base-splits.
Spent 1ms computing TeraScheduler splits.
Computing input splits took 270ms
Sampling 4 splits of 4
Making 8 from 1000 sampled records
Computing parititions took 176ms
Spent 448ms computing partitions.
19/02/14 21:38:22 INFO client.RMProxy: Connecting to ResourceManager at ip-10-0-0-128.ec2.internal/10.0.0.128:8032
19/02/14 21:38:23 INFO mapreduce.JobSubmitter: number of splits:4
19/02/14 21:38:23 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1550163516356_0008
19/02/14 21:38:23 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:nameservice-ha, Ident: (token for julianjunge: HDFS_DELEGATION_TOKEN owner=julianjunge@EXAMPLE.COM, renewer=yarn, realUser=, issueDate=1550180302573, maxDate=1550785102573, sequenceNumber=11, masterKeyId=12)
19/02/14 21:38:23 INFO impl.YarnClientImpl: Submitted application application_1550163516356_0008
19/02/14 21:38:23 INFO mapreduce.Job: The url to track the job: http://ip-10-0-0-128.ec2.internal:8088/proxy/application_1550163516356_0008/
19/02/14 21:38:23 INFO mapreduce.Job: Running job: job_1550163516356_0008
19/02/14 21:38:30 INFO mapreduce.Job: Job job_1550163516356_0008 running in uber mode : false
19/02/14 21:38:30 INFO mapreduce.Job:  map 0% reduce 0%
19/02/14 21:38:42 INFO mapreduce.Job:  map 100% reduce 0%
19/02/14 21:38:51 INFO mapreduce.Job:  map 100% reduce 38%
19/02/14 21:38:52 INFO mapreduce.Job:  map 100% reduce 50%
19/02/14 21:38:58 INFO mapreduce.Job:  map 100% reduce 75%
19/02/14 21:38:59 INFO mapreduce.Job:  map 100% reduce 100%
19/02/14 21:38:59 INFO mapreduce.Job: Job job_1550163516356_0008 completed successfully
19/02/14 21:38:59 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=43590
                FILE: Number of bytes written=1933118
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=100524
                HDFS: Number of bytes written=100000
                HDFS: Number of read operations=36
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=4
                Launched reduce tasks=8
                Rack-local map tasks=4
                Total time spent by all maps in occupied slots (ms)=39725
                Total time spent by all reduces in occupied slots (ms)=48425
                Total time spent by all map tasks (ms)=39725
                Total time spent by all reduce tasks (ms)=48425
                Total vcore-milliseconds taken by all map tasks=39725
                Total vcore-milliseconds taken by all reduce tasks=48425
                Total megabyte-milliseconds taken by all map tasks=40678400
                Total megabyte-milliseconds taken by all reduce tasks=49587200
        Map-Reduce Framework
                Map input records=1000
                Map output records=1000
                Map output bytes=102000
                Map output materialized bytes=45096
                Input split bytes=524
                Combine input records=0
                Combine output records=0
                Reduce input groups=1000
                Reduce shuffle bytes=45096
                Reduce input records=1000
                Reduce output records=1000
                Spilled Records=2000
                Shuffled Maps =32
                Failed Shuffles=0
                Merged Map outputs=32
                GC time elapsed (ms)=1195
                CPU time spent (ms)=11280
                Physical memory (bytes) snapshot=4022321152
                Virtual memory (bytes) snapshot=19180683264
                Total committed heap usage (bytes)=4743757824
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=100000
        File Output Format Counters
                Bytes Written=100000
19/02/14 21:38:59 INFO terasort.TeraSort: done

real    0m39.176s
user    0m5.185s
sys     0m0.249s
