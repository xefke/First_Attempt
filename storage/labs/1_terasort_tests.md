# TeraGen and TeraSort
## Create an end-user Linux account named with your GitHub handle
```
useradd xefke
```

## Create a home HDFS directory for this user as well
```
sudo -u hdfs hdfs dfs -mkdir /user/xefke
sudo -u hdfs hdfs dfs -chown xefke:xefke /user/xefke
```

### Run the following exercises as this user
Become user:
```
sudo -su xefke
```

#### Create a 10 GB file using teragen
* Set the number of mappers to four
* Limit the block size to 32 MB
* Land the result under your user's home directory
* Use the time command to report the job's duration

TeraGen Command:
```
time /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Ddfs.blocksize=33554432 -Dmapreduce.job.maps=4 100000000 /user/xefke/10GB-Map4-Block32MB
```
Time Results:
```
real  3m12.896s
user  0m6.446s
sys 0m0.862s
```
Data:
```
hdfs dfs -ls /user/xefke
Found 2 items
drwx------   - xefke xefke          0 2017-06-07 14:41 /user/xefke/.staging
drwxr-xr-x   - xefke xefke          0 2017-06-07 14:41 /user/xefke/10GB-Map4-Block32MB
```

### Run the terasort command on this file
* Use the time command to report the job's duration
* Land the result under your user's home directory

TeraSort Command:
```
time /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=4 -Dmapreduce.job.reduces=4 /user/xefke/10GB-Map4-Block32MB /user/xefke/10GB-Map4-Block32MB_SORT
```
Time Result:
```
real	5m56.894s
user	0m9.917s
sys	0m1.062s
```
Data:
```
hdfs dfs -ls /user/xefke
Found 3 items
drwx------   - xefke xefke          0 2017-06-07 14:55 /user/xefke/.staging
drwxr-xr-x   - xefke xefke          0 2017-06-07 14:41 /user/xefke/10GB-Map4-Block32MB
drwxr-xr-x   - xefke xefke          0 2017-06-07 14:55 /user/xefke/10GB-Map4-Block32MB_SORT
```