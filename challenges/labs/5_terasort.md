## <center> Challenge 5 - Kerberize the cluster

* Create the Issue `Kerberize cluster`
* Assign the issue to yourself and label it `started`
* Install an MIT KDC on the second node in your cluster
  * Name your realm after your GitHub handle
  * Use `HQ` as a suffix
  * For example: `RSTOKES.HQ`
* Create Kerberos principals for `saturn`, `haley`, and `cloudera-scm`
  * Grant `cloudera-scm` the privileges needed to create principals and generate keytabs
* Kerberize the cluster
* Run the `terasort` program as user `saturn` with the output target `/user/saturn/tsort`
  * Generate 10,000,000 records
  * Copy the command and full output to `challenges/labs/5_terasort.md`
```
[centos@ip-172-31-6-18 ~]$ yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort tgen tsort 10000000
18/03/04 16:15:08 INFO terasort.TeraSort: starting
18/03/04 16:15:10 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LDA.HQ, renewer=yarn, realUser=, issueDate=1520180110413, maxDate=1520784910413, sequenceNumber=1, masterKeyId=2 on 172.31.6.18:8020
18/03/04 16:15:10 INFO security.TokenCache: Got dt for hdfs://ip-172-31-6-18.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.6.18:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LDA.HQ, renewer=yarn, realUser=, issueDate=1520180110413, maxDate=1520784910413, sequenceNumber=1, masterKeyId=2)
18/03/04 16:15:10 INFO input.FileInputFormat: Total input paths to process : 12
Spent 502ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 509ms
Sampling 10 splits of 204
Making 6 from 100000 sampled records
Computing parititions took 1719ms
Spent 2232ms computing partitions.
18/03/04 16:15:12 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-6-18.eu-west-1.compute.internal/172.31.6.18:8032
18/03/04 16:15:12 INFO mapreduce.JobSubmitter: number of splits:204
18/03/04 16:15:13 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1520179710955_0001
18/03/04 16:15:13 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.6.18:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@LDA.HQ, renewer=yarn, realUser=, issueDate=1520180110413, maxDate=1520784910413, sequenceNumber=1, masterKeyId=2)
18/03/04 16:15:14 INFO impl.YarnClientImpl: Submitted application application_1520179710955_0001
18/03/04 16:15:14 INFO mapreduce.Job: The url to track the job: http://ip-172-31-6-18.eu-west-1.compute.internal:8088/proxy/application_1520179710955_0001/
18/03/04 16:15:14 INFO mapreduce.Job: Running job: job_1520179710955_0001
18/03/04 16:15:23 INFO mapreduce.Job: Job job_1520179710955_0001 running in uber mode : false
18/03/04 16:15:23 INFO mapreduce.Job:  map 0% reduce 0%
18/03/04 16:15:33 INFO mapreduce.Job:  map 1% reduce 0%
18/03/04 16:15:41 INFO mapreduce.Job:  map 2% reduce 0%
18/03/04 16:15:42 INFO mapreduce.Job:  map 6% reduce 0%
18/03/04 16:15:43 INFO mapreduce.Job:  map 7% reduce 0%
18/03/04 16:15:51 INFO mapreduce.Job:  map 8% reduce 0%
18/03/04 16:15:52 INFO mapreduce.Job:  map 9% reduce 0%
18/03/04 16:15:53 INFO mapreduce.Job:  map 10% reduce 0%
18/03/04 16:15:54 INFO mapreduce.Job:  map 12% reduce 0%
18/03/04 16:15:59 INFO mapreduce.Job:  map 13% reduce 0%
18/03/04 16:16:00 INFO mapreduce.Job:  map 14% reduce 0%
18/03/04 16:16:04 INFO mapreduce.Job:  map 15% reduce 0%
18/03/04 16:16:05 INFO mapreduce.Job:  map 17% reduce 0%
18/03/04 16:16:07 INFO mapreduce.Job:  map 18% reduce 0%
18/03/04 16:16:10 INFO mapreduce.Job:  map 19% reduce 0%
18/03/04 16:16:15 INFO mapreduce.Job:  map 20% reduce 0%
18/03/04 16:16:17 INFO mapreduce.Job:  map 21% reduce 0%
18/03/04 16:16:18 INFO mapreduce.Job:  map 24% reduce 0%
18/03/04 16:16:19 INFO mapreduce.Job:  map 25% reduce 0%
18/03/04 16:16:28 INFO mapreduce.Job:  map 28% reduce 0%
18/03/04 16:16:29 INFO mapreduce.Job:  map 29% reduce 0%
18/03/04 16:16:30 INFO mapreduce.Job:  map 30% reduce 0%
18/03/04 16:16:37 INFO mapreduce.Job:  map 31% reduce 0%
18/03/04 16:16:38 INFO mapreduce.Job:  map 32% reduce 0%
18/03/04 16:16:39 INFO mapreduce.Job:  map 33% reduce 0%
18/03/04 16:16:40 INFO mapreduce.Job:  map 35% reduce 0%
18/03/04 16:16:44 INFO mapreduce.Job:  map 36% reduce 0%
18/03/04 16:16:47 INFO mapreduce.Job:  map 37% reduce 0%
18/03/04 16:16:49 INFO mapreduce.Job:  map 38% reduce 0%
18/03/04 16:16:50 INFO mapreduce.Job:  map 39% reduce 0%
18/03/04 16:16:51 INFO mapreduce.Job:  map 40% reduce 0%
18/03/04 16:16:52 INFO mapreduce.Job:  map 41% reduce 0%
18/03/04 16:16:54 INFO mapreduce.Job:  map 42% reduce 0%
18/03/04 16:17:00 INFO mapreduce.Job:  map 43% reduce 0%
18/03/04 16:17:01 INFO mapreduce.Job:  map 44% reduce 0%
18/03/04 16:17:02 INFO mapreduce.Job:  map 46% reduce 0%
18/03/04 16:17:03 INFO mapreduce.Job:  map 48% reduce 0%
18/03/04 16:17:10 INFO mapreduce.Job:  map 49% reduce 0%
18/03/04 16:17:12 INFO mapreduce.Job:  map 50% reduce 0%
18/03/04 16:17:13 INFO mapreduce.Job:  map 51% reduce 0%
18/03/04 16:17:14 INFO mapreduce.Job:  map 53% reduce 0%
18/03/04 16:17:20 INFO mapreduce.Job:  map 54% reduce 0%
18/03/04 16:17:21 INFO mapreduce.Job:  map 55% reduce 0%
18/03/04 16:17:23 INFO mapreduce.Job:  map 56% reduce 0%
18/03/04 16:17:25 INFO mapreduce.Job:  map 58% reduce 0%
18/03/04 16:17:28 INFO mapreduce.Job:  map 59% reduce 0%
18/03/04 16:17:29 INFO mapreduce.Job:  map 60% reduce 0%
18/03/04 16:17:33 INFO mapreduce.Job:  map 61% reduce 0%
18/03/04 16:17:35 INFO mapreduce.Job:  map 62% reduce 0%
18/03/04 16:17:36 INFO mapreduce.Job:  map 64% reduce 0%
18/03/04 16:17:37 INFO mapreduce.Job:  map 65% reduce 0%
18/03/04 16:17:43 INFO mapreduce.Job:  map 66% reduce 0%
18/03/04 16:17:44 INFO mapreduce.Job:  map 67% reduce 0%
18/03/04 16:17:46 INFO mapreduce.Job:  map 68% reduce 0%
18/03/04 16:17:47 INFO mapreduce.Job:  map 71% reduce 0%
18/03/04 16:17:53 INFO mapreduce.Job:  map 72% reduce 0%
18/03/04 16:17:56 INFO mapreduce.Job:  map 73% reduce 0%
18/03/04 16:17:57 INFO mapreduce.Job:  map 75% reduce 0%
18/03/04 16:17:59 INFO mapreduce.Job:  map 76% reduce 0%
18/03/04 16:18:02 INFO mapreduce.Job:  map 77% reduce 0%
18/03/04 16:18:05 INFO mapreduce.Job:  map 78% reduce 0%
18/03/04 16:18:08 INFO mapreduce.Job:  map 80% reduce 0%
18/03/04 16:18:09 INFO mapreduce.Job:  map 81% reduce 0%
18/03/04 16:18:10 INFO mapreduce.Job:  map 82% reduce 0%
18/03/04 16:18:14 INFO mapreduce.Job:  map 83% reduce 0%
18/03/04 16:18:17 INFO mapreduce.Job:  map 84% reduce 0%
18/03/04 16:18:19 INFO mapreduce.Job:  map 86% reduce 0%
18/03/04 16:18:20 INFO mapreduce.Job:  map 87% reduce 0%
18/03/04 16:18:25 INFO mapreduce.Job:  map 87% reduce 5%
18/03/04 16:18:27 INFO mapreduce.Job:  map 87% reduce 8%
18/03/04 16:18:29 INFO mapreduce.Job:  map 87% reduce 9%
18/03/04 16:18:30 INFO mapreduce.Job:  map 87% reduce 12%
18/03/04 16:18:31 INFO mapreduce.Job:  map 87% reduce 13%
18/03/04 16:18:32 INFO mapreduce.Job:  map 89% reduce 17%
18/03/04 16:18:33 INFO mapreduce.Job:  map 90% reduce 18%
18/03/04 16:18:34 INFO mapreduce.Job:  map 90% reduce 19%
18/03/04 16:18:35 INFO mapreduce.Job:  map 90% reduce 23%
18/03/04 16:18:37 INFO mapreduce.Job:  map 90% reduce 24%
18/03/04 16:18:38 INFO mapreduce.Job:  map 90% reduce 25%
18/03/04 16:18:42 INFO mapreduce.Job:  map 91% reduce 25%
18/03/04 16:18:43 INFO mapreduce.Job:  map 92% reduce 25%
18/03/04 16:18:44 INFO mapreduce.Job:  map 93% reduce 25%
18/03/04 16:18:45 INFO mapreduce.Job:  map 93% reduce 26%
18/03/04 16:18:50 INFO mapreduce.Job:  map 94% reduce 26%
18/03/04 16:18:51 INFO mapreduce.Job:  map 95% reduce 26%
18/03/04 16:18:52 INFO mapreduce.Job:  map 96% reduce 26%
18/03/04 16:18:53 INFO mapreduce.Job:  map 96% reduce 27%
18/03/04 16:18:59 INFO mapreduce.Job:  map 98% reduce 27%
18/03/04 16:19:00 INFO mapreduce.Job:  map 99% reduce 27%
18/03/04 16:19:03 INFO mapreduce.Job:  map 99% reduce 28%
18/03/04 16:19:04 INFO mapreduce.Job:  map 100% reduce 28%
18/03/04 16:19:05 INFO mapreduce.Job:  map 100% reduce 38%
18/03/04 16:19:07 INFO mapreduce.Job:  map 100% reduce 49%
18/03/04 16:19:08 INFO mapreduce.Job:  map 100% reduce 57%
18/03/04 16:19:10 INFO mapreduce.Job:  map 100% reduce 59%
18/03/04 16:19:11 INFO mapreduce.Job:  map 100% reduce 66%
18/03/04 16:19:13 INFO mapreduce.Job:  map 100% reduce 68%
18/03/04 16:19:14 INFO mapreduce.Job:  map 100% reduce 72%
18/03/04 16:19:17 INFO mapreduce.Job:  map 100% reduce 78%
18/03/04 16:19:19 INFO mapreduce.Job:  map 100% reduce 79%
18/03/04 16:19:20 INFO mapreduce.Job:  map 100% reduce 88%
18/03/04 16:19:22 INFO mapreduce.Job:  map 100% reduce 89%
18/03/04 16:19:23 INFO mapreduce.Job:  map 100% reduce 92%
18/03/04 16:19:25 INFO mapreduce.Job:  map 100% reduce 94%
18/03/04 16:19:26 INFO mapreduce.Job:  map 100% reduce 97%
18/03/04 16:19:28 INFO mapreduce.Job:  map 100% reduce 98%
18/03/04 16:19:29 INFO mapreduce.Job:  map 100% reduce 99%
18/03/04 16:19:31 INFO mapreduce.Job:  map 100% reduce 100%
18/03/04 16:19:32 INFO mapreduce.Job: Job job_1520179710955_0001 completed successfully
18/03/04 16:19:32 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2930146562
                FILE: Number of bytes written=5823915302
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=6553630192
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=630
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=204
                Launched reduce tasks=6
                Data-local map tasks=204
                Total time spent by all maps in occupied slots (ms)=1928007
                Total time spent by all reduces in occupied slots (ms)=363127
                Total time spent by all map tasks (ms)=1928007
                Total time spent by all reduce tasks (ms)=363127
                Total vcore-seconds taken by all map tasks=1928007
                Total vcore-seconds taken by all reduce tasks=363127
                Total megabyte-seconds taken by all map tasks=1974279168
                Total megabyte-seconds taken by all reduce tasks=371842048
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Map output bytes=6684672000
                Map output materialized bytes=2867367122
                Input split bytes=30192
                Combine input records=0
                Combine output records=0
                Reduce input groups=65536000
                Reduce shuffle bytes=2867367122
                Reduce input records=65536000
                Reduce output records=65536000
                Spilled Records=131072000
                Shuffled Maps =1224
                Failed Shuffles=0
                Merged Map outputs=1224
                GC time elapsed (ms)=23997
                CPU time spent (ms)=914840
                Physical memory (bytes) snapshot=102640918528
                Virtual memory (bytes) snapshot=328537853952
                Total committed heap usage (bytes)=123597750272
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
18/03/04 16:19:32 INFO terasort.TeraSort: done

```
* Run the Hadoop `pi` program as user `haley`
  * Copy the command and full output to `challenges/labs/5_pi.md`
```
[centos@ip-172-31-6-18 ~]$ kinit haley
Password for haley@LDA.HQ:
[centos@ip-172-31-6-18 ~]$ yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 12 1000
Number of Maps  = 12
Samples per Map = 1000
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
Starting Job
18/03/04 16:20:40 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-6-18.eu-west-1.compute.internal/172.31.6.18:8032
18/03/04 16:20:40 INFO hdfs.DFSClient: Created token for haley: HDFS_DELEGATION_TOKEN owner=haley@LDA.HQ, renewer=yarn, realUser=, issueDate=1520180440982, maxDate=1520785240982, sequenceNumber=2, masterKeyId=2 on 172.31.6.18:8020
18/03/04 16:20:41 INFO security.TokenCache: Got dt for hdfs://ip-172-31-6-18.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.6.18:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@LDA.HQ, renewer=yarn, realUser=, issueDate=1520180440982, maxDate=1520785240982, sequenceNumber=2, masterKeyId=2)
18/03/04 16:20:41 INFO input.FileInputFormat: Total input paths to process : 12
18/03/04 16:20:41 INFO mapreduce.JobSubmitter: number of splits:12
18/03/04 16:20:41 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1520179710955_0002
18/03/04 16:20:41 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.6.18:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@LDA.HQ, renewer=yarn, realUser=, issueDate=1520180440982, maxDate=1520785240982, sequenceNumber=2, masterKeyId=2)
18/03/04 16:20:41 INFO impl.YarnClientImpl: Submitted application application_1520179710955_0002
18/03/04 16:20:41 INFO mapreduce.Job: The url to track the job: http://ip-172-31-6-18.eu-west-1.compute.internal:8088/proxy/application_1520179710955_0002/
18/03/04 16:20:41 INFO mapreduce.Job: Running job: job_1520179710955_0002
18/03/04 16:20:49 INFO mapreduce.Job: Job job_1520179710955_0002 running in uber mode : false
18/03/04 16:20:49 INFO mapreduce.Job:  map 0% reduce 0%
18/03/04 16:20:57 INFO mapreduce.Job:  map 17% reduce 0%
18/03/04 16:20:58 INFO mapreduce.Job:  map 25% reduce 0%
18/03/04 16:21:01 INFO mapreduce.Job:  map 33% reduce 0%
18/03/04 16:21:04 INFO mapreduce.Job:  map 42% reduce 0%
18/03/04 16:21:05 INFO mapreduce.Job:  map 100% reduce 0%
18/03/04 16:21:10 INFO mapreduce.Job:  map 100% reduce 100%
18/03/04 16:21:10 INFO mapreduce.Job: Job job_1520179710955_0002 completed successfully
18/03/04 16:21:10 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=112
                FILE: Number of bytes written=1624700
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=3566
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=51
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=12
                Launched reduce tasks=1
                Data-local map tasks=12
                Total time spent by all maps in occupied slots (ms)=124345
                Total time spent by all reduces in occupied slots (ms)=3076
                Total time spent by all map tasks (ms)=124345
                Total time spent by all reduce tasks (ms)=3076
                Total vcore-seconds taken by all map tasks=124345
                Total vcore-seconds taken by all reduce tasks=3076
                Total megabyte-seconds taken by all map tasks=127329280
                Total megabyte-seconds taken by all reduce tasks=3149824
        Map-Reduce Framework
                Map input records=12
                Map output records=24
                Map output bytes=216
                Map output materialized bytes=408
                Input split bytes=2150
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=408
                Reduce input records=24
                Reduce output records=0
                Spilled Records=48
                Shuffled Maps =12
                Failed Shuffles=0
                Merged Map outputs=12
                GC time elapsed (ms)=626
                CPU time spent (ms)=8600
                Physical memory (bytes) snapshot=5653241856
                Virtual memory (bytes) snapshot=20377194496
                Total committed heap usage (bytes)=6692012032
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1416
        File Output Format Counters
                Bytes Written=97
Job Finished in 29.96 seconds
Estimated value of Pi is 3.14266666666666666667

```

*  Copy the configuration files in `/var/kerberos/krb5kdc/` to your repo:
    * Add the prefix `5_` and the suffix `.md` to the original file name
    * Example: `5_kdc.conf.md`
* Push this work to GitHub and label the Issue `review`
* Assign the issue to the instructors

