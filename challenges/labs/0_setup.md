# Setup

## Cloud Provide
* AWS  NA

## List instances 
| Ext                                        | IP             | Int DNS                    | Int IP     |
| ------------------------------------------ | -------------- | -------------------------- | ---------- |
| ec2-3-208-88-106.compute-1.amazonaws.com   | 3.208.88.106   | ip-10-0-0-30.ec2.internal  | 10.0.0.30  |
| ec2-18-214-15-239.compute-1.amazonaws.com  | 18.214.15.239  | ip-10-0-0-27.ec2.internal  | 10.0.0.27  |
| ec2-34-237-137-112.compute-1.amazonaws.com | 34.237.137.112 | 34.237.137.112             | 10.0.0.32  |
| ec2-35-170-55-59.compute-1.amazonaws.com   | 35.170.55.59   | ip-10-0-0-247.ec2.internal | 10.0.0.247 |
| ec2-52-54-73-252.compute-1.amazonaws.com   | 52.54.73.252   | ip-10-0-0-193.ec2.internal | 10.0.0.193 |

# OS running
`cat /etc/os-release`

```
NAME="CentOS Linux"
VERSION="7 (Core)"
ID="centos"
ID_LIKE="rhel fedora"
VERSION_ID="7"
PRETTY_NAME="CentOS Linux 7 (Core)"
ANSI_COLOR="0;31"
CPE_NAME="cpe:/o:centos:centos:7"
HOME_URL="https://www.centos.org/"
BUG_REPORT_URL="https://bugs.centos.org/"

CENTOS_MANTISBT_PROJECT="CentOS-7"
CENTOS_MANTISBT_PROJECT_VERSION="7"
REDHAT_SUPPORT_PRODUCT="centos"
REDHAT_SUPPORT_PRODUCT_VERSION="7"

```

# Disk capacity
`df -h`

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p1   30G  897M   30G   3% /
devtmpfs        7.6G     0  7.6G   0% /dev
tmpfs           7.6G     0  7.6G   0% /dev/shm
tmpfs           7.6G   17M  7.6G   1% /run
tmpfs           7.6G     0  7.6G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000
```

# Repo enabled
`yum repolist enabled`

```
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: repos-va.psychz.net
 * extras: repos-va.psychz.net
 * updates: repos-va.psychz.net
base                                                                                                        | 3.6 kB  00:00:00
extras                                                                                                      | 3.4 kB  00:00:00
updates                                                                                                     | 3.4 kB  00:00:00
(1/4): base/7/x86_64/group_gz                                                                               | 166 kB  00:00:00
(2/4): extras/7/x86_64/primary_db                                                                           | 179 kB  00:00:00
(3/4): base/7/x86_64/primary_db                                                                             | 6.0 MB  00:00:00
(4/4): updates/7/x86_64/primary_db                                                                          | 2.4 MB  00:00:00
repo id                                                      repo name                                                       status
base/7/x86_64                                                CentOS-7 - Base                                                 10,019
extras/7/x86_64                                              CentOS-7 - Extras                                                  364
updates/7/x86_64                                             CentOS-7 - Updates                                               1,067
repolist: 11,450

```

# List users & groups

```
$cat /etc/passwd | grep rocky

rocky:x:3800:3800::/home/rocky:/bin/bash
```

```
$cat /etc/passwd | grep denali

denali:x:3900:3900::/home/denali:/bin/bash
```

```
$cat /etc/group | grep denali

denali:x:3900:
alaska:x:3901:denali
```

```
$cat /etc/group | grep rocky

rocky:x:3800:
colorado:x:3902:rocky

```

```
$getent group alaska

alaska:x:3901:denali
```

```
$getent passwd rocky

rocky:x:3800:3800::/home/rocky:/bin/bash

```
