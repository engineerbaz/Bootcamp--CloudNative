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

`systemctl list-units` to view list of service 


`gluster volume create bazVol 192.168.144.131:/gluster/disk/brick/ force`
`gluster volume start bazVol`

`firewall-cmd --add-service=glusterfs --permanent` to add service in firewall


`docker service create --mount type=bind,src=/bazVol/httpd,dst=/var/www/html --name bazdockerindex -p 5000:80 centos/httpd` for making volumes 


=============


