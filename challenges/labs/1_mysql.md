# MySQL Server installation

## The hostname of your MySQL node
`cat /etc/sysconfig/network`
```
NETWORKING=yes
NETWORKING_IPV6=no
HOSTNAME=node201.sebc
```

or

`hostname -f`
```
node201.sebc
```

## The command and output for mysql --version
```
[root@ip-10-1-1-201 ~]# mysql --version
mysql  Ver 14.14 Distrib 5.5.56, for Linux (x86_64) using readline 5.1
```

## The command and output for listing MySQL databases
Show schemas:
```
mysql> select * from information_schema.schemata;
+--------------+--------------------+----------------------------+------------------------+----------+
| CATALOG_NAME | SCHEMA_NAME        | DEFAULT_CHARACTER_SET_NAME | DEFAULT_COLLATION_NAME | SQL_PATH |
+--------------+--------------------+----------------------------+------------------------+----------+
| def          | information_schema | utf8                       | utf8_general_ci        | NULL     |
| def          | amon               | utf8                       | utf8_general_ci        | NULL     |
| def          | hue                | utf8                       | utf8_general_ci        | NULL     |
| def          | metastore          | utf8                       | utf8_general_ci        | NULL     |
| def          | mysql              | latin1                     | latin1_swedish_ci      | NULL     |
| def          | oozie              | utf8                       | utf8_general_ci        | NULL     |
| def          | performance_schema | utf8                       | utf8_general_ci        | NULL     |
| def          | rman               | utf8                       | utf8_general_ci        | NULL     |
| def          | scm                | utf8                       | utf8_general_ci        | NULL     |
| def          | sentry             | utf8                       | utf8_general_ci        | NULL     |
+--------------+--------------------+----------------------------+------------------------+----------+
10 rows in set (0.00 sec)
```
or 

Show databases:
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hue                |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
10 rows in set (0.00 sec)
```