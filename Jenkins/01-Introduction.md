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


--

WORKER NODE 

























---


- START DATE: Classes to be started from November 11th, 2022
- TIMING : Schedule disucssed as 2100 PKT (UTC+5) on Fridays.
- COURSE DURATION : Approx 4 months (16 weeks - 18 weeks ) as per availability of trainer.
- AUDIENCE: Professioanls as its a dedicated Class with minimum number of participatents 
- COMMENCEMNET: Class will be commenced if 60% audience availble (Trainer / Students) 
- CLASS STRUCTURE: Total One & half hour class starting with quick review & issue resolution (if any)
- STUDY TIME:  One & half hour Online Class & atlest 2 Hours for assignment/practice & self study.   
- COURSE OUTLINE: Shared already, Just to sum up Linux, Git, Docker, Kubernetes, Jenkins and Ansible with GitHub, Also real world projects.
- SILENT FEATURES:
  - Dedicated Online class with minimum participatents for dedicated attention
  - LMS Session for learning and review
  - Video recordings
  - Assignments/Tasks for continous learning
  - WhatsApp Group for queries and questions 
- GUIDELINES:
  - 85% attendance is madontory so maximum benefit can availabled.
  - Please inform prior to class if not going to attend class 
  - 