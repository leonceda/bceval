## <center> Challenge Setup

* List Cloud Provider
```
AWS 
```

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
