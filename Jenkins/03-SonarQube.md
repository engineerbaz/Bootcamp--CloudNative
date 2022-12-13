# Sonar Qube 

Static Code Analysis 
Each language has its own sets of rules.


- Stop Jenkins
- make user sonarqube
- download SonarQube
- unzip

====$
Credentils
admin /admin
web
admin/sonarqube
CLI
sonarqube/sonarqube
====$

## Sonar Scanner
Create a configuration file in your project's root directory called `sonar-project.properties` in machine

```
sonar.projectKey=my:projectred
sonar.projectName=Myproject
sonar.projectVersion=1.0
```

Now move to directory where code is there and update `sonar-project.properties` as

```
sonar.host.url=http://172.21.74.53:9000
sonar.login=admin
sonar.password=sonarqube
```

Now run batch file of Sonar Scanner as 
`d:\sonar-scanner-cli-4.7.0.2747-windows\sonar-scanner-4.7.0.2747-windows\bin\sonar-scanner.bat`

====
# Attach Postgres SQL with SonarQube 

- Install Postgres SQL 
- Docker compose file
  - docker-compose -d up 

```yaml 
version: "3.9"
services:
  sqdb:
    image: postgres
    ports:
      - "5432:5432"
    container_name: sqdb
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=Red*St0ne
      - POSTGRES_DB=sonar
    volumes:
      - ./postgresql_data:/var/lib/postgresql/data

```
`ulimit -a`
`sysctl -p`


# docker compose up -d

Open `vim /etc/sysctl.conf`
# vm.max_map_count = 262144


Now open `vim /etc/security/limits.conf`
*       soft    nofile  10000
*       hard    nofile  65535

# su - sonarqube
$ cd sonarqube-8.9.10.61524/conf/
$ vim sonar.properties
$ sonar.jdbc.username=postgres
$ sonar.jdbc.password=Red*St0ne
$ sonar.jdbc.url=jdbc:postgresql://192.168.174.201/sonar

$ cd /home/sonarqube/sonarqube-8.9.10.61524/bin/linux-x86-64
./sonar.sh start
 



--
`piof java` shows number of process 

`bash` for reinitaing session 

----

IN CONTAINER

docker exec -ti sqdb bash

root@4c6200872b82:/# su - postgres
 
postgres@4c6200872b82:~$ psql
psql (15.1 (Debian 15.1-1.pgdg110+1))
Type "help" for help.

postgres=# \l

 
 
 
postgres=# \connect sonar
You are now connected to database "sonar" as user "postgres".
sonar=# \d


================================

Make another Docker compose file 

```yaml
version: "3.9"
services:
  sqdb:
    image: postgres
    ports:
      - "5432:5432"
    container_name: sqdb
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=Red*St0ne
      - POSTGRES_DB=sonar
    volumes:
      - ./postgresql_data:/var/lib/postgresql/data

  sonarqube:
    image: sonarqube
    container_name: sonarqube
    ports:
      - "9000:9000"
    environment:
      - sonar.jdbc.url=jdbc:postgresql://sqdb:5432/sonar
      - sonar.jdbc.username=postgres
      - sonar.jdbc.password=Red*St0ne
    volumes:
      - ./sonarqube/data/:/opt/sonarqube/data
      - ./sonarqube/logs/:/opt/sonarqube/logs
      - ./sonarqube/extensions/:/opt/sonarqube/extensions
      - /etc/localtime:/etc/localtime:ro
   
```

if issue with data 

drop database sonar
create database sonar