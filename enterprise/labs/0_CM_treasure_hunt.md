#Treasure Hunt

1. What is ubertask optimization?
Ubertask optimization is defined by:

 * mapreduce.job.ubertask.maxmaps
 * mapreduce.job.ubertask.maxreduces
 * mapreduce.job.ubertask.maxbytes

Ubertask optimization is in charge of running "sufficiently small" jobs sequetialy.

>> http://www.tothenew.com/blog/yarn-cluster-optimization-for-spark-jobs/

2. Where in CM is the Kerberos Security Realm value displayed?

* Administration >> Settings >> Kerberos >> Kerberos Security Realm

3. Which CDH service(s) host a property for enabling Kerberos authentication?

* Core service host a property to enable Kerberos (HDFS, Zookeeper, YARN, HIVE, HUE, OOzie & CMS)

4. How do you upgrade the CM agents?
  a.) Manually on each node through the use of OS tools e.g `$yum updata`.
  b.) Through the use of CM Hosts >> All Hosts >> Re-run Upgrade Wizard.

5. Give the tsquery statement used to chart Hue's CPU utilization?
6. Name all the roles that make up the Hive service
* Hive Metastore
* Hive Gateway
* Hive2

8. What steps must be completed before integrating Cloudera Manager with Kerberos?
      ```
    1. Java Cryptografic Extension installed.
    2. KDC needs to be available. LDAP(AD), OpenLDAP and/or MIT KDC work with Cloudera.
    3. Kerberos packages installed: 
        **Server**: krb5-server, krb5-libs, krb5-auth-dialog, krb5-workstation
        **client**: krb5-libs, krb5-auth-dialog, krb5-workstation
    4. Account with privilige to create KDC accounts
    5. Kerberos Principal for CMS.

   





