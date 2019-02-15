#System Configuration Lab

## Set VM Swappiness

1. `sudo vi /etc/sysctl.conf`
2. add line `vm.swappiness = 1`

## Disable SeLinux

`vi /etc/selinux/config`

## Disable hugepage support
1. `sudo vi /etc/default/grub`
2. add/append `transparent_hugepage=never` to the line *GRUB_CMDLINE_Linux*
3. reboot machine

## Copy /etc/hosts to all nodes
```
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
10.0.0.32      ip-10-0-0-32.ec2.internal
10.0.0.30      ip-10-0-0-30.ec2.internal
10.0.0.27      ip-10-0-0-27.ec2.internal
10.0.0.247       ip-10-0-0-247.ec2.internal
10.0.0.193       ip-10-0-0-193.ec2.internal
``` 

## add user + group
`adduser julianjunge`

## create group
`sudo groupadd superuser`

## add user
`sudo usermod -a -G wheel julianjunge`
`sudo usermod -a -G superuser julianjunge`

## show mount attributes

1. `cat /proc/mounts`

## List reserve spacing 

1. `df -h / | grep dev | cut -f 3,6 -d\  | awk '{print ($1*.05)+$2}'`

## List Network configuration
1. ifconfig
```
 ifconfig
ens5: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.0.0.124  netmask 255.255.255.0  broadcast 10.0.0.255
        inet6 fe80::13:9fff:fed0:b710  prefixlen 64  scopeid 0x20<link>
        ether 02:13:9f:d0:b7:10  txqueuelen 1000  (Ethernet)
        RX packets 6857  bytes 33259146 (31.7 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 3494  bytes 934837 (912.9 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 1377  bytes 3390190 (3.2 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1377  bytes 3390190 (3.2 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```

## Forward & Reverse Lookup
### hosts
1. `getent hosts`
```
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
10.0.0.136      ip-10-0-0-136.ec2.internal
10.0.0.124      ip-10-0-0-124.ec2.internal
10.0.0.128      ip-10-0-0-128.ec2.internal
10.0.0.72       ip-10-0-0-72.ec2.internal
10.0.0.39       ip-10-0-0-39.ec2.internal
``` 

## NSCD service
1. `ps -aux | grep nscd`
    `centos    5688  0.0  0.0 112708   972 pts/0    S+   11:56   0:00 grep --color=auto nscd`

## NTPD service
1. `ps -aux | grep ntpd`
    `centos    5908  0.0  0.0 112708   976 pts/0    S+   11:58   0:00 grep --color=auto ntpd`

## Install MySQL

1. Installation:
`wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm`
`sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm`
`yum update`

`sudo yum install mysql-server`
`sudo systemctl start mysqld`

3. Configuration & Security:
`sudo mysql_secure_installation`

!! allow root from external sources

## Prepare the DBs

https://www.cloudera.com/documentation/enterprise/latest/topics/cm_ig_mysql.html#cmig_topic_5_5


## Change FQDN of local machine
```/etc/sysconfig/network``` and add ```HOSTNAME=use FQDN provided by AWS for simplicity```

## (Optional)
### change hostname of every machine as follows:
```sudo hostnamectl set-hostname <city>.europe.internal```


#Install Java (all nodes)

## Prepare the repo & install wget
```sudo yum install wget```

### Import the repo
```sudo wget https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo -P /etc/yum.repos.d/```

### get the key
```sudo rpm --import https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera```

### update
```sudo yum update```

#Install the JDK
```sudo yum install oracle.j2sdk1.7```

## verify XOR set the PATH
```sudo vi  ~/.bashrc```

and add
```export JAVA_HOME=/usr/java/jdk1.8.0_141-cloudera```

# install JDBC Connector
```sudo yum install mysql-connector-java```

## Run the installation (master node only)
`sudo yum install cloudera-manager-daemons cloudera-manager-server`

## Run on all the other Agents (optional, can be run from within CMC)
!! Doublecheck if SELinux is disabled!! Otherwise /var/lib/ will contain many folders with wrong permissions.

```sudo yum install cloudera-manager-daemons cloudera-manager-agent`


