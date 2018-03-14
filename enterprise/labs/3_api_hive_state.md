# Use the CM API

## Hive commands

Stop

```
    curl -X POST -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v14/clusters/jovv/services/hive/commands/stop'
```

Output

```
    {
    "id" : 580,
    "name" : "Stop",
    "startTime" : "2018-03-14T09:51:50.761Z",
    "active" : true,
    "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
    }
```

Start

```
    curl -X POST -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v14/clusters/jovv/services/hive/commands/start'
```

Output

```
    {
    "id" : 584,
    "name" : "Start",
    "startTime" : "2018-03-14T09:52:37.110Z",
    "active" : true,
    "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
    }    
```

Status

```
    curl -X POST -u user:pw 'http://ec2-34-242-187-43.eu-west-1.compute.amazonaws.com:7180/api/v14/clusters/jovv/services/hive'
```

Output

```
    {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
        "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-135.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
    "roleInstancesUrl" : "http://ip-172-31-2-135.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
        "name" : "HIVE_HIVEMETASTORES_HEALTHY",
        "summary" : "GOOD",
        "suppressed" : false
    }, {
        "name" : "HIVE_HIVESERVER2S_HEALTHY",
        "summary" : "GOOD",
        "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive",
    "entityStatus" : "GOOD_HEALTH"
    }
```