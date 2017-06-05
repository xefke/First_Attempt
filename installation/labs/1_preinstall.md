# Lab 01
## Check vm.swappiness on all your nodes

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /proc/sys/vm/swappiness"
[1] 13:36:31 [SUCCESS] 10.1.1.101
60
[2] 13:36:31 [SUCCESS] 10.1.1.103
60
[3] 13:36:31 [SUCCESS] 10.1.1.102
60
[4] 13:36:31 [SUCCESS] 10.1.1.104
60
[5] 13:36:31 [SUCCESS] 10.1.1.105
60

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "sysctl -w vm.swappiness=1"
[1] 13:36:27 [SUCCESS] 10.1.1.103
vm.swappiness = 1
[2] 13:36:27 [SUCCESS] 10.1.1.101
vm.swappiness = 1
[3] 13:36:27 [SUCCESS] 10.1.1.102
vm.swappiness = 1
[4] 13:36:27 [SUCCESS] 10.1.1.104
vm.swappiness = 1
[5] 13:36:27 [SUCCESS] 10.1.1.105
vm.swappiness = 1

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /proc/sys/vm/swappiness"
[1] 13:36:31 [SUCCESS] 10.1.1.101
1
[2] 13:36:31 [SUCCESS] 10.1.1.103
1
[3] 13:36:31 [SUCCESS] 10.1.1.102
1
[4] 13:36:31 [SUCCESS] 10.1.1.104
1
[5] 13:36:31 [SUCCESS] 10.1.1.105
1


## Show the mount attributes of all volumes

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "df -h"
[1] 13:43:34 [SUCCESS] 10.1.1.101
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[2] 13:43:34 [SUCCESS] 10.1.1.102
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[3] 13:43:34 [SUCCESS] 10.1.1.103
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[4] 13:43:34 [SUCCESS] 10.1.1.105
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[5] 13:43:34 [SUCCESS] 10.1.1.104
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  662M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm

## Show the reserve space of any non-root, ext-based volumes
* XFS volumes do not maintain reserve space


## Disable transparent hugepage support
pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "echo 'never' > /sys/kernel/mm/redhat_transparent_hugepage/defrag"
[1] 14:14:32 [FAILURE] 10.1.1.101 Exited with error code 1
Stderr: bash: /sys/kernel/mm/redhat_transparent_hugepage/defrag: No such file or directory
[2] 14:14:32 [FAILURE] 10.1.1.102 Exited with error code 1
Stderr: bash: /sys/kernel/mm/redhat_transparent_hugepage/defrag: No such file or directory
[3] 14:14:32 [FAILURE] 10.1.1.103 Exited with error code 1
Stderr: bash: /sys/kernel/mm/redhat_transparent_hugepage/defrag: No such file or directory
[4] 14:14:32 [FAILURE] 10.1.1.105 Exited with error code 1
Stderr: bash: /sys/kernel/mm/redhat_transparent_hugepage/defrag: No such file or directory
[5] 14:14:32 [FAILURE] 10.1.1.104 Exited with error code 1
Stderr: bash: /sys/kernel/mm/redhat_transparent_hugepage/defrag: No such file or directory


## List your network interface configuration
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "ip addr"
[1] 13:56:33 [SUCCESS] 10.1.1.101
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:71:f8:7e:d9:ca brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.101/24 brd 10.1.1.255 scope global eth0
    inet6 fe80::871:f8ff:fe7e:d9ca/64 scope link
       valid_lft forever preferred_lft forever
[2] 13:56:33 [SUCCESS] 10.1.1.105
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:46:88:ba:b6:42 brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.105/24 brd 10.1.1.255 scope global eth0
    inet6 fe80::846:88ff:feba:b642/64 scope link
       valid_lft forever preferred_lft forever
[3] 13:56:33 [SUCCESS] 10.1.1.103
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:35:cd:2a:bc:1a brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.103/24 brd 10.1.1.255 scope global eth0
    inet6 fe80::835:cdff:fe2a:bc1a/64 scope link
       valid_lft forever preferred_lft forever
[4] 13:56:33 [SUCCESS] 10.1.1.104
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:5d:c5:24:ad:2e brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.104/24 brd 10.1.1.255 scope global eth0
    inet6 fe80::85d:c5ff:fe24:ad2e/64 scope link
       valid_lft forever preferred_lft forever
[5] 13:56:33 [SUCCESS] 10.1.1.102
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:23:7b:02:a6:46 brd ff:ff:ff:ff:ff:ff
    inet 10.1.1.102/24 brd 10.1.1.255 scope global eth0
    inet6 fe80::823:7bff:fe02:a646/64 scope link
       valid_lft forever preferred_lft forever

## List forward and reverse host lookups using getent or nslookup


## Show the nscd service is running
yum -y install nscd

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service nscd start"
[1] 14:00:14 [SUCCESS] 10.1.1.101
Starting nscd: [  OK  ]
[2] 14:00:14 [SUCCESS] 10.1.1.102
Starting nscd: [  OK  ]
[3] 14:00:14 [SUCCESS] 10.1.1.103
Starting nscd: [  OK  ]
[4] 14:00:14 [SUCCESS] 10.1.1.104
Starting nscd: [  OK  ]
[5] 14:00:14 [SUCCESS] 10.1.1.105
Starting nscd: [  OK  ]

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service nscd status"
[1] 14:01:41 [SUCCESS] 10.1.1.101
nscd (pid 1105) is running...
[2] 14:01:41 [SUCCESS] 10.1.1.103
nscd (pid 1100) is running...
[3] 14:01:41 [SUCCESS] 10.1.1.104
nscd (pid 1109) is running...
[4] 14:01:41 [SUCCESS] 10.1.1.105
nscd (pid 1100) is running...
[5] 14:01:41 [SUCCESS] 10.1.1.102
nscd (pid 1110) is running...

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "chkconfig nscd on"
[1] 14:02:04 [SUCCESS] 10.1.1.101
[2] 14:02:04 [SUCCESS] 10.1.1.102
[3] 14:02:04 [SUCCESS] 10.1.1.103
[4] 14:02:04 [SUCCESS] 10.1.1.104
[5] 14:02:04 [SUCCESS] 10.1.1.105

Show the ntpd service is running
yum -y install ntp
chkconfig --list ntpd
chkconfig ntpd on

sudo service ntpd start

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service ntpd status"
[1] 14:05:24 [SUCCESS] 10.1.1.101
ntpd (pid  1263) is running...
[2] 14:05:24 [SUCCESS] 10.1.1.102
ntpd (pid  1278) is running...
[3] 14:05:24 [SUCCESS] 10.1.1.103
ntpd (pid  1256) is running...
[4] 14:05:24 [SUCCESS] 10.1.1.105
ntpd (pid  1261) is running...
[5] 14:05:24 [SUCCESS] 10.1.1.104
ntpd (pid  1267) is running...