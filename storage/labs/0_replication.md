Create own dir:
```
hdfs dfs -mkdir xefke
```

Create external dir:
```
hdfs dfs -mkdir external
```

Create 500MB file:
```
/opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen 5120000 /user/root/xefke/500MB-File
```

Verify the file is generated:
```
hdfs dfs -ls /user/root/xefke
Found 1 items
drwxr-xr-x   - root root          0 2017-06-07 14:19 /user/root/xefke/500MB-File
```

Copy with distCp:
```
hadoop distcp hdfs://node01.sebc:8020/user/root/xefke/500MB-File hdfs://node01.sebc:8020/user/root/external
```

Verify the copy
```
hdfs dfs -ls /user/root/external
Found 1 items
drwxr-xr-x   - root root          0 2017-06-07 14:20 /user/root/external/500MB-File
```

Run FSCK on Source:
```
hdfs fsck /user/root/xefke/500MB-File -files -blocks

Connecting to namenode via http://node01.sebc:50070
FSCK started by root (auth:SIMPLE) from /10.1.1.101 for path /user/root/xefke/500MB-File at Wed Jun 07 14:25:47 UTC 2017
/user/root/xefke/500MB-File <dir>
/user/root/xefke/500MB-File/_SUCCESS 0 bytes, 0 block(s):  OK

/user/root/xefke/500MB-File/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-606695219-10.1.1.101-1496753884284:blk_1073746142_5327 len=134217728 Live_repl=3
1. BP-606695219-10.1.1.101-1496753884284:blk_1073746144_5329 len=121782272 Live_repl=3

/user/root/xefke/500MB-File/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-606695219-10.1.1.101-1496753884284:blk_1073746143_5328 len=134217728 Live_repl=3
1. BP-606695219-10.1.1.101-1496753884284:blk_1073746146_5331 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:  512000000 B
 Total dirs:  1
 Total files: 3
 Total symlinks:    0
 Total blocks (validated):  4 (avg. block size 128000000 B)
 Minimally replicated blocks: 4 (100.0 %)
 Over-replicated blocks:  0 (0.0 %)
 Under-replicated blocks: 0 (0.0 %)
 Mis-replicated blocks:   0 (0.0 %)
 Default replication factor:  3
 Average block replication: 3.0
 Corrupt blocks:    0
 Missing replicas:    0 (0.0 %)
 Number of data-nodes:    4
 Number of racks:   1
FSCK ended at Wed Jun 07 14:25:47 UTC 2017 in 2 milliseconds


The filesystem under path '/user/root/xefke/500MB-File' is HEALTHY
```

Run FSCK on Target:
```
hdfs fsck /user/root/external/500MB-File -files -blocks
Connecting to namenode via http://node01.sebc:50070
FSCK started by root (auth:SIMPLE) from /10.1.1.101 for path /user/root/external/500MB-File at Wed Jun 07 14:27:03 UTC 2017
/user/root/external/500MB-File <dir>
/user/root/external/500MB-File/_SUCCESS 0 bytes, 0 block(s):  OK

/user/root/external/500MB-File/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-606695219-10.1.1.101-1496753884284:blk_1073746164_5349 len=134217728 Live_repl=3
1. BP-606695219-10.1.1.101-1496753884284:blk_1073746168_5353 len=121782272 Live_repl=3

/user/root/external/500MB-File/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-606695219-10.1.1.101-1496753884284:blk_1073746165_5350 len=134217728 Live_repl=3
1. BP-606695219-10.1.1.101-1496753884284:blk_1073746167_5352 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:  512000000 B
 Total dirs:  1
 Total files: 3
 Total symlinks:    0
 Total blocks (validated):  4 (avg. block size 128000000 B)
 Minimally replicated blocks: 4 (100.0 %)
 Over-replicated blocks:  0 (0.0 %)
 Under-replicated blocks: 0 (0.0 %)
 Mis-replicated blocks:   0 (0.0 %)
 Default replication factor:  3
 Average block replication: 3.0
 Corrupt blocks:    0
 Missing replicas:    0 (0.0 %)
 Number of data-nodes:    4
 Number of racks:   1
FSCK ended at Wed Jun 07 14:27:03 UTC 2017 in 1 milliseconds


The filesystem under path '/user/root/external/500MB-File' is HEALTHY
```