# Yum Repos
`[root@node201 yum.repos.d]# ls -l /etc/yum.repos.d`
```
total 28
-rw-r--r--. 1 root root 1926 Nov 27  2013 CentOS-Base.repo
-rw-r--r--. 1 root root  638 Nov 27  2013 CentOS-Debuginfo.repo
-rw-r--r--. 1 root root  630 Nov 27  2013 CentOS-Media.repo
-rw-r--r--. 1 root root 3664 Nov 27  2013 CentOS-Vault.repo
-rw-r--r--. 1 root root  293 Jun  9 09:07 cloudera-manager.repo
-rw-r--r--. 1 root root 1836 Jun  9 08:27 mysql-community.repo
-rw-r--r--. 1 root root 1885 Apr 27 09:04 mysql-community-source.repo
```
# CM Install
**While running the scm_prepare_database.sh script, it could not finish because the database already exists. Decided to drop the database and try again. Afterwards it worked fine.**

Error:
```
/usr/share/cmf/schema/scm_prepare_database.sh mysql -uroot -pmysqlpw scm scm scmpw
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
2017-06-09 09:17:17,208 [main] ERROR com.cloudera.enterprise.dbutil.DbProvisioner  - Exception when creating/dropping database with user 'root' and jdbc url 'jdbc:mysql://localhost/?useUnicode=true&characterEncoding=UTF-8'
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
2017-06-09 09:17:17,214 [main] ERROR com.cloudera.enterprise.dbutil.DbProvisioner  - Stack Trace:
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
--> Error 1, giving up (use --force if you wish to ignore the error)
[root@node201 yum.repos.d]# clear
[root@node201 yum.repos.d]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -uroot -pmysqlpw scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
2017-06-09 09:17:58,795 [main] ERROR com.cloudera.enterprise.dbutil.DbProvisioner  - Exception when creating/dropping database with user 'root' and jdbc url 'jdbc:mysql://localhost/?useUnicode=true&characterEncoding=UTF-8'
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
2017-06-09 09:17:58,802 [main] ERROR com.cloudera.enterprise.dbutil.DbProvisioner  - Stack Trace:
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
--> Error 1, giving up (use --force if you wish to ignore the error)
```
After dropping database;
```[root@node201 yum.repos.d]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -uroot -pmysqlpw scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
2017-06-09 09:21:51,119 [main] INFO  com.cloudera.enterprise.dbutil.DbCommandExecutor  - Successfully connected to database.
All done, your SCM database is configured correctly!
```