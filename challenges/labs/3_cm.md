# Cloudera Cluster Install
## HDFS Output
`[root@node201 ~]# hdfs dfs -ls /user`
```
Found 6 items
drwxrwxrwx   - mapred  hadoop           0 2017-06-09 09:59 /user/history
drwxrwxr-t   - hive    hive             0 2017-06-09 10:00 /user/hive
drwxrwxr-x   - hue     hue              0 2017-06-09 10:00 /user/hue
drwxr-xr-x   - jeremy  jeremy           0 2017-06-09 10:04 /user/jeremy
drwxrwxr-x   - oozie   oozie            0 2017-06-09 10:01 /user/oozie
drwxr-xr-x   - theresa theresa          0 2017-06-09 10:04 /user/theresa
```

## API Call
`[root@node201 ~]# curl -u admin:**** http://node201.sebc:7180/api/v14/hosts`
```
{
  "items" : [ {
    "hostId" : "2c83c71f-da35-404d-b60d-53722693b66a",
    "ipAddress" : "10.1.1.201",
    "hostname" : "node201.sebc",
    "rackId" : "/default",
    "hostUrl" : "http://node201.sebc:7180/cmf/hostRedirect/2c83c71f-da35-404d-b60d-53722693b66a",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "cb0d5922-8b22-430c-973c-54aab0616acf",
    "ipAddress" : "10.1.1.202",
    "hostname" : "node202.sebc",
    "rackId" : "/default",
    "hostUrl" : "http://node201.sebc:7180/cmf/hostRedirect/cb0d5922-8b22-430c-973c-54aab0616acf",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "4d086d5d-db5f-4466-b801-1ca1724f22c0",
    "ipAddress" : "10.1.1.203",
    "hostname" : "node203.sebc",
    "rackId" : "/default",
    "hostUrl" : "http://node201.sebc:7180/cmf/hostRedirect/4d086d5d-db5f-4466-b801-1ca1724f22c0",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "37941994-290c-4bf6-bd26-0ef2257b9c91",
    "ipAddress" : "10.1.1.204",
    "hostname" : "node204.sebc",
    "rackId" : "/default",
    "hostUrl" : "http://node201.sebc:7180/cmf/hostRedirect/37941994-290c-4bf6-bd26-0ef2257b9c91",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "23e2a48b-6eba-467f-9885-19a031966305",
    "ipAddress" : "10.1.1.205",
    "hostname" : "node205.sebc",
    "rackId" : "/default",
    "hostUrl" : "http://node201.sebc:7180/cmf/hostRedirect/23e2a48b-6eba-467f-9885-19a031966305",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  } ]
}
```