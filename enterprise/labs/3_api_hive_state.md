#HIVE Status

`curl -u julianjunge:cloudera '10.0.0.136:7180/api/v12/clusters/julianjunge/services/hive/'`

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-10-0-0-136.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-10-0-0-136.ec2.internal:7180/cmf/serviceRedirect/hive/intances",
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
```

# Stopping service

`curl -XPOST -u julianjunge:cloudera '10.0.0.136:7180/api/v12/clusters/julianjunge/services/hive/commands/stop'`

```
{
  "id" : 2656,
  "name" : "Stop",
  "startTime" : "2019-02-15T00:16:56.325Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

# Verifying stopped status

`curl -u julianjunge:cloudera '10.0.0.136:7180/api/v12/clusters/julianjunge/services/hive/'`

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-10-0-0-136.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-10-0-0-136.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "STOPPED"
  ```

#Starting Service

`curl -XPOST -u julianjunge:cloudera '10.0.0.136:7180/api/v12/clusters/julianjunge/services/hive/commands/start'`

```
{
  "id" : 2662,
  "name" : "Start",
  "startTime" : "2019-02-15T00:24:29.645Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }

```

# Verifying started Service

`curl -u julianjunge:cloudera '10.0.0.136:7180/api/v12/clusters/julianjunge/services/hive/'`

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-10-0-0-136.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-10-0-0-136.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
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
```

