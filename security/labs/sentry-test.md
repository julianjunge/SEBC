#Sentry user priviliges

```
beeline> !connect jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
scan complete in 2ms
Connecting to jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
Connected to: Apache Hive (version 1.1.0-cdh5.16.1)
Driver: Hive JDBC (version 1.1.0-cdh5.16.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://10.0.0.128:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20190214155959_8dc4a04d-a45a-4e4a-9de0-800850fd1a83): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20190214155959_8dc4a04d-a45a-4e4a-9de0-800850fd1a83); Time taken: 0.054 seconds
INFO  : Executing command(queryId=hive_20190214155959_8dc4a04d-a45a-4e4a-9de0-800850fd1a83): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20190214155959_8dc4a04d-a45a-4e4a-9de0-800850fd1a83); Time taken: 0.08 seconds
INFO  : OK
+---------------------+--+
|      tab_name       |
+---------------------+--+
| 201408_status_data  |
| customers           |
| sample_07           |
| sample_08           |
| web_logs            |
+---------------------+--+
5 rows selected (0.207 seconds)
0: jdbc:hive2://10.0.0.128:10000/default>

```

# Kinit as George and Ferdinand

## George

```
[centos@ip-10-0-0-124 ~]$ kdestroy
[centos@ip-10-0-0-124 ~]$ kinit george
Password for george@EXAMPLE.COM:
[centos@ip-10-0-0-124 ~]$ beeline
Beeline version 1.1.0-cdh5.16.1 by Apache Hive
beeline> jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
. . . .>
. . . .>
. . . .> ;
No current connection
beeline> !connect jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
scan complete in 1ms
Connecting to jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
Connected to: Apache Hive (version 1.1.0-cdh5.16.1)
Driver: Hive JDBC (version 1.1.0-cdh5.16.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://10.0.0.128:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20190214160404_32e698e1-9017-45d9-ad1d-71589fb86b14): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20190214160404_32e698e1-9017-45d9-ad1d-71589fb86b14); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20190214160404_32e698e1-9017-45d9-ad1d-71589fb86b14): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20190214160404_32e698e1-9017-45d9-ad1d-71589fb86b14); Time taken: 0.092 seconds
INFO  : OK
+---------------------+--+
|      tab_name       |
+---------------------+--+
| 201408_status_data  |
| customers           |
| sample_07           |
| sample_08           |
| web_logs            |
+---------------------+--+
5 rows selected (0.217 seconds)

```

## Ferdinand

```
[centos@ip-10-0-0-124 ~]$ kinit ferdinand
Password for ferdinand@EXAMPLE.COM:
[centos@ip-10-0-0-124 ~]$ beeline
Beeline version 1.1.0-cdh5.16.1 by Apache Hive
beeline> !connect jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
scan complete in 1ms
Connecting to jdbc:hive2://10.0.0.128:10000/default;principal=hive/ip-10-0-0-128.ec2.internal@EXAMPLE.COM
Connected to: Apache Hive (version 1.1.0-cdh5.16.1)
Driver: Hive JDBC (version 1.1.0-cdh5.16.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://10.0.0.128:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20190214160808_48734b13-9b9d-47ec-9a78-b215f44fc95e): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20190214160808_48734b13-9b9d-47ec-9a78-b215f44fc95e); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20190214160808_48734b13-9b9d-47ec-9a78-b215f44fc95e): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20190214160808_48734b13-9b9d-47ec-9a78-b215f44fc95e); Time taken: 0.081 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.206 seconds)

```


