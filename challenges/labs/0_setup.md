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
