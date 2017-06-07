# Questions and Answers
## What is ubertask optimization?
This provides the possibility to run 'small' tasks within one JVM container.
The number and size of the tasks is defined by its parameters.

This function can be enabled through YARN > Configuration.
Select the "Performance" category and search for "ubertask"
Four parameters can be set:
* mapreduce.job.ubertask.enable (enables the function)
* mapreduce.job.ubertask.maxmaps (defines the max number of mappers in one JVM)
* mapreduce.job.ubertask.maxreduces (defines the max number of reducers in one JVM)
* mapreduce.job.ubertask.maxbytes (defines the max job size in order to be run as ubertask)

## Where in CM is the Kerberos Security Realm value displayed?
* Administration > Settings > Kerberos
  * Kerberos Security Realm

Other location:
There are multiple locations:
* HDFS > Configuration > Security
  * Trusted Kerberos Realms: shows all trusted realms if configured

## Which CDH service(s) host a property for enabling Kerberos authentication?
This is done on cluster level. Use the drop-down list next to the cluster name and select "Enable Kerberos".

## How do you upgrade the CM agents?
You can upgrade the CM Agents via Hosts > All Hosts > Re-run Upgrade Wizard. 

## Give the tsquery statement used to chart Hue's CPU utilization?
```
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
```

## Name all the roles that make up the Hive service
* Hive Metastore Server
* WebHCat Server
* HiveServer2
* Gateway

## What steps must be completed before integrating Cloudera Manager with Kerberos?
1. Make sure you have a working kerberos realm and KDC on the cluster machines
* Installed krb5server on Kerberos server
* Installed packages openldap-clients on the CM Server hosts
* Installed krb5-workstation, krb5-libs on all hosts

* Edited the krb5.conf file to work
* Edited the kdc.conf file to work

* Created KDC Database
* Add ACLs to ACL File

2. Add Administrator principals
* for cloudera-scm
* for cloudera
* for your hdfs superuser account
* for each user account

3. Started Kerberos

4. Installed/Enabled JCE Policy File if using AES-256 encryption

