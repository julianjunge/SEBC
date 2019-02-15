# Repos

`ls -ltra /etc/yum.repos.d/`

```
total 52
-rw-r--r--.  1 root root 5701 Nov 23 13:16 CentOS-Vault.repo
-rw-r--r--.  1 root root 1331 Nov 23 13:16 CentOS-Sources.repo
-rw-r--r--.  1 root root  630 Nov 23 13:16 CentOS-Media.repo
-rw-r--r--.  1 root root  314 Nov 23 13:16 CentOS-fasttrack.repo
-rw-r--r--.  1 root root  649 Nov 23 13:16 CentOS-Debuginfo.repo
-rw-r--r--.  1 root root 1309 Nov 23 13:16 CentOS-CR.repo
-rw-r--r--.  1 root root 1664 Nov 23 13:16 CentOS-Base.repo
-rw-r--r--   1 root root  137 Feb 15 08:45 mariadb.repo
-rw-r--r--   1 root root  294 Feb 15 09:43 cloudera-manager.repo
drwxr-xr-x.  2 root root  236 Feb 15 09:43 .
drwxr-xr-x. 83 root root 8192 Feb 15 09:46 ..

```

# Prepare the DB

`/usr/share/cmf/schema/scm_prepare_database.sh mysql -h 10.0.0.30 scm scm cloudera`

```
JAVA_HOME=/usr/lib/jvm/jre-openjdk
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/lib/jvm/jre-openjdk/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```