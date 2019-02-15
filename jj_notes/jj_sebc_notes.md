# SEBC Notes

## Overview

|     | Brusels | Rome | Berlin | Vienna | Prag |
| --- | ------- | ---- | ------ | ------ | ----
|     |         |      |        |        |
|     |         |      |        |        |
|     |         |      |        |        |

# Prerequisites

* Original Instructions:
https://www.cloudera.com/documentation/enterprise/5-15-x/topics/configure_network_names.html

## Hosts File

### copy to /etc/hosts of every machine

```
10.0.0.136 ip-10-0-0-136.ec2.internal brussels.europe.local
10.0.0.124 ip-10-0-0-124.ec2.internal berlin.europe.local
10.0.0.128 ip-10-0-0-128.ec2.internal prag.europe.local
10.0.0.72 ip-10-0-0-72.ec2.internal vienna.europe.local
10.0.0.39 ip-10-0-0-39.ec2.internal rome.europe.local
```

ip-10-0-0-136.ec2.internal 
ip-10-0-0-124.ec2.internal
ip-10-0-0-128.ec2.internal
ip-10-0-0-72.ec2.internal
ip-10-0-0-39.ec2.internal

### change hostname of every machine as follows:
```sudo hostnamectl set-hostname <city>.europe.internal```

### Change FQDN of local machine to xxx.europe.internal in 
```/etc/sysconfig/network``` and add ```HOSTNAME=<city>.europe.internal``` 



# Installation of Cloudera Manager

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

## Run the installation (master node only)
`sudo yum install cloudera-manager-daemons cloudera-manager-server`

## Run on all the other Agents
```sudo yum install cloudera-manager-daemons cloudera-manager-agent```

## sudo service cloudera-scm-agent

* brussels - done
* viena - 
* prag - 
* rome - 
* berlin - 

Follow the instruntions from:
* https://www.cloudera.com/documentation/enterprise/5-15-x/topics/installation.html

# Install&prep MySql
Follow https://www.cloudera.com/documentation/enterprise/5-15-x/topics/cm_ig_mysql.html#cmig_topic_5_5


# install JDBC Connector
```sudo yum install mysql-connector-java```




#Noteworthy

## Increase volume
https://support.amimoto-ami.com/english/self-hosting-accounts/increasing-your-ec2-volume-size

## Ports
https://www.cloudera.com/documentation/enterprise/5-15-x/topics/cm_ig_ports.html

sudo yum remove cloudera-manager-agent && sudo hostnamectl set-hostname ip-10-0-0-
