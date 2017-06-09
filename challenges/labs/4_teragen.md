# HDFS Testing
## Create TeraGen File (As theresa)
```
sudo -u theresa time /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Ddfs.blocksize=33554432 -Dmapreduce.job.maps=6 51200000 /user/theresa/tgen512m
```

## Time output
```
real	1m28.108s
user	0m6.059s
sym 	0m0.661s
```

## HDFS Output
`[root@node201 ~]# sudo -u theresa hdfs dfs -ls /user/theresa/tgen512m`
```
Found 7 items
-rw-r--r--   3 theresa theresa          0 2017-06-09 10:18 /user/theresa/tgen512m/_SUCCESS
-rw-r--r--   3 theresa theresa  853333400 2017-06-09 10:17 /user/theresa/tgen512m/part-m-00000
-rw-r--r--   3 theresa theresa  853333300 2017-06-09 10:18 /user/theresa/tgen512m/part-m-00001
-rw-r--r--   3 theresa theresa  853333300 2017-06-09 10:18 /user/theresa/tgen512m/part-m-00002
-rw-r--r--   3 theresa theresa  853333400 2017-06-09 10:18 /user/theresa/tgen512m/part-m-00003
-rw-r--r--   3 theresa theresa  853333300 2017-06-09 10:18 /user/theresa/tgen512m/part-m-00004
-rw-r--r--   3 theresa theresa  853333300 2017-06-09 10:18 /user/theresa/tgen512m/part-m-00005
```

## Block List
`hdfs fsck /user/theresa/tgen512m -blocks`
```
Connecting to namenode via http://node201.sebc:50070
FSCK started by root (auth:SIMPLE) from /10.1.1.201 for path /user/theresa/tgen512m at Fri Jun 09 10:23:12 UTC 2017
.......Status: HEALTHY
 Total size:	5120000000 B
 Total dirs:	1
 Total files:	7
 Total symlinks:		0
 Total blocks (validated):	156 (avg. block size 32820512 B)
 Minimally replicated blocks:	156 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Jun 09 10:23:12 UTC 2017 in 9 milliseconds


The filesystem under path '/user/theresa/tgen512m' is HEALTHY
```