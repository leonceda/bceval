## <center> Challenge 2: Install Cloudera Manager 5.11

* Install Cloudera Manager on the second node listed in `0_setup.md`
* List the command and output for `ls /etc/yum.repos.d` in `challenges/labs/2_cm.md`
```
[centos@ip-172-31-2-243 ~]$ ll /etc/yum.repos.d
total 36
-rw-r--r--. 1 root root 2001 Jan  7 14:25 CentOS-Base.repo
-rw-r--r--. 1 root root  647 Mar 28  2017 CentOS-Debuginfo.repo
-rw-r--r--. 1 root root  289 Mar 28  2017 CentOS-fasttrack.repo
-rw-r--r--. 1 root root  630 Mar 28  2017 CentOS-Media.repo
-rw-r--r--. 1 root root 7989 Mar 28  2017 CentOS-Vault.repo
-rw-r--r--. 1 root root  957 Nov  5  2012 epel.repo
-rw-r--r--. 1 root root 1056 Nov  5  2012 epel-testing.repo
-rw-r--r--  1 root root  192 Mar  4 13:58 mysql-community.repo

```
  * Copy `cloudera-manager.repo` to `challenges/labs/2_cloudera-manager.repo.md`
* Connect Cloudera Manager Server to its database
  * Use the `scm_prepare_database.sh` script to create the `db.properties` file 
    * List the full command and its output in `2_cm.md`
```
[centos@ip-172-31-2-243 ~]$ sudo /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-6-18.eu-west-1.compute.internal mysql scm scm scm
JAVA_HOME=/usr/java/jdk1.7.0_67
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
2018-03-04 14:29:03,633 [main] INFO  com.cloudera.enterprise.dbutil.DbCommandExecutor  - Successfully connected to database.
All done, your SCM database is configured correctly!

```

* Start the Cloudera Manager server
* In `challenges/labs/2_db.properties.md` add:
  * The first line of the server log
  * The line(s) that contain the phrase "Started Jetty server"
  * The content of the `db.properties` file 
* Push these changes to GitHub and label the Issue `review`
* Assign the issue to the instructors
