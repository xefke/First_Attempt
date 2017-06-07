# HIVE API Commands
## Summary
Status:
```
curl -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive
```
Stop:
```
curl -X POST -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive/commands/stop
```

Start:
```
curl -X POST -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive/commands/stop
```

Follow Process:
```
curl -u admin:***** http://node01.sebc:7180/api/v1/ccommands/<pid>
```

## Detail
### Get the HIVE Service status
Command:
```
curl -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive
```
Result:
```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://node01.sebc:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false
}
```

### Stop the HIVE Service
Command:
```
curl -X POST -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive/commands/stop
```
Result:
```
{
  "id" : 298,
  "name" : "Stop",
  "startTime" : "2017-06-07T10:37:49.229Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

#### Follow the command:
```
curl -u admin:***** http://node01.sebc:7180/api/v1/commands/298
```
Result:
```
{
  "id" : 298,
  "name" : "Stop",
  "startTime" : "2017-06-07T10:37:49.229Z",
  "endTime" : "2017-06-07T10:37:52.986Z",
  "active" : false,
  "success" : true,
  "resultMessage" : "Successfully stopped service.",
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  },
  "children" : {
    "items" : [ {
      "id" : 300,
      "name" : "Stop",
      "startTime" : "2017-06-07T10:37:49.235Z",
      "endTime" : "2017-06-07T10:37:52.985Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVEMETASTORE-77333a17d553cc66cc48fce1542f303b"
      }
    }, {
      "id" : 299,
      "name" : "Stop",
      "startTime" : "2017-06-07T10:37:49.231Z",
      "endTime" : "2017-06-07T10:37:52.980Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVESERVER2-77333a17d553cc66cc48fce1542f303b"
      }
    } ]
  }
}
```

### Get the HIVE Service status
Command:
```
curl -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive
```
Result:
```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://node01.sebc:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false
}
```

### Start the HIVE Service
Command:
```
curl -X POST -u admin:***** http://node01.sebc:7180/api/v1/clusters/Xefke/services/hive/commands/start
```
Result:
```
{
  "id" : 302,
  "name" : "Start",
  "startTime" : "2017-06-07T10:48:33.781Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```




