# API Calls After upgrade

## Report the latest available version of the API
The latest version is v14

Command:
```
curl -u admin:***** http://node01.sebc:7180/api/v14/clusters/
```

Result:
```
{
  "items" : [ {
    "name" : "cluster",
    "displayName" : "Xefke",
    "version" : "CDH5",
    "fullVersion" : "5.9.2",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "clusterUrl" : "http://node01.sebc:7180/cmf/clusterRedirect/cluster",
    "hostsUrl" : "http://node01.sebc:7180/cmf/clusterRedirect/cluster/hosts",
    "entityStatus" : "GOOD_HEALTH"
  } ]
}
```

## Report the CM version
Command:
```
curl -u admin:***** http://node01.sebc:7180/api/v14/cm/version
```

Result:
```
{
  "version" : "5.9.2",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170330-1814",
  "gitHash" : "822da28bff818f57fc1bfc3eafe3a550300ef1b0",
  "snapshot" : false
}
```

## List all CM users
Command:
```
curl -u admin:***** http://node01.sebc:7180/api/v14/users
```

Result:
```
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

## Report the database server in use by CM
Command:
```
curl -u admin:sebcadmin http://node01.sebc:7180/api/v14/cm/scmDbInfo
```

Result:
```
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```