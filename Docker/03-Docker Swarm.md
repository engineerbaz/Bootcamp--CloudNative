## Swarm

`docker swarm init`

```
docker swarm join --token SWMTKN-1-5gryn9e48z923herrpq1eizedn23ft8nkzvemkaaj0243x74cu-0kduitrdny0c37u513ocwvcw6 192.168.144.131:2377
```

`firewall-cmd --add-port=2377/tcp --permanent` & reload it 


`docker node ls`


```yaml
docker service create --name http-svc -p 5000:80 httpd
```

docker service create --name nginx-svc -p 5000:80 --replicas=3 nginx




