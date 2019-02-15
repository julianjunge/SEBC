# Hostname

MariaDB [(none)]> `select @@hostaname`

```
+---------------------------+
| @@hostname                |
+---------------------------+
| ip-10-0-0-30.ec2.internal |
+---------------------------+
1 row in set (0.00 sec)
```

# Version
MariaDB [(none)]> `SELECT VERSION();

```
+----------------+
| VERSION()      |
+----------------+
| 5.5.63-MariaDB |
+----------------+
1 row in set (0.00 sec)

```

# List all Databases
MariaDB [(none)]> `SHOW DATABASES;`
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
8 rows in set (0.00 sec)

```



