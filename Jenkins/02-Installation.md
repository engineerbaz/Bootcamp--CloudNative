# Installation



sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

wget -O /etc/yum.repos.d/jenkins.repo  --no-check-certificate    https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo yum upgrade
# Add required dependencies for the jenkins package
sudo yum install java-11-openjdk
sudo yum install jenkins
sudo systemctl daemon-reload

systemctl enable jenkins
systemctl start jenkins
systemctl status jenkins


Then Login using IP with port 8080 
Add password from path `/var/lib/jenkins/secrets/initialAdminPassword`
Install Plugins 

http://172.21.74.53:8080/
B@Z12345


Websware -- IBM Java 
JBoss 
Tomcat

===


git remote add jkn https://github.com/baztesting/jenkins.git
git branch -M main
git push -u jkn main


tail /etc/passwd

usermod -s /bin/bash jenkins

su - jenkins




cat id_rsa
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEA3fFcMS6Aq9/vn6UANtyOSDVl6tHIg7kSVnyeLOysIxyqD6+q
ahihlI8oOi0YBZ1KsjRWxVyGDJzCLJX5OAidTLwolTQ021Wc0nRQpQ8yNq/uDg5r
sQcg3klz00Ajinw7FvU/NIZNqvcU50CQgvNFr360YJ8kMOHVFnaFuS0UVQcE+K03
N25CTLGud+5mtVDPEaig2pi/AENbftG6BZsoWXUI24vEKHCHe4dwNFx2Gfg7H0We
tIFb88X7bmDbMCBP7WdXNQi4g/SvjKfUl9NqiexoOdDavarpH6/VO0mTKNQiraoJ
KIXhJLXcPA3ypQB9X+yy/+olUvCRIfSOwKG7NwIDAQABAoIBACz7tWbWeQfc/HFL
/Q4hh8kE4aJFYLGp+hiDa3/JfF4leiZxwUV9toootcuMxjilF7WkvA2GYjj+MLDe
uMNto4wg+sy65xepc36ISqwZt2C0Kbi5nYQk4LmNA6fGcS2pXkSZ8nSP4AAN0jPI
t0GDUxVtxdtrhedObmT+Ir5Ub7GHuPcMydp/7gNxai6IHHql4jD5hjhhjbV2wBVX
YzMPhmusY29fMyWWWJxiAoTbLJAMyiQkR0bx8X2lHV0oEOaHtGjAsuNYplFHNdQa
frJkzv2ax2ta06vgK0pvlkzghlhGEZ6VrmnU7RWIs8qb50K1Ub+BD2KjQkD9MaxY
9lCmBxECgYEA+Sx/W+DtHWdOH2nIRt1oyycqyX1ShwP8zakJppR7YQlf70G5BgCz
51DSpIJ7qhI9tJjbVTfGQ85YVNz3J9ut8ETrKE//rAbI4yA3fM6dg26AxVPSdqNh
rgfOaaEn9A36K1U11DpAdMYbp8PJTZgT8RzuwbMWdX4QFTMSvpvAZKkCgYEA5AXi
8gkg58Zj2uny9Hv80E5oMbeDgRsfV7wU9rxyhsioDXuhPYhwINZCpSH0gURQu9DH
2SRcawvXeiiKovSwJN4PrzsnqQ/sRgJk10cDa4Wx4pKxLxHd76rWcJ+R0r2QNh+h
zl7bJ6wt57NOdQLQXMH73P4Q5jH5lXCYQWX1LN8CgYAHusKkpgCVBexdexmUYS/s
BWYFZBbYS15fPtwmx7pgEztfn6lOr1zlUxOFuOp/Jxu063z6UsWaut7wmv4rxVvK
9UhaMskanAdFTG2MOJiYSChEdsozlfPkwyc7DZ3Aq2JUT8tgrwHq3W5kMOWgu5P6
ycv6RETxFh0Hm1L8iLZaKQKBgBSdZ6AkLSJnMD3parqpvviCLi9YfP4eGp5O9cI8
1UnUOEVHyRMME78UP+A4CqfpKjdgr8C05doTrv5vTeFfp9EddmOMQJCrTNwjeURx
OiDtbGCkjHpJ7jutwUdbVc6srq4F/BXxQ3T5vwi0kEJJ59aK/x9CpPp6yCq3jDxV
YG4XAoGAbs2JCAsIRfHfzzIdEtPgFej5o4hdGm9+OZzCC2mwYW84KjBf6Xec7wd/
kPLE5AMVaowjmAIUJxqRHiAoF75SWPP+0kJprmDH/E3461f2SjkHEyvA0ZRV3cgM
+qYKFEH4Bcxg+O8tE7j15guP/OOqHrTfn3TY6D9/GqAvJVrTSPE=
-----END RSA PRIVATE KEY-----


ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDd8VwxLoCr3++fpQA23I5INWXq0ciDuRJWfJ4s7KwjHKoPr6pqGKGUjyg6LRgFnUqyNFbFXIYMnMIslfk4CJ1MvCiVNDTbVZzSdFClDzI2r+4ODmuxByDeSXPTQCOKfDsW9T80hk2q9xTnQJCC80WvfrRgnyQw4dUWdoW5LRRVBwT4rTc3bkJMsa537ma1UM8RqKDamL8AQ1t+0boFmyhZdQjbi8QocId7h3A0XHYZ+DsfRZ60gVvzxftuYNswIE/tZ1c1CLiD9K+Mp9SX02qJ7Gg50Nq9qukfr9U7SZMo1CKtqgkoheEktdw8DfKlAH1f7LL/6iVS8JEh9I7Aobs3 jenkins@jenkins-server


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


https://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@github.com/baztesting/jenkins.git





Two Method for creating Pipeline
1. Token based 
2. Key based 


add path of git insatllation , that can be checked by `whereis git` 



yumm install httpd -y 
systemctl start httpd
firewall-cmd --list-all 
firewall-cmd --add-service http
getenforce

MASTER 
ssh-copy-id 172.21.74.103
yum install rsync -y 

WEBSERVER



ssh-copy-id root@172.21.74.103

ssh root@172.21.74.103

yum install rsync -y
rsync -av /var/lib/jenkins/workspace/jenkinspipeline/ 172.21.74.103:/var/www/html



`grep -r BAZ .` for searching content


- stop jenkins-server
- stop web-server
- install Docker CE on both machines 
-  
- 

Install Docker 
sudo yum install -y yum-utils
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo

sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
sudo systemctl start docker
sudo systemctl enable docker

**jenkins-server**
docker pull jenkins/jenkins:lts

    docker run -d -p 8080:8080 -v /opt/jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts


docker logs jenkins
chown 1000:1000 /opt/jenkins_home
docker rm -f jenkins
docker run -d -p 8080:8080 -v /opt/jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts



----

docker run -d -p 80:80 -v /opt/webroot:/usr/share/nginx/html --name web1 nginx


docker exec -ti -u root jenkins bash 

Then go to  CONTAINER 

apt update 
apt install rsync
apt install iputils-ping -y 

------=
IN CONTAINER

ssh-keygen
ssh-copy-id root@web-server ip

rsync -av /var/jenkins_home/workspace/pipeline-with-token-container/ root@172.21.74.103:/opt/webroot/

