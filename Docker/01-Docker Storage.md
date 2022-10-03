# Storage

NAS is 

```
lsblk
mkfs -t xfs /dev/sdb
mkdir -p /gluster/disk
mount -t xfs /dev/sdb /gluster/disk/

vi /etc/fstab
/dev/sdb        /gluster/disk   xfs defaults    0 0
```
install `yum install centos-release-gluster9.noarch` to install repo of gluster and update it as `yum update -y` 
then install `yum install glusterfs-server.x86_64` 


`echo $?` for checking status of last run command, if command returns Zero for ok 