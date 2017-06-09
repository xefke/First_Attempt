```
[theresa@node201 root]$ time /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=6 -Dmapreduce.job.reduces=6 /user/theresa/tgen512m /user/theresa/tsort512m
```
```
17/06/09 11:20:48 INFO terasort.TeraSort: starting
17/06/09 11:20:50 INFO hdfs.DFSClient: Created token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@XEFKE.CO.UK, renewer=yarn, realUser=, issueDate=1497007250233, maxDate=1497612050233, sequenceNumber=1, masterKeyId=2 on 10.1.1.201:8020
17/06/09 11:20:50 INFO security.TokenCache: Got dt for hdfs://node201.sebc:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.1.201:8020, Ident: (token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@XEFKE.CO.UK, renewer=yarn, realUser=, issueDate=1497007250233, maxDate=1497612050233, sequenceNumber=1, masterKeyId=2)
17/06/09 11:20:50 INFO input.FileInputFormat: Total input paths to process : 6
Spent 492ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 497ms
Sampling 10 splits of 156
Making 6 from 100000 sampled records
Computing parititions took 883ms
Spent 1384ms computing partitions.
17/06/09 11:20:51 INFO client.RMProxy: Connecting to ResourceManager at node201.sebc/10.1.1.201:8032
17/06/09 11:20:51 INFO mapreduce.JobSubmitter: number of splits:156
17/06/09 11:20:52 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1497006713536_0001
17/06/09 11:20:52 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.1.1.201:8020, Ident: (token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@XEFKE.CO.UK, renewer=yarn, realUser=, issueDate=1497007250233, maxDate=1497612050233, sequenceNumber=1, masterKeyId=2)
17/06/09 11:20:53 INFO impl.YarnClientImpl: Submitted application application_1497006713536_0001
17/06/09 11:20:53 INFO mapreduce.Job: The url to track the job: http://node201.sebc:8088/proxy/application_1497006713536_0001/
17/06/09 11:20:53 INFO mapreduce.Job: Running job: job_1497006713536_0001
17/06/09 11:21:03 INFO mapreduce.Job: Job job_1497006713536_0001 running in uber mode : false
17/06/09 11:21:03 INFO mapreduce.Job:  map 0% reduce 0%
17/06/09 11:21:15 INFO mapreduce.Job:  map 1% reduce 0%
17/06/09 11:21:16 INFO mapreduce.Job:  map 2% reduce 0%
17/06/09 11:21:18 INFO mapreduce.Job:  map 3% reduce 0%
17/06/09 11:21:21 INFO mapreduce.Job:  map 5% reduce 0%
17/06/09 11:21:25 INFO mapreduce.Job:  map 6% reduce 0%
17/06/09 11:21:26 INFO mapreduce.Job:  map 10% reduce 0%
17/06/09 11:21:27 INFO mapreduce.Job:  map 11% reduce 0%
17/06/09 11:21:32 INFO mapreduce.Job:  map 13% reduce 0%
17/06/09 11:21:35 INFO mapreduce.Job:  map 14% reduce 0%
17/06/09 11:21:38 INFO mapreduce.Job:  map 15% reduce 0%
17/06/09 11:21:39 INFO mapreduce.Job:  map 17% reduce 0%
17/06/09 11:21:40 INFO mapreduce.Job:  map 18% reduce 0%
17/06/09 11:21:41 INFO mapreduce.Job:  map 19% reduce 0%
17/06/09 11:21:44 INFO mapreduce.Job:  map 22% reduce 0%
17/06/09 11:21:49 INFO mapreduce.Job:  map 23% reduce 0%
17/06/09 11:21:50 INFO mapreduce.Job:  map 24% reduce 0%
17/06/09 11:21:52 INFO mapreduce.Job:  map 26% reduce 0%
17/06/09 11:21:53 INFO mapreduce.Job:  map 27% reduce 0%
17/06/09 11:21:54 INFO mapreduce.Job:  map 28% reduce 0%
17/06/09 11:21:55 INFO mapreduce.Job:  map 29% reduce 0%
17/06/09 11:21:59 INFO mapreduce.Job:  map 30% reduce 0%
17/06/09 11:22:00 INFO mapreduce.Job:  map 32% reduce 0%
17/06/09 11:22:01 INFO mapreduce.Job:  map 33% reduce 0%
17/06/09 11:22:04 INFO mapreduce.Job:  map 34% reduce 0%
17/06/09 11:22:05 INFO mapreduce.Job:  map 35% reduce 0%
17/06/09 11:22:06 INFO mapreduce.Job:  map 37% reduce 0%
17/06/09 11:22:08 INFO mapreduce.Job:  map 38% reduce 0%
17/06/09 11:22:10 INFO mapreduce.Job:  map 40% reduce 0%
17/06/09 11:22:13 INFO mapreduce.Job:  map 41% reduce 0%
17/06/09 11:22:16 INFO mapreduce.Job:  map 43% reduce 0%
17/06/09 11:22:17 INFO mapreduce.Job:  map 44% reduce 0%
17/06/09 11:22:19 INFO mapreduce.Job:  map 45% reduce 0%
17/06/09 11:22:20 INFO mapreduce.Job:  map 46% reduce 0%
17/06/09 11:22:21 INFO mapreduce.Job:  map 47% reduce 0%
17/06/09 11:22:22 INFO mapreduce.Job:  map 48% reduce 0%
17/06/09 11:22:23 INFO mapreduce.Job:  map 49% reduce 0%
17/06/09 11:22:25 INFO mapreduce.Job:  map 50% reduce 0%
17/06/09 11:22:26 INFO mapreduce.Job:  map 51% reduce 0%
17/06/09 11:22:29 INFO mapreduce.Job:  map 52% reduce 0%
17/06/09 11:22:31 INFO mapreduce.Job:  map 53% reduce 0%
17/06/09 11:22:32 INFO mapreduce.Job:  map 54% reduce 0%
17/06/09 11:22:33 INFO mapreduce.Job:  map 56% reduce 0%
17/06/09 11:22:34 INFO mapreduce.Job:  map 58% reduce 0%
17/06/09 11:22:36 INFO mapreduce.Job:  map 59% reduce 0%
17/06/09 11:22:41 INFO mapreduce.Job:  map 62% reduce 0%
17/06/09 11:22:43 INFO mapreduce.Job:  map 63% reduce 0%
17/06/09 11:22:46 INFO mapreduce.Job:  map 65% reduce 0%
17/06/09 11:22:47 INFO mapreduce.Job:  map 67% reduce 0%
17/06/09 11:22:50 INFO mapreduce.Job:  map 68% reduce 0%
17/06/09 11:22:52 INFO mapreduce.Job:  map 69% reduce 0%
17/06/09 11:22:53 INFO mapreduce.Job:  map 71% reduce 0%
17/06/09 11:22:56 INFO mapreduce.Job:  map 72% reduce 0%
17/06/09 11:22:57 INFO mapreduce.Job:  map 73% reduce 0%
17/06/09 11:22:58 INFO mapreduce.Job:  map 74% reduce 0%
17/06/09 11:23:00 INFO mapreduce.Job:  map 76% reduce 0%
17/06/09 11:23:04 INFO mapreduce.Job:  map 78% reduce 0%
17/06/09 11:23:05 INFO mapreduce.Job:  map 80% reduce 0%
17/06/09 11:23:06 INFO mapreduce.Job:  map 81% reduce 0%
17/06/09 11:23:13 INFO mapreduce.Job:  map 83% reduce 0%
17/06/09 11:23:14 INFO mapreduce.Job:  map 86% reduce 0%
17/06/09 11:23:16 INFO mapreduce.Job:  map 88% reduce 0%
17/06/09 11:23:18 INFO mapreduce.Job:  map 89% reduce 0%
17/06/09 11:23:24 INFO mapreduce.Job:  map 90% reduce 0%
17/06/09 11:23:27 INFO mapreduce.Job:  map 92% reduce 0%
17/06/09 11:23:30 INFO mapreduce.Job:  map 92% reduce 5%
17/06/09 11:23:32 INFO mapreduce.Job:  map 93% reduce 15%
17/06/09 11:23:34 INFO mapreduce.Job:  map 94% reduce 21%
17/06/09 11:23:35 INFO mapreduce.Job:  map 94% reduce 26%
17/06/09 11:23:36 INFO mapreduce.Job:  map 94% reduce 31%
17/06/09 11:23:38 INFO mapreduce.Job:  map 96% reduce 31%
17/06/09 11:23:41 INFO mapreduce.Job:  map 97% reduce 32%
17/06/09 11:23:44 INFO mapreduce.Job:  map 98% reduce 32%
17/06/09 11:23:45 INFO mapreduce.Job:  map 99% reduce 32%
17/06/09 11:23:47 INFO mapreduce.Job:  map 100% reduce 33%
17/06/09 11:23:48 INFO mapreduce.Job:  map 100% reduce 35%
17/06/09 11:23:50 INFO mapreduce.Job:  map 100% reduce 47%
17/06/09 11:23:52 INFO mapreduce.Job:  map 100% reduce 53%
17/06/09 11:23:53 INFO mapreduce.Job:  map 100% reduce 60%
17/06/09 11:23:54 INFO mapreduce.Job:  map 100% reduce 71%
17/06/09 11:23:56 INFO mapreduce.Job:  map 100% reduce 75%
17/06/09 11:23:58 INFO mapreduce.Job:  map 100% reduce 77%
17/06/09 11:23:59 INFO mapreduce.Job:  map 100% reduce 79%
17/06/09 11:24:00 INFO mapreduce.Job:  map 100% reduce 84%
17/06/09 11:24:02 INFO mapreduce.Job:  map 100% reduce 88%
17/06/09 11:24:04 INFO mapreduce.Job:  map 100% reduce 90%
17/06/09 11:24:05 INFO mapreduce.Job:  map 100% reduce 96%
17/06/09 11:24:06 INFO mapreduce.Job:  map 100% reduce 97%
17/06/09 11:24:07 INFO mapreduce.Job:  map 100% reduce 99%
17/06/09 11:24:08 INFO mapreduce.Job:  map 100% reduce 100%
17/06/09 11:24:08 INFO mapreduce.Job: Job job_1497006713536_0001 completed successfully
17/06/09 11:24:09 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=2285841684
		FILE: Number of bytes written=4546435103
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=5120019344
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=486
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters
		Launched map tasks=156
		Launched reduce tasks=6
		Data-local map tasks=155
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=1567355
		Total time spent by all reduces in occupied slots (ms)=304948
		Total time spent by all map tasks (ms)=1567355
		Total time spent by all reduce tasks (ms)=304948
		Total vcore-seconds taken by all map tasks=1567355
		Total vcore-seconds taken by all reduce tasks=304948
		Total megabyte-seconds taken by all map tasks=1604971520
		Total megabyte-seconds taken by all reduce tasks=312266752
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Map output bytes=5222400000
		Map output materialized bytes=2240080039
		Input split bytes=19344
		Combine input records=0
		Combine output records=0
		Reduce input groups=51200000
		Reduce shuffle bytes=2240080039
		Reduce input records=51200000
		Reduce output records=51200000
		Spilled Records=102400000
		Shuffled Maps =936
		Failed Shuffles=0
		Merged Map outputs=936
		GC time elapsed (ms)=21650
		CPU time spent (ms)=798360
		Physical memory (bytes) snapshot=80108199936
		Virtual memory (bytes) snapshot=253242884096
		Total committed heap usage (bytes)=91932852224
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters
		Bytes Read=5120000000
	File Output Format Counters
		Bytes Written=5120000000
17/06/09 11:24:09 INFO terasort.TeraSort: done

real	3m22.175s
user	0m8.693s
sys	0m0.899s
```