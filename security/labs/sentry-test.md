# SENTRY

## Test 1: No tables
```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/node01.sebc@SEBC
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/node01.sebc@SEBC
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables
. . . . . . . . . . . . . . . . . . . .> ;
INFO  : Compiling command(queryId=hive_20170608121515_77756cfc-36a4-43bf-bccf-7965014accd0): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608121515_77756cfc-36a4-43bf-bccf-7965014accd0); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20170608121515_77756cfc-36a4-43bf-bccf-7965014accd0): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608121515_77756cfc-36a4-43bf-bccf-7965014accd0); Time taken: 0.154 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.35 seconds)
0: jdbc:hive2://localhost:10000/default>
```

## Create Group
```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170608123636_4e8cdb78-588a-4c2a-9260-f4b6fe58fe37): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608123636_4e8cdb78-588a-4c2a-9260-f4b6fe58fe37); Time taken: 0.053 seconds
INFO  : Executing command(queryId=hive_20170608123636_4e8cdb78-588a-4c2a-9260-f4b6fe58fe37): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608123636_4e8cdb78-588a-4c2a-9260-f4b6fe58fe37); Time taken: 0.023 seconds
INFO  : OK
No rows affected (0.091 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170608123636_0e3152f5-14e4-4b7a-a792-245646f9b782): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608123636_0e3152f5-14e4-4b7a-a792-245646f9b782); Time taken: 0.058 seconds
INFO  : Executing command(queryId=hive_20170608123636_0e3152f5-14e4-4b7a-a792-245646f9b782): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608123636_0e3152f5-14e4-4b7a-a792-245646f9b782); Time taken: 0.079 seconds
INFO  : OK
No rows affected (0.15 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP xefke;
INFO  : Compiling command(queryId=hive_20170608123636_b9bd2dde-6727-466c-8493-dc9fdd43f08b): GRANT ROLE sentry_admin TO GROUP xefke
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608123636_b9bd2dde-6727-466c-8493-dc9fdd43f08b); Time taken: 0.053 seconds
INFO  : Executing command(queryId=hive_20170608123636_b9bd2dde-6727-466c-8493-dc9fdd43f08b): GRANT ROLE sentry_admin TO GROUP xefke
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608123636_b9bd2dde-6727-466c-8493-dc9fdd43f08b); Time taken: 0.031 seconds
INFO  : OK
No rows affected (0.097 seconds)
```

## Test 2: Yes Tables
```
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170608123636_488fa759-0024-430d-9bbb-46957acb242d): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608123636_488fa759-0024-430d-9bbb-46957acb242d); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20170608123636_488fa759-0024-430d-9bbb-46957acb242d): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608123636_488fa759-0024-430d-9bbb-46957acb242d); Time taken: 0.098 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.214 seconds)
```
## Create additional Users/Groups
```
[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "groupadd selector"
[1] 12:41:24 [SUCCESS] 10.1.1.101
[2] 12:41:24 [SUCCESS] 10.1.1.104
[3] 12:41:24 [SUCCESS] 10.1.1.105
[4] 12:41:24 [SUCCESS] 10.1.1.102
[5] 12:41:24 [SUCCESS] 10.1.1.103

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "groupadd inserters"
[1] 12:41:29 [SUCCESS] 10.1.1.101
[2] 12:41:29 [SUCCESS] 10.1.1.105
[3] 12:41:29 [SUCCESS] 10.1.1.102
[4] 12:41:29 [SUCCESS] 10.1.1.103
[5] 12:41:29 [SUCCESS] 10.1.1.104

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "useradd -u 1200 -g inserters ferdinand"
[1] 12:41:33 [SUCCESS] 10.1.1.103
[2] 12:41:33 [SUCCESS] 10.1.1.102
[3] 12:41:33 [SUCCESS] 10.1.1.105
[4] 12:41:33 [SUCCESS] 10.1.1.101
[5] 12:41:34 [SUCCESS] 10.1.1.104

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "useradd -u 1100 -g selector george"
[1] 12:41:37 [SUCCESS] 10.1.1.101
[2] 12:41:37 [SUCCESS] 10.1.1.102
[3] 12:41:37 [SUCCESS] 10.1.1.104
[4] 12:41:37 [SUCCESS] 10.1.1.105
[5] 12:41:37 [SUCCESS] 10.1.1.103

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /etc/passwd | grep george"
[1] 12:42:08 [SUCCESS] 10.1.1.102
george:x:1100:501::/home/george:/bin/bash
[2] 12:42:08 [SUCCESS] 10.1.1.101
george:x:1100:501::/home/george:/bin/bash
[3] 12:42:08 [SUCCESS] 10.1.1.103
george:x:1100:501::/home/george:/bin/bash
[4] 12:42:08 [SUCCESS] 10.1.1.104
george:x:1100:501::/home/george:/bin/bash
[5] 12:42:08 [SUCCESS] 10.1.1.105
george:x:1100:501::/home/george:/bin/bash

[root@ip-10-1-1-100 ~]# pssh -h "nodes.txt" -l root -i "-O StrictHostKeyChecking=no" "cat /etc/passwd | grep ferdinand"
[1] 12:42:32 [SUCCESS] 10.1.1.101
ferdinand:x:1200:502::/home/ferdinand:/bin/bash
[2] 12:42:32 [SUCCESS] 10.1.1.102
ferdinand:x:1200:502::/home/ferdinand:/bin/bash
[3] 12:42:32 [SUCCESS] 10.1.1.103
ferdinand:x:1200:502::/home/ferdinand:/bin/bash
[4] 12:42:32 [SUCCESS] 10.1.1.105
ferdinand:x:1200:502::/home/ferdinand:/bin/bash
[5] 12:42:32 [SUCCESS] 10.1.1.104
ferdinand:x:1200:502::/home/ferdinand:/bin/bash

## Create principals
```
[root@ip-10-1-1-100 ~]# ssh node01
Last login: Thu Jun  8 12:38:54 2017 from 10.1.1.100

[root@node01 ~]# kadmin.local
Authenticating as principal xefke/admin@SEBC with password.

kadmin.local:  addprinc -pw krb5george george@SEBC
WARNING: no policy specified for george@SEBC; defaulting to no policy
Principal "george@SEBC" created.

kadmin.local:  addprinc -pw krb5ferdinand ferdinand@SEBC
WARNING: no policy specified for ferdinand@SEBC; defaulting to no policy
Principal "ferdinand@SEBC" created.
```

## Create new roles
```0: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
```
```
INFO  : Compiling command(queryId=hive_20170608125050_f3ffb727-26f2-45ef-8b57-7c39b7a6fcc7): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608125050_f3ffb727-26f2-45ef-8b57-7c39b7a6fcc7); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20170608125050_f3ffb727-26f2-45ef-8b57-7c39b7a6fcc7): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608125050_f3ffb727-26f2-45ef-8b57-7c39b7a6fcc7); Time taken: 0.034 seconds
INFO  : OK
No rows affected (0.172 seconds)
```
```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
```
```
INFO  : Compiling command(queryId=hive_20170608125050_312bab05-9aae-420a-a057-961f4b0c6da7): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170608125050_312bab05-9aae-420a-a057-961f4b0c6da7); Time taken: 0.051 seconds
INFO  : Executing command(queryId=hive_20170608125050_312bab05-9aae-420a-a057-961f4b0c6da7): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608125050_312bab05-9aae-420a-a057-961f4b0c6da7); Time taken: 0.021 seconds
INFO  : OK
No rows affected (0.085 seconds)
```
## Test 3
### George
```
[root@node01 ~]# kinit george
Password for george@SEBC:
[root@node01 ~]# beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/node01.sebc@SEBC
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/node01.sebc@SEBC
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170608125454_ce04e886-b11d-4f38-989c-5023082930f5): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608125454_ce04e886-b11d-4f38-989c-5023082930f5); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20170608125454_ce04e886-b11d-4f38-989c-5023082930f5): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608125454_ce04e886-b11d-4f38-989c-5023082930f5); Time taken: 0.119 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.31 seconds)
```

### Ferdinand
```
[root@node01 ~]# kinit ferdinand
Password for ferdinand@SEBC:
[root@node01 ~]# beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/node01.sebc@SEBC
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/node01.sebc@SEBC
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170608125656_b3f058d2-03d6-40df-950f-00f8ff61d328): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170608125656_b3f058d2-03d6-40df-950f-00f8ff61d328); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20170608125656_b3f058d2-03d6-40df-950f-00f8ff61d328): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170608125656_b3f058d2-03d6-40df-950f-00f8ff61d328); Time taken: 0.129 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.306 seconds)
```











