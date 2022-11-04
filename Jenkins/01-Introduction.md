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



=====


Project or Task 


- Build 
  - One run of project 
- Build Step
  - A task inside a projetc 
- Build Trigger
  - Criteria for starting a build 
  - Manual or auto

plugins = A software package that extends Jenkins' core functionality


Jenkins is web-based application , can run on laptop or server (256MB RAM & 1GB HDD) with Java 11 JRE /JDK, if containerization 1Gb RAM & 10GB storage





















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





- CLASSES WILL BEGIN ON 11 NOVEMBER 2022
Fridays at 2100 PKT (UTC+5), the schedule will be discussed.
- COURSE DURATION: Roughly four months (16 to 18 weeks) depending on trainer availability.

- AUDIENCE: Professionals, as this is a specialized class with a small number of participants.
- CLASS WILL BEGIN IF 60% OF THE AUDIENCE IS PRESENT (Trainers/Students).
- Lesson STRUCTURE: Total one-and-a-half-hour class beginning with a brief review and problem-solving (if any)
- STUDY TIME: One-and-a-half-hour online class and at least two hours for homework/practice and independent study.
- COURSE OUTLINE: Shared previously; Just to summarize Linux, Git, Docker, Kubernetes, Jenkins, and Ansible with GitHub; Also, real-world applications.
- SILENT FEATURES:
- Online class with limited enrollment for individualized instruction.
- LMS Session for review and study - Video recordings
- Assignments and tasks for continuous learning - WhatsApp Group for questions and concerns
- RECOMMENDATIONS: - Attendance of at least 85 percent is required to provide optimal benefit.
- Inform the instructor before to class if you will be absent.