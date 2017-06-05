# Lab 01
_*Note: For managing the five nodes, I use parallel SSH from a small jumpnode. In the output, I only show the first of the results while running the commands. This first result might not always be node01.*_

## 1. Check vm.swappiness on all your nodes
Check the current value:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /proc/sys/vm/swappiness"
[1] 13:36:31 [SUCCESS] 10.1.1.101
60
```
Update the value:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "sysctl -w vm.swappiness=1"
[1] 13:36:27 [SUCCESS] 10.1.1.103
vm.swappiness = 1
```

Verify the new value:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /proc/sys/vm/swappiness"
[1] 13:36:31 [SUCCESS] 10.1.1.101
1
```

## 2. Show the mount attributes of all volumes
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /etc/fstab"
[1] 15:00:57 [SUCCESS] 10.1.1.103
LABEL=centos_root   /        ext4      defaults         0 0
devpts     /dev/pts  devpts  gid=5,mode=620   0 0
tmpfs      /dev/shm  tmpfs   defaults         0 0
proc       /proc     proc    defaults         0 0
sysfs      /sys      sysfs   defaults         0 0
```

## 3. Show the reserve space of any non-root, ext-based volumes
Showing all disks and partitions:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "df -h"
[1] 15:14:19 [SUCCESS] 10.1.1.101
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde       126G  793M  119G   1% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
```

## 4. Disable transparent hugepage support
Since the hugepage folder was non existing, I was not able to run the command successfully:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "ls /sys/kernel/mm/"
[1] 15:15:19 [SUCCESS] 10.1.1.101
hugepages
ksm

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "ls /sys/kernel/mm/hugepages"
[1] 15:15:33 [SUCCESS] 10.1.1.101
hugepages-2048kB

```

Tried nonetheless:
```
pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "echo 'never' > /sys/kernel/mm/redhat_transparent_hugepage/defrag"
[1] 14:14:32 [FAILURE] 10.1.1.101 Exited with error code 1
Stderr: bash: /sys/kernel/mm/redhat_transparent_hugepage/defrag: No such file or directory
```

## 5. List your network interface configuration
```
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
```

## 6. List forward and reverse host lookups using getent or nslookup
Install nslookup:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "yum -y install bind-utils"
```
Test the install:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "nslookup www.google.com"
[5] 15:18:38 [SUCCESS] 10.1.1.105
Server:   10.1.1.2
Address:  10.1.1.2#53

Non-authoritative answer:
Name: www.google.com
Address: 209.85.203.103
```

## 7 Show the nscd service is running
Install the nscd service:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "yum -y install nscd"
```

Start the service:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service nscd start"
[1] 14:00:14 [SUCCESS] 10.1.1.101
Starting nscd: [  OK  ]
```

Check if the service is running:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service nscd status"
[1] 14:01:41 [SUCCESS] 10.1.1.101
nscd (pid 1105) is running...
```

Make sure the service starts upon reboot:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "chkconfig nscd on"
[1] 14:02:04 [SUCCESS] 10.1.1.101
```

## 8. Show the ntpd service is running
Install the ntpd service:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "yum -y install ntp"
```

Start the service:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service ntpd start"
```

Check the service status:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "service ntpd status"
[1] 14:05:24 [SUCCESS] 10.1.1.101
ntpd (pid  1263) is running...
```

Make sure the service starts upon reboot:
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "chkconfig ntpd on"
```
