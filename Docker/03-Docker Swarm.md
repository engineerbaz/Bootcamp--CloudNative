## Swarm

- Scheduling 
- State managemnet 
- Secret managemnet
- Distributed networking and loaodbalancer 


`docker swarm init`

```
docker swarm join --token SWMTKN-1-5gryn9e48z923herrpq1eizedn23ft8nkzvemkaaj0243x74cu-0kduitrdny0c37u513ocwvcw6 192.168.144.131:2377
```

`firewall-cmd --add-port=2377/tcp --permanent` & reload it `systemctl reload firewalld` or `firewall-cmd --reload`


`docker node ls`


```yaml
docker service create --name http-svc -p 5000:80 httpd
```

docker service create --name nginx-svc -p 5000:80 --replicas=3 nginx



====

`ss -lptn | grep 5000` for checking 

`iptables -t nat -L -n | grep 5000`

```shell
[root@node1 ~]# iptables -t nat -L -n | grep 5000
DNAT       tcp  --  0.0.0.0/0            0.0.0.0/0            tcp dpt:5000 to:172.18.0.2:5000
[root@node1 ~]#
```

`docker node ps $(docker node ls -q) --filter desired-state=Running | uniq`


===

1. we
2. 
3. npm
4. npm run build 

1. Framework Project made on 
2. which tool used for manage it 
3. How did you build it. 
4. where are build asset stored
5. how deployed