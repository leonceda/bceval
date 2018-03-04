## <center> Challenge 3 - Install CDH 5.9

* Create the Issue `Install CDH`
* Assign yourself and label it `started`
* Deploy Coreset services + Spark
  * Rename your cluster after your GitHub handle
* Create user directories in HDFS for `saturn` and `haley`
* Add the following to `3_cm.md`:
    * The command and output for `hdfs dfs -ls /user`
```
[centos@ip-172-31-6-18 ~]$ sudo -u hdfs hdfs dfs -ls /user                                              Found 7 items
drwxr-xr-x   - haley  haley           0 2018-03-04 14:54 /user/haley
drwxrwxrwx   - mapred hadoop          0 2018-03-04 14:52 /user/history
drwxrwxr-t   - hive   hive            0 2018-03-04 14:54 /user/hive
drwxrwxr-x   - hue    hue             0 2018-03-04 15:14 /user/hue
drwxrwxr-x   - oozie  oozie           0 2018-03-04 14:54 /user/oozie
drwxr-xr-x   - saturn saturn          0 2018-03-04 14:54 /user/saturn
drwxr-x--x   - spark  spark           0 2018-03-04 14:53 /user/spark

```
    * The command and output from the CM API call `../api/v14/hosts` 
```
[centos@ip-172-31-6-18 ~]$ curl -v -u 'admin:******' http://ip-172-31-2-243.eu-west-1.compute.internal:7180/api/v14/hosts
* About to connect() to ip-172-31-2-243.eu-west-1.compute.internal port 7180 (#0)
*   Trying 172.31.2.243... connected
* Connected to ip-172-31-2-243.eu-west-1.compute.internal (172.31.2.243) port 7180 (#0)
* Server auth using Basic with user 'admin'
> GET /api/v14/hosts HTTP/1.1
> Authorization: Basic YWRtaW46YWRtaW4=
> User-Agent: curl/7.19.7 (x86_64-redhat-linux-gnu) libcurl/7.19.7 NSS/3.27.1 zlib/1.2.3 libidn/1.18 libssh2/1.4.2
> Host: ip-172-31-2-243.eu-west-1.compute.internal:7180
> Accept: */*
>
< HTTP/1.1 200 OK
< Expires: Thu, 01-Jan-1970 00:00:00 GMT
< Set-Cookie: CLOUDERA_MANAGER_SESSIONID=1clovnz5x0pf119417m91sr0ff;Path=/;HttpOnly
< Content-Type: application/json
< Date: Sun, 04 Mar 2018 14:43:32 GMT
< Transfer-Encoding: chunked
< Server: Jetty(6.1.26.cloudera.4)
<
{
  "items" : [ {
    "hostId" : "608424e8-7714-48c9-9a8f-76205c2cdef8",
    "ipAddress" : "172.31.2.243",
    "hostname" : "ip-172-31-2-243.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/hostRedirect/608424e8-7714-48c9-9a8f-76205c2cdef8",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 1,
    "totalPhysMemBytes" : 8251174912
  }, {
    "hostId" : "e85c61c8-0497-468b-8c0c-c7c09be1ac57",
    "ipAddress" : "172.31.21.14",
    "hostname" : "ip-172-31-21-14.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/hostRedirect/e85c61c8-0497-468b-8c0c-c7c09be1ac57",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722612224
  }, {
    "hostId" : "2e2d8e19-6fcb-4e13-b9ec-8735a14525fa",
    "ipAddress" : "172.31.29.119",
    "hostname" : "ip-172-31-29-119.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/hostRedirect/2e2d8e19-6fcb-4e13-b9ec-8735a14525fa",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722612224
  }, {
    "hostId" : "1b033e0e-340e-49d0-9ac2-56cde51875b3",
    "ipAddress" : "172.31.30.155",
    "hostname" : "ip-172-31-30-155.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/hostRedirect/1b033e0e-340e-49d0-9ac2-56cde51875b3",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16722612224
  }, {
    "hostId" : "e9006b34-57ba-49d8-8681-3e9f1b55e252",
    "ipAddress" : "172.31.6.18",
    "hostname" : "ip-172-31-6-18.eu-west-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/hostRedirect/e9006b34-57ba-49d8-8681-3e9f1b55e252",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 1,
    "totalPhysMemBytes" : 8251174912
  } ]
* Connection #0 to host ip-172-31-2-243.eu-west-1.compute.internal left intact
* Closing connection #0

```
    * The command and output from the CM API call `../api/v8/clusters/<githubName>/services`
```
[centos@ip-172-31-6-18 ~]$ curl -v -u 'admin:admin' http://ip-172-31-2-243.eu-west-1.compute.internal:7180/api/v8/clusters/lda/services
* About to connect() to ip-172-31-2-243.eu-west-1.compute.internal port 7180 (#0)
*   Trying 172.31.2.243... connected
* Connected to ip-172-31-2-243.eu-west-1.compute.internal (172.31.2.243) port 7180 (#0)
* Server auth using Basic with user 'admin'
> GET /api/v8/clusters/lda/services HTTP/1.1
> Authorization: Basic YWRtaW46YWRtaW4=
> User-Agent: curl/7.19.7 (x86_64-redhat-linux-gnu) libcurl/7.19.7 NSS/3.27.1 zlib/1.2.3 libidn/1.18 libssh2/1.4.2
> Host: ip-172-31-2-243.eu-west-1.compute.internal:7180
> Accept: */*
>
< HTTP/1.1 200 OK
< Expires: Thu, 01-Jan-1970 00:00:00 GMT
< Set-Cookie: CLOUDERA_MANAGER_SESSIONID=c0jtwptffh4h1e4b7yrxr1mgj;Path=/;HttpOnly
< Content-Type: application/json
< Date: Sun, 04 Mar 2018 15:17:39 GMT
< Transfer-Encoding: chunked
< Server: Jetty(6.1.26.cloudera.4)
<
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hive",
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
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/zookeeper",
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
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/oozie",
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
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/yarn",
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
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-2-243.eu-west-1.compute.internal:7180/cmf/serviceRedirect/hdfs",
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
  } ]
* Connection #0 to host ip-172-31-2-243.eu-west-1.compute.internal left intact
* Closing connection #0

```
* Login to Hue and install the Hive sample data 
    * Copy a HUE screen that shows the Hive tables to `challenges/labs/3_hue_hive.png`
```
See attached screenshot
```
* Push this work to GitHub and label the Issue `review`
* Assign the issue to the instructors
