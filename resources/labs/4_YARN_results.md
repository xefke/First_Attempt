# Test runs
```
RunNo	Map	Red	ConMem	MapTime	RedTime	TotTime
-----	---	---	------	-------	-------	-------
1	1	1	1024	01:40	03:20	05:07
2	1	2	1024	01:41	01:59	03:46
3	2	4	1024	01:20	01:50	03:16
4	4	8	1024	01:26	02:10	03:44
5	3	6	1024	02:20	01:49	04:15
6	2	6	1024	01:12	01:42	03:00
7	2	6	2048	01:31	02:12	03:50
8	2	6	512	01:09	01:53	03:07
9	4	4	512	00:59	02:55	04:00
10	6	2	512	00:57	02:07	03:10
11	6	4	512	00:58	01:57	03:02
12	6	4	1024	01:11	02:08	03:25
```

## Worst Run
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

## Best Run
### 6 Mapper, 4 Reducer, 512MB Container
```
[root@node01 ~]# time ./YARNtest.sh
Testing loop started on Wed Jun 7 08:37:31 UTC 2017
Number of Mappers 6
Number of reducers 4
Container Memory Size 512

real	0m58.975s
user	0m5.887s
sys	0m0.704s

real	1m57.253s
user	0m7.831s
sys	0m0.838s
Deleted /user/root/results/tg-10GB-6-4-512
Deleted /user/root/results/ts-10GB-6-4-512
Testing loop ended on Wed Jun 7 08:40:33 UTC 2017

real	3m2.028s
user	0m21.093s
sys	0m2.562s
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
```
[root@node01 ~]# time ./YARNtest.sh
Testing loop started on Wed Jun 7 07:58:26 UTC 2017
Number of Mappers 4
Number of reducers 8
Container Memory Size 1024

real	1m26.972s
user	0m6.274s
sys	0m0.723s

real	2m10.345s
user	0m9.525s
sys	0m1.014s
Deleted /user/root/results/tg-10GB-4-8-1024
Deleted /user/root/results/ts-10GB-4-8-1024
Testing loop ended on Wed Jun 7 08:02:10 UTC 2017

real	3m44.327s
user	0m24.620s
sys	0m2.866s
```
```
[root@node01 ~]# time ./YARNtest.sh
Testing loop started on Wed Jun 7 08:06:23 UTC 2017
Number of Mappers 3
Number of reducers 6
Container Memory Size 1024

real	2m20.068s
user	0m6.009s
sys	0m0.714s

real	1m49.745s
user	0m8.782s
sys	0m0.827s
Deleted /user/root/results/tg-10GB-3-6-1024
Deleted /user/root/results/ts-10GB-3-6-1024
Testing loop ended on Wed Jun 7 08:10:38 UTC 2017

real	4m15.408s
user	0m21.822s
sys	0m2.495s
```




