# CM Install Lab

## System Configuration Checks

### 1. Check swappiness

```
    cat /proc/sys/vm/swappiness
    less /etc/sysctl.conf
    sudo su root -
    echo "vm.swappiness = 1" >> /etc/sysctl.conf
    sysctl vm.swappiness=1
    exit
    cat /proc/sys/vm/swappiness
```

### 2. Show mount attributes of your volumes

```
    df -h
    mount
```

Output for the root mount point:
/dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)

### 3. Reserve space setting

The XFS filesystem does not have a reserrve space setting.

### 4. Disable transparent hugepage support

```
    sudo su root -
    cat /sys/kernel/mm/transparent_hugepage/enabled
    cat /sys/kernel/mm/transparent_hugepage/defrag
    vi /etc/rc.d/rc.local
```

Add to /etc/rc.d/rc.local:

```
    echo never > /sys/kernel/mm/transparent_hugepage/enabled
    echo never > /sys/kernel/mm/transparent_hugepage/defrag
```

Then save the file (:x or :qw)
Modify the file permissions

```
    ls -lAh /etc/rc.d/
    chmod +x /etc/rc.d/rc.local
    ls -lAh /etc/rc.d/
```

On RHEL 7.x, modify the GRUB configuration to disable THP.

```
    cat /etc/default/grub
    vi /etc/default/grub
```

Add to the GRUB_CMDLINE_LINUX option:

```
    transparent_hugepage=never
```

Then save the file.

Update the grub config:

```
    grub2-mkconfig -o /boot/grub2/grub.cfg
```

On RHEL, disable the tuned service:

```
    systemctl start tuned
    tuned-adm off
    tuned-adm list
    systemctl stop tuned
    systemctl disable tuned
```

### 5. List network interfaces

```
    ip link show
    netstat -i
    ls -lAh /etc/sysconfig/network-scripts/
    cat /etc/sysconfig/network-scripts/ifcfg-eth0
```

### 6. Show that forward and reverse host lookups are correctly resolved

```
    sudo yum install -y bind-utils
    hostname
    nslookup ip-172-31-2-135.eu-west-1.compute.internal
    nslookup 172.31.2.135
```

### 7. Show the nscd service is running

```
    yum install -y nscd
    systemctl start nscd
    systemctl status nscd
    chkconfig nscd on
```

### 8. Show the ntpd service is running

```
    yum install -y ntp
    systemctl start ntpd
    systemctl status ntpd
    chkconfig ntpd on
    less /etc/ntp.conf
    ntpdate -u 0.rhel.pool.ntp.org
    hwclock --systohc
```

### 9. Disable SELinux

```
    getenforce
    vi /etc/selinux/config
```

Modify _enforcing_ to _permissive_

Save the file

```
    setenforce 0
```

