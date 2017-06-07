# Snapshotting

Copy file to Jumpnode:
```
scp Big\ Industries/SEBC-master.zip root@54.77.135.159:~/
```

Copy file to node01:
```
scp SEBC-master.zip root@node01:~/
```

Make the precious dir:
hdfs dfs -mkdir precious

Verify:
```
hdfs dfs -ls
drwxr-xr-x   - root root          0 2017-06-07 14:57 precious
```

Put zip in precious:
```
hdfs dfs -put SEBC-master.zip /user/root/precious
```

Verify file:
```
hdfs dfs -ls /user/roious
Found 1 items
-rw-r--r--   3 root root     449822 2017-06-07 14:59 /user/root/precious/SEBC-master.zip
```

Enable snapshots: 
In CM go to HDFS > File Browser, select the directory and select enable snapshots from the drop down list.

Create snapshot:
In CM go to HDFS > File Browser, select the directory and select 'Create Snapshot', fill in the name "sebc-hdfs-test"

Delete the directory (or try):
```
hdfs dfs -rm -R -skipTrash /user/root/precious
rm: The directory /user/root/precious cannot be deleted since /user/root/precious is snapshottable and already has snapshots
```

Delete the file:
```
hdfs dfs -rm -skipTrash /user/root/precious/SEBC-master.zip
Deleted /user/root/precious/SEBC-master.zip
```

Restore the snapshot:
In CM go to HDFS > File Browser, select the directory and select 'Restore Snapshot'