# Monitoring Lab

### What is ubertask optimization?

Ubertask optimization runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

### Where in CM is the Kerberos Security Realm value displayed?

Administration -> Settings -> Kerberos

### Which CDH service(s) host a property for enabling Kerberos authentication?

Zookeeper
HDFS
YARN

### How do you upgrade the CM agents?

Re-run Upgrade Wizard on the All Hosts page.

### Give the tsquery statement used to chart Hue's CPU utilization?

select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME

### Name all the roles that make up the Hive service

Gateway
Hive Metastore Server
HiveServer2

### What steps must be completed before integrating Cloudera Manager with Kerberos?


Have a working Kerberos key distribution center (KDC) and realm setup, Kerberos client packages are installed on all cluster hosts and hosts that will be used to access the cluster.
Install a JCE Policy File.
Create a Kerberos Principal for the Cloudera Manager Server.