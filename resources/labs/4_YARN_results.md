# Test runs
## Worst Run (At this moment)
### 1 Mapper, 1 Reducer, 1024MB Container
```
[root@node01 ~]# time ./YARNtest.sh
Testing loop started on Tue Jun 6 16:05:12 UTC 2017
Number of Mappers 1
Number of reducers 1
Container Memory Size 1024

real	1m40.968s
user	0m6.150s
sys	0m0.794s

real	3m20.196s
user	0m8.801s
sys	0m0.882s
Deleted /user/root/results/tg-10GB-1-1-1024
Deleted /user/root/results/ts-10GB-1-1-1024
Testing loop ended on Tue Jun 6 16:10:19 UTC 2017

real	5m7.110s
user	0m21.899s
sys	0m2.717s
```

## Best Run (At this moment)
### 2 Mapper, 4 Reducer, 1024MB Container
```
[root@node01 ~]# time ./YARNtest.sh
Testing loop started on Tue Jun 6 16:17:36 UTC 2017
Number of Mappers 2
Number of reducers 4
Container Memory Size 1024

real	1m20.050s
user	0m6.349s
sys	0m0.713s

real	1m50.554s
user	0m7.309s
sys	0m0.775s
Deleted /user/root/results/tg-10GB-2-4-1024
Deleted /user/root/results/ts-10GB-2-4-1024
Testing loop ended on Tue Jun 6 16:20:53 UTC 2017

real	3m16.761s
user	0m21.154s
sys	0m2.569s
```


## Other Runs
### 1 Mapper, 2 Reducer, 1024MB Container
```
[root@node01 ~]# time ./YARNtest.sh
Testing loop started on Tue Jun 6 16:13:01 UTC 2017
Number of Mappers 1
Number of reducers 2
Container Memory Size 1024

real	1m41.061s
user	0m5.992s
sys	0m0.721s

real	1m59.480s
user	0m8.667s
sys	0m0.832s
Deleted /user/root/results/tg-10GB-1-2-1024
Deleted /user/root/results/ts-10GB-1-2-1024
Testing loop ended on Tue Jun 6 16:16:47 UTC 2017

real	3m46.435s
user	0m22.289s
sys	0m2.594s
```





