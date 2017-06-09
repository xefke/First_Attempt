# Challenge Setup

## List the cloud provider you are using (AWS, GCE, Azure, other)
AWS

## List the Linux release you have chosen
Centos 6.5

## Show that the disk space on each node is at least 30 GB
```
[1] 08:09:59 [SUCCESS] 10.1.1.201
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[2] 08:09:59 [SUCCESS] 10.1.1.202
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[3] 08:09:59 [SUCCESS] 10.1.1.203
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[4] 08:09:59 [SUCCESS] 10.1.1.204
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[5] 08:09:59 [SUCCESS] 10.1.1.205
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
```

## List the command and output for yum repolist enabled
```
[root@ip-10-1-1-201 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
base                                                                 | 3.7 kB     00:00
base/primary_db                                                      | 4.7 MB     00:00
extras                                                               | 3.4 kB     00:00
extras/primary_db                                                    |  29 kB     00:00
updates                                                              | 3.4 kB     00:00
updates/primary_db                                                   | 1.4 MB     00:00
repo id                              repo name                                        status
base                                 CentOS-6 - Base                                  6,706
extras                               CentOS-6 - Extras                                   45
updates                              CentOS-6 - Updates                                 354
repolist: 7,105
```

## List the /etc/passwd entries for theresa and jeremy in your setup file
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /etc/passwd | grep 'theresa\|jeremy'"
[1] 08:17:24 [SUCCESS] 10.1.1.201
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:1200:501::/home/jeremy:/bin/bash
[2] 08:17:24 [SUCCESS] 10.1.1.202
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:1200:501::/home/jeremy:/bin/bash
[3] 08:17:24 [SUCCESS] 10.1.1.204
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:1200:501::/home/jeremy:/bin/bash
[4] 08:17:24 [SUCCESS] 10.1.1.203
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:1200:501::/home/jeremy:/bin/bash
[5] 08:17:24 [SUCCESS] 10.1.1.205
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:1200:501::/home/jeremy:/bin/bash
```

## List the /etc/group entries for conservative and labour in your setup file
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /etc/group | grep 'conservative\|labour'"
[1] 08:18:36 [SUCCESS] 10.1.1.201
conservative:x:500:
labour:x:501:
[2] 08:18:36 [SUCCESS] 10.1.1.202
conservative:x:500:
labour:x:501:
[3] 08:18:36 [SUCCESS] 10.1.1.203
conservative:x:500:
labour:x:501:
[4] 08:18:36 [SUCCESS] 10.1.1.204
conservative:x:500:
labour:x:501:
[5] 08:18:36 [SUCCESS] 10.1.1.205
conservative:x:500:
labour:x:501:
```












