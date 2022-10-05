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

`mount -t glusterfs 192.168.144.131:/bazVol /root/bazVolume1`

`docker service create --mount type=bind,src=/root/bazVolume1/httpd,dst=/var/www/html --name bazdockerindex -p 5000:80 centos/httpd` for making volumes 

`docker service create --mount type=bind,source=/root/bazVolume1/httpd,dst=/var/www/html --name dockerindex -p 5000:80 centos/httpd

=============
## Docker Registry

File `/etc/docker-distribution/registry/config.yml`



**VM 3 is registry container**

```
firewall-cmd --add-port=5000/tcp  --permanent
firewall-cmd --reload
```

Add entry in `/etc/hosts` as 
```registry.myapp.com      192.168.144.133```


**VM2 normal machine**

Add entry in `/etc/hosts` as 
```registry.myapp.com      192.168.144.133```

`docker image tag nginx registry.myapp.com:5000/bazapp`

`docker push registry.myapp.com:5000/bazapp`


docker image tag nginx registry.myapp.com:5001/bazapp


docker push registry.myapp.com:5001/bazapp
