# Challenge Setup

Cloud Provider: AWS

Instances by IP:
```
    172.31.12.170
    172.31.0.159
    172.31.3.222
    172.31.15.23
    172.31.3.79
```

Instances by FQDN:

```
    ip-172-31-12-170.eu-west-1.compute.internal 
    ip-172-31-0-159.eu-west-1.compute.internal
    ip-172-31-3-222.eu-west-1.compute.internal
    ip-172-31-15-23.eu-west-1.compute.internal
    ip-172-31-3-79.eu-west-1.compute.internal
```

Linux Release

```
    Linux ip-172-31-12-170.eu-west-1.compute.internal 3.10.0-693.11.6.el7.x86_64 #1 SMP Thu Dec 28 14:23:39 EST 2017 x86_64 x86_64 x86_64 GNU/Linux
```

Filesystem capacity of first node:

```
    Filesystem      Size  Used Avail Use% Mounted on
    /dev/xvda2       50G  1.4G   49G   3% /
    devtmpfs        7.3G     0  7.3G   0% /dev
    tmpfs           7.3G     0  7.3G   0% /dev/shm
    tmpfs           7.3G   17M  7.3G   1% /run
    tmpfs           7.3G     0  7.3G   0% /sys/fs/cgroup
    tmpfs           1.5G     0  1.5G   0% /run/user/1000
    tmpfs           1.5G     0  1.5G   0% /run/user/0
```

Repolist:

```
[root@ip-172-31-12-170 tmp]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                             repo name                                                                                           status
!rhui-REGION-client-config-server-7/x86_64          Red Hat Update Infrastructure 2.0 Client Configuration Server 7                                          1
!rhui-REGION-rhel-server-releases/7Server/x86_64    Red Hat Enterprise Linux Server 7 (RPMs)                                                            18,256
!rhui-REGION-rhel-server-rh-common/7Server/x86_64   Red Hat Enterprise Linux Server 7 RH Common (RPMs)                                                     231
repolist: 18,488
```

/etc/passwd entries for hilary and anupam

```
    hilary:x:2800:1002::/home/hilary:/bin/bash
    anupam:x:2900:1001::/home/anupam:/bin/bash
```

/etc/group entries for analytics and datasci

```
    analytics:x:1001:
    datasci:x:1002:
```