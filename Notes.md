


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