#System Configuration Lab

## Set VM Swappiness

1. `sudo vi /etc/sysctl.conf`
2. add line `vm.swappiness = 1`

## show mount attributes

1. `cat /proc/mounts`

## List reserve spacing 

1. `df -h / | grep dev | cut -f 3,6 -d\  | awk '{print ($1*.05)+$2}'`

## Disable hugepage support
1. `sudo vi /etc/default/grub`
2. add/append `transparent_hugepage=never` to the line *GRUB_CMDLINE_Linux*
3. reboot machine

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