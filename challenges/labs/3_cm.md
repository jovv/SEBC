# Install C.D.H.13.x

```
    [hdfs@ip-172-31-0-159 ec2-user]$ hdfs dfs -ls /user
    Found 7 items
    drwxr-xr-x   - anupam analytics          0 2018-03-16 09:48 /user/anupam
    drwxr-xr-x   - hilary datasci            0 2018-03-16 09:48 /user/hilary
    drwxrwxrwx   - mapred hadoop             0 2018-03-16 09:46 /user/history
    drwxrwxr-t   - hive   hive               0 2018-03-16 09:47 /user/hive
    drwxrwxr-x   - hue    hue                0 2018-03-16 09:47 /user/hue
    drwxrwxr-x   - impala impala             0 2018-03-16 09:47 /user/impala
    drwxrwxr-x   - oozie  oozie              0 2018-03-16 09:47 /user/oozie
```

```
    [hdfs@ip-172-31-0-159 ec2-user]$ curl -u admin:admin 'ec2-54-246-252-71.eu-west-1.compute.amazonaws.com:7180/api/v14/hosts'
    {
    "items" : [ {
        "hostId" : "6406338f-96ff-498f-951f-1bc31648232c",
        "ipAddress" : "172.31.0.159",
        "hostname" : "ip-172-31-0-159.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/hostRedirect/6406338f-96ff-498f-951f-1bc31648232c",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15599980544
    }, {
        "hostId" : "27deaf65-8a78-4732-9128-a67bc3c20811",
        "ipAddress" : "172.31.12.170",
        "hostname" : "ip-172-31-12-170.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/hostRedirect/27deaf65-8a78-4732-9128-a67bc3c20811",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15599980544
    }, {
        "hostId" : "ec97a48e-1bd9-4579-bab2-2ae57bae90e2",
        "ipAddress" : "172.31.15.23",
        "hostname" : "ip-172-31-15-23.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/hostRedirect/ec97a48e-1bd9-4579-bab2-2ae57bae90e2",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15599980544
    }, {
        "hostId" : "abe4f191-7417-4912-a7e3-04cb7efa8508",
        "ipAddress" : "172.31.3.222",
        "hostname" : "ip-172-31-3-222.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/hostRedirect/abe4f191-7417-4912-a7e3-04cb7efa8508",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15599980544
    }, {
        "hostId" : "6dabd1d7-3c20-410c-846a-2befaa49d0f8",
        "ipAddress" : "172.31.3.79",
        "hostname" : "ip-172-31-3-79.eu-west-1.compute.internal",
        "rackId" : "/default",
        "hostUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/hostRedirect/6dabd1d7-3c20-410c-846a-2befaa49d0f8",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "commissionState" : "COMMISSIONED",
        "numCores" : 4,
        "numPhysicalCores" : 2,
        "totalPhysMemBytes" : 15599980544
    } ]
    }
```

```
    [hdfs@ip-172-31-0-159 ec2-user]$ curl -u admin:admin 'ec2-54-246-252-71.eu-west-1.compute.amazonaws.com:7180/api/v8/clusters'
    {
    "items" : [ {
        "name" : "cluster",
        "displayName" : "jovv",
        "version" : "CDH5",
        "fullVersion" : "5.13.2",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ]
    } ]
    }
```

```
    [hdfs@ip-172-31-0-159 ec2-user]$ curl -u admin:admin 'ec2-54-246-252-71.eu-west-1.compute.amazonaws.com:7180/api/v8/clusters/jovv/services'
    {
    "items" : [ {
        "name" : "zookeeper",
        "type" : "ZOOKEEPER",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/zookeeper",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "ZOOKEEPER_CANARY_HEALTH",
        "summary" : "GOOD"
        }, {
        "name" : "ZOOKEEPER_SERVERS_HEALTHY",
        "summary" : "GOOD"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "ZooKeeper"
    }, {
        "name" : "oozie",
        "type" : "OOZIE",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/oozie",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
        "summary" : "GOOD"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "Oozie"
    }, {
        "name" : "hue",
        "type" : "HUE",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hue",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "HUE_HUE_SERVERS_HEALTHY",
        "summary" : "GOOD"
        }, {
        "name" : "HUE_LOAD_BALANCER_HEALTHY",
        "summary" : "GOOD"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "Hue"
    }, {
        "name" : "hdfs",
        "type" : "HDFS",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hdfs",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
        "summary" : "GOOD"
        }, {
        "name" : "HDFS_CANARY_HEALTH",
        "summary" : "GOOD"
        }, {
        "name" : "HDFS_DATA_NODES_HEALTHY",
        "summary" : "GOOD"
        }, {
        "name" : "HDFS_FREE_SPACE_REMAINING",
        "summary" : "GOOD"
        }, {
        "name" : "HDFS_HA_NAMENODE_HEALTH",
        "summary" : "GOOD"
        }, {
        "name" : "HDFS_MISSING_BLOCKS",
        "summary" : "GOOD"
        }, {
        "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
        "summary" : "GOOD"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "HDFS"
    }, {
        "name" : "impala",
        "type" : "IMPALA",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/impala",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "IMPALA_ASSIGNMENT_LOCALITY",
        "summary" : "DISABLED"
        }, {
        "name" : "IMPALA_CATALOGSERVER_HEALTH",
        "summary" : "GOOD"
        }, {
        "name" : "IMPALA_IMPALADS_HEALTHY",
        "summary" : "GOOD"
        }, {
        "name" : "IMPALA_STATESTORE_HEALTH",
        "summary" : "GOOD"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "Impala"
    }, {
        "name" : "yarn",
        "type" : "YARN",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/yarn",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "YARN_JOBHISTORY_HEALTH",
        "summary" : "GOOD"
        }, {
        "name" : "YARN_NODE_MANAGERS_HEALTHY",
        "summary" : "GOOD"
        }, {
        "name" : "YARN_RESOURCEMANAGERS_HEALTH",
        "summary" : "GOOD"
        }, {
        "name" : "YARN_USAGE_AGGREGATION_HEALTH",
        "summary" : "DISABLED"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "YARN (MR2 Included)"
    }, {
        "name" : "hive",
        "type" : "HIVE",
        "clusterRef" : {
        "clusterName" : "cluster"
        },
        "serviceUrl" : "http://ip-172-31-0-159.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
        "serviceState" : "STARTED",
        "healthSummary" : "GOOD",
        "healthChecks" : [ {
        "name" : "HIVE_HIVEMETASTORES_HEALTHY",
        "summary" : "GOOD"
        }, {
        "name" : "HIVE_HIVESERVER2S_HEALTHY",
        "summary" : "GOOD"
        } ],
        "configStalenessStatus" : "FRESH",
        "clientConfigStalenessStatus" : "FRESH",
        "maintenanceMode" : false,
        "maintenanceOwners" : [ ],
        "displayName" : "Hive"
    } ]
    }
```