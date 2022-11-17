


**tar** is just an archive 
**tar.gz** is archive and compression 

`yum whatprovides ifconfig` helps in finding package name as its not always same as package name 

hair pin mode multiple MAC to be recieved on a port



`nmcli con show`

`nmcli con modify ens33 connection.autoconnect yes` 



**apache** is **httpd** in CentOs distro 
drivers = module in Linux



### Disable SELinux

`vi /etc/sysconfig/selinux` and edit it like `SELINUX=disable` (normally at line 9)
and make it premissive by `setenforce 0` 


### Entering ALIAS, ENV in bashrc

`vi ~/.bashrc` and then run `source ~/.bashrc` for reloading


`exec bash` for implenting changes 


# Add line number in VI 
Write `:set number` in Vi for adding line numbers
==============



nmcli connection modify Wired connection 1 ipv4.method manual ipv4.addresses 192.168.144.128/24 ipv4.dns "8.8.8.8,1.1.1.1" ipv4.gateway 192.168.144.2 connection.autoconnect yes
nmcli con modify ens33 connection.autoconnect yes


nmcli connection reload


vi /etc/hosts
vi /etc/hostname



======================
========================
```shell

#! /bin/bash
yum -y install httpd
systemctl start httpd 
firewall-cmd --add-service=http
firewall-cmd --add-service=http --permenent

```



scp hhtp.sh serverb:/bin/http #copy file to next server 
ssh serverb http  #run file in remote server 


===
#### Copy file from Host to VM
scp ansible@192.168.144.200:/home/ansible/bazPV.yaml d:\

`df -h` for Human readable with 1024 size 
`df -H` for Human readable with 1000 size 


In **vi** you can set Tab Space to 2 by running `set ts=2` after pressing `:` in vi editor.


## Decode Password 
echo -n "emVlc2hhbm11bmlyMTg6WkVFbXVuaXIxOA==" | base64 -d=Abc123


docker run --name=mysql-db -d -e "MYSQL_USER=mysql, MYSQL_PASSWORD=sql123" mysql  


docker exec -ti mysql /bin/bash 
mysql --user=root --password



docker run --name=<name of container> --link <database container>:<name of database> -p 8082:80 <image>
docker run --name=phpadmin --link mysql-1:mydb -p 8082:80 phpadmin