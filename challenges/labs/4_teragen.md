## <center> Challenge 4 - HDFS Testing

* Create the Issue `Test HDFS`
* Assign yourself and label it `started`
* As user `saturn`, use `teragen` to generate a 65,536,000-record dataset
  * Write the output to 12 files 
  * Set the block size to 32 MB
  * Set the mapper container size to 512 MiB
  * Name the target directory `tgen`
  * Use the `time` command to capture job duration
* Put the following in `challenges/labs/4_teragen.md`
  * The full `teragen` command and output 
```
[centos@ip-172-31-6-18 ~]$ sudo -u saturn time yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Ddfs.blocksize=32m -Dmapred.map.tasks=12 -Dmapreduce.map.memory.mb=512 65536000 tgen
18/03/04 15:28:46 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-6-18.eu-west-1.compute.internal/172.31.6.18:8032
18/03/04 15:28:47 INFO terasort.TeraSort: Generating 65536000 using 12
18/03/04 15:28:47 INFO mapreduce.JobSubmitter: number of splits:12
18/03/04 15:28:47 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
18/03/04 15:28:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1520175164100_0002
18/03/04 15:28:47 INFO impl.YarnClientImpl: Submitted application application_1520175164100_0002
18/03/04 15:28:47 INFO mapreduce.Job: The url to track the job: http://ip-172-31-6-18.eu-west-1.compute.internal:8088/proxy/application_1520175164100_0002/
18/03/04 15:28:47 INFO mapreduce.Job: Running job: job_1520175164100_0002
18/03/04 15:28:54 INFO mapreduce.Job: Job job_1520175164100_0002 running in uber mode : false
18/03/04 15:28:54 INFO mapreduce.Job:  map 0% reduce 0%
18/03/04 15:29:06 INFO mapreduce.Job:  map 3% reduce 0%
18/03/04 15:29:07 INFO mapreduce.Job:  map 6% reduce 0%
18/03/04 15:29:08 INFO mapreduce.Job:  map 10% reduce 0%
18/03/04 15:29:09 INFO mapreduce.Job:  map 19% reduce 0%
18/03/04 15:29:10 INFO mapreduce.Job:  map 22% reduce 0%
18/03/04 15:29:11 INFO mapreduce.Job:  map 23% reduce 0%
18/03/04 15:29:12 INFO mapreduce.Job:  map 27% reduce 0%
18/03/04 15:29:13 INFO mapreduce.Job:  map 28% reduce 0%
18/03/04 15:29:14 INFO mapreduce.Job:  map 30% reduce 0%
18/03/04 15:29:15 INFO mapreduce.Job:  map 32% reduce 0%
18/03/04 15:29:16 INFO mapreduce.Job:  map 34% reduce 0%
18/03/04 15:29:17 INFO mapreduce.Job:  map 35% reduce 0%
18/03/04 15:29:18 INFO mapreduce.Job:  map 38% reduce 0%
18/03/04 15:29:19 INFO mapreduce.Job:  map 41% reduce 0%
18/03/04 15:29:20 INFO mapreduce.Job:  map 42% reduce 0%
18/03/04 15:29:21 INFO mapreduce.Job:  map 44% reduce 0%
18/03/04 15:29:22 INFO mapreduce.Job:  map 47% reduce 0%
18/03/04 15:29:23 INFO mapreduce.Job:  map 48% reduce 0%
18/03/04 15:29:24 INFO mapreduce.Job:  map 51% reduce 0%
18/03/04 15:29:25 INFO mapreduce.Job:  map 53% reduce 0%
18/03/04 15:29:26 INFO mapreduce.Job:  map 55% reduce 0%
18/03/04 15:29:27 INFO mapreduce.Job:  map 58% reduce 0%
18/03/04 15:29:28 INFO mapreduce.Job:  map 60% reduce 0%
18/03/04 15:29:29 INFO mapreduce.Job:  map 62% reduce 0%
18/03/04 15:29:30 INFO mapreduce.Job:  map 64% reduce 0%
18/03/04 15:29:31 INFO mapreduce.Job:  map 65% reduce 0%
18/03/04 15:29:32 INFO mapreduce.Job:  map 67% reduce 0%
18/03/04 15:29:33 INFO mapreduce.Job:  map 68% reduce 0%
18/03/04 15:29:35 INFO mapreduce.Job:  map 71% reduce 0%
18/03/04 15:29:37 INFO mapreduce.Job:  map 72% reduce 0%
18/03/04 15:29:38 INFO mapreduce.Job:  map 76% reduce 0%
18/03/04 15:29:40 INFO mapreduce.Job:  map 77% reduce 0%
18/03/04 15:29:41 INFO mapreduce.Job:  map 81% reduce 0%
18/03/04 15:29:43 INFO mapreduce.Job:  map 82% reduce 0%
18/03/04 15:29:45 INFO mapreduce.Job:  map 86% reduce 0%
18/03/04 15:29:47 INFO mapreduce.Job:  map 88% reduce 0%
18/03/04 15:29:48 INFO mapreduce.Job:  map 90% reduce 0%
18/03/04 15:29:49 INFO mapreduce.Job:  map 91% reduce 0%
18/03/04 15:29:50 INFO mapreduce.Job:  map 92% reduce 0%
18/03/04 15:29:51 INFO mapreduce.Job:  map 96% reduce 0%
18/03/04 15:29:54 INFO mapreduce.Job:  map 100% reduce 0%
18/03/04 15:29:55 INFO mapreduce.Job: Job job_1520175164100_0002 completed successfully
18/03/04 15:29:55 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1482362
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=551296
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=551296
                Total vcore-seconds taken by all map tasks=551296
                Total megabyte-seconds taken by all map tasks=564527104
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2750
                CPU time spent (ms)=145110
                Physical memory (bytes) snapshot=2447937536
                Virtual memory (bytes) snapshot=13417213952
                Total committed heap usage (bytes)=3158310912
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000

```
  * The result of the `time` command
```
6.41user 0.30system 1:11.73elapsed 9%CPU (0avgtext+0avgdata 210580maxresident)k
0inputs+1936outputs (0major+77674minor)pagefaults 0swaps

```
  * The command and output of `hdfs dfs -ls /user/saturn/tgen`
```
[centos@ip-172-31-6-18 ~]$ sudo -u saturn hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn saturn          0 2018-03-04 15:29 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn saturn  546133400 2018-03-04 15:29 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn saturn  546133400 2018-03-04 15:29 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn saturn  546133400 2018-03-04 15:29 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn saturn  546133400 2018-03-04 15:29 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn saturn  546133300 2018-03-04 15:29 /user/saturn/tgen/part-m-00011

```
  * The command and output of `hadoop fsck -blocks /user/saturn`
```
[centos@ip-172-31-6-18 ~]$ sudo -u saturn hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-6-18.eu-west-1.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.6.18 for path /user/saturn at Sun Mar 04 15:31:26 UTC 2018
.............Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    7
 Total files:   13
 Total symlinks:                0
 Total blocks (validated):      204 (avg. block size 32125490 B)
 Minimally replicated blocks:   204 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Sun Mar 04 15:31:26 UTC 2018 in 10 milliseconds


The filesystem under path '/user/saturn' is HEALTHY

```

* Push this work to GitHub and label the Issue `review`
* Assign the issue to the instructors
