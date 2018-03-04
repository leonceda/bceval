## <center> Challenge Setup

* Create the Issue `Challenges Setup`
* In the file `challenges/labs/0_setup.md`:
  * List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)
```
Cloud Provider: AWS
```
  * List your instances by IP address and DNS name (don't use `/etc/hosts` for this)
```
ip-172-31-2-243.eu-west-1.compute.internal has address 172.31.2.243
ip-172-31-21-14.eu-west-1.compute.internal has address 172.31.21.14
ip-172-31-29-119.eu-west-1.compute.internal has address 172.31.29.119
ip-172-31-30-155.eu-west-1.compute.internal has address 172.31.30.155
ip-172-31-6-18.eu-west-1.compute.internal has address 172.31.6.18

```
  * List the Linux release you are using 
```
CentOS release 6.9 (Final)
```
  * List the file system capacity for the first node 
```
[centos@ip-172-31-6-18 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.4G   45G   6% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
/dev/xvdb        99G   60M   99G   1% /data/00
```
  * List the command and output for `yum repolist enabled` 
```
 [WARNING]: Consider using yum module rather than running yum

ip-172-31-6-18.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-2-243.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-29-119.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-21-14.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-30-155.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

```
* Add the following Linux accounts to all nodes
  * User `saturn` with a UID of `2800`
  * User `haley` with a UID of `2900`
  * Create the group `comets` and add `haley` to it
  * Create the group `planets` and add `saturn` to it
* List the `/etc/passwd` entries for `saturn` and `haley` 
  * Do not list the entire file
```
ip-172-31-2-243.eu-west-1.compute.internal | SUCCESS | rc=0 >>
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

ip-172-31-30-155.eu-west-1.compute.internal | SUCCESS | rc=0 >>
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

ip-172-31-21-14.eu-west-1.compute.internal | SUCCESS | rc=0 >>
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

ip-172-31-29-119.eu-west-1.compute.internal | SUCCESS | rc=0 >>
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

ip-172-31-6-18.eu-west-1.compute.internal | SUCCESS | rc=0 >>
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash

```
* List the `/etc/group` entries for `comets` and `planets` 
  * Do not list the entire file
```
ip-172-31-2-243.eu-west-1.compute.internal | SUCCESS | rc=0 >>
comets:x:2901:haley
planets:x:2902:saturn

ip-172-31-29-119.eu-west-1.compute.internal | SUCCESS | rc=0 >>
comets:x:3003:haley
planets:x:3004:saturn

ip-172-31-21-14.eu-west-1.compute.internal | SUCCESS | rc=0 >>
comets:x:3003:haley
planets:x:3004:saturn

ip-172-31-30-155.eu-west-1.compute.internal | SUCCESS | rc=0 >>
comets:x:3003:haley
planets:x:3004:saturn

ip-172-31-6-18.eu-west-1.compute.internal | SUCCESS | rc=0 >>
comets:x:2901:haley
planets:x:2902:saturn

```
* Push these updates to GitHub 
* Label your Issue `review` 
* Assign the Issue to the instructors
* List Linux release
```
CentOS release 6.9 (Final)
```

* Show disk space
```
ip-172-31-17-168.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  6.1G   41G  13% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
/dev/xvdb        99G  573M   98G   1% /data/00
cm_processes    3.9G  316K  3.9G   1% /var/run/cloudera-scm-agent/process

ip-172-31-17-231.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  6.1G   41G  13% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
/dev/xvdb        99G  573M   98G   1% /data/00
cm_processes    3.9G  372K  3.9G   1% /var/run/cloudera-scm-agent/process

ip-172-31-27-64.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  6.1G   41G  14% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
/dev/xvdb        99G   60M   99G   1% /data/00
cm_processes    3.9G     0  3.9G   0% /var/run/cloudera-scm-agent/process

ip-172-31-27-116.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           3.9G  180K  3.9G   1% /dev/shm
/dev/xvdb        99G   60M   99G   1% /data/00

ip-172-31-16-223.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.0G   45G   5% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
/dev/xvdb        99G   60M   99G   1% /data/00

```

* List the command output `yum repolist enabled`
```
ip-172-31-17-168.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-16-223.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirror.vorboss.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-17-231.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-27-64.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: s3-mirror-eu-west-1.fedoraproject.org
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

ip-172-31-27-116.eu-west-1.compute.internal | SUCCESS | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: ftp.heanet.ie
 * epel: mirrors.coreix.net
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id          repo name                                                status
base             CentOS-6 - Base                                           6,706
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,457
extras           CentOS-6 - Extras                                            52
updates          CentOS-6 - Updates                                          950
repolist: 20,165

```

* List `/etc/passwd`
```
[centos@ip-172-31-27-116 ~]$ cat /etc/passwd | egrep 'theresa|jeremy'
theresa:x:2000:2000::/home/theresa:/bin/bash
jeremy:x:3000:3000::/home/jeremy:/bin/bash
```

* List `/etc/group`
```
[centos@ip-172-31-27-116 ~]$ cat /etc/group | egrep 'conservative|labour'
conservative:x:3001:
labour:x:3002:
```
