# Challenge 2: Install Cloudera Manager 5.13.x (latest)

```
    2018-03-16 09:24:31,247 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.13.2 (#6 built by jenkins on 20180205-1145 git: caa35e134bfc8a112ad1f3cae7d80a2b1f30796f)    
```

```
    2018-03-16 09:25:51,641 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
```

```
    # Auto-generated by scm_prepare_database.sh on Fri Mar 16 09:23:30 UTC 2018
    #
    # For information describing how to configure the Cloudera Manager Server
    # to connect to databases, see the "Cloudera Manager Installation Guide."
    #
    com.cloudera.cmf.db.type=mysql
    com.cloudera.cmf.db.host=ip-172-31-12-170.eu-west-1.compute.internal
    com.cloudera.cmf.db.name=scm
    com.cloudera.cmf.db.user=scm
    com.cloudera.cmf.db.setupType=EXTERNAL
    com.cloudera.cmf.db.password=scm_password    
```