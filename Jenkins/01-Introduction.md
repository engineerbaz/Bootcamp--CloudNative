# Jenkins


sudo apt-get install openssh-server



## Installation 

apt install curl

sudo curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

sudo echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

sudo apt install netcat


netstat -tulpen | grep 8080

nc -zv 192.168.0.110 8080

http://192.168.144.128:8080/

password can be seen from `cat /var/lib/jenkins/secrets/initialAdminPassword`


after opening select **Suggested plugins** options
