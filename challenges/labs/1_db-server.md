## <center> Challenge 1: Install a MySQL server

* Create the Issue `Install MySQL` if you are using RHEL/Centos 6.x
  * Name it `Install MariaDB` if you are using RHEL/CentOS 7.x
* Assign the Issue to yourself and label it `started`
* Install MySQL 5.6 or MariaDB 5.5 server on the first node listed in `0_setup.md`
  * Use a YUM repository to install the package
  * Copy the repo configuration you used to `challenges/labs/1_my-database-server.repo.md`
* On all cluster nodes
  * Install the database client package and JDBC connector jar on all nodes
* Start the database service and create these databases
  * `scm`
  * `rman`
  * `hive`
  * `oozie`
  * `hue`
* Record the following in `challenges/labs/1_db-server.md`
  * A command and output that shows the hostname of your database server 
```
[centos@ip-172-31-6-18 ~]$ mysql -uroot -e "show variables where Variable_name='hostname';"
+---------------+-------------------------------------------+
| Variable_name | Value                                     |
+---------------+-------------------------------------------+
| hostname      | ip-172-31-6-18.eu-west-1.compute.internal |
+---------------+-------------------------------------------+

```  
* A command and output that reports the database server version
```
[centos@ip-172-31-6-18 ~]$ mysql -uroot -e "SHOW GLOBAL VARIABLES LIKE '%version%';"
+-------------------------+------------------------------+
| Variable_name           | Value                        |
+-------------------------+------------------------------+
| innodb_version          | 5.6.39                       |
| protocol_version        | 10                           |
| slave_type_conversions  |                              |
| version                 | 5.6.39                       |
| version_comment         | MySQL Community Server (GPL) |
| version_compile_machine | x86_64                       |
| version_compile_os      | Linux                        |
+-------------------------+------------------------------+

```
  * A command and output that lists all the databases in the server
```
[centos@ip-172-31-6-18 ~]$ mysql -uroot -e "show databases;"                                            +--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+

```
* Push this work to GitHub
* Label the Issue `review` and assign it to the instructors
