# Docker

- Invented Solmon Haik

If your application can be dockerized and it can be run anywhere where docker rumtime is available (Linux, Windows)


## Installation 

```
yum -qa | grep docker
yum remove -y $(!!)
```


`wget get.docker.com -O docker.sh` and run as `./docker.sh` then set **execute** permissions as `chmod u+x`
after running docker by 


`systemctl start docker` for starting docker service

`systemctl enable docker` for enabling docker everytime system boots

===

`docker start [detail of container]`  to start exiting container 

`docker run -d --name [name] -p [hostPort:conatinerPort]/[protocal]`

By default **tcp** if we dont mention 

`docker exec -it [containerName] (Shell)` like `docker exec -it nginx bash` 

  - Container uses **namespace** and **cGroup** of Host

===

graceful termination 
forced termination = end process 
SNAT = MASQUERADE 

=======

`iptables -t nat -L | grep 172.17.0.2` 
**DNAT  tcp --  anywhere    0.0.0.0/0   tcp dpt:5000**

`firewall-cmd --add-port=5000` 

----

one after the other: ctrl+p followed by ctrl+q. You turn interactive mode to daemon mode, which keeps the container running but frees up your terminal. You can attach to it later using docker attach, if you need to interact with the container more.
===============
open vpn connect to be installed. 

nmcli connection ens192 ipv4.method manual ipv4.addr 172.21.74.110/24 ipv4.gateway 172.21.74.1 ipv4.dns 172.20.20.48,172.20.20.49 connection.autoconnect yes


nmcli connection ens192 ipv4.method manual ipv4.addr 172.21.74.111/24 ipv4.gateway 172.21.74.1 ipv4.dns 172.20.20.48,172.20.20.49 connection.autoconnect yes
===--




=======

docker run --name=mysql1 -d -e MYSQL_ROOT_PASSWORD=root123 -e MYSQL_USER=baz -e MYSQL_PASSWORD=user123 mysql 

docker run --name=phpmyadmin-test -P -d --link mysql1:db phpmyadmin


docker run --name=phpmyadmin -P -d --link mysql1:db myapp



