# Ansible
A configuration management software by Redhat

------------
### Chef 
- Agent based.
- creates Recipe
- Uses Ruby language
- Client Server model 


### Ansible 
- Introduced in 2012, devloped in Python
- Uses YAML 
- By Redhat
- Agentless
- Push based
- Ansible is opensource
- Ansible Tower is GUI based for Enterprise

## Required for Ansible 
- User with Su doer 
- Package available 
- Keyless (Keygen)



- ASIS
  - Intel Supported
- RSIS 
  - Unix based

Middleware for running application like IIS,nginx, apache,tomcat, Webspare (IBM) and Weblogic (Oracle), it also called as Three tier architecture 

---

## Installation of Ansible

First add user by `useradd ansible ` and set password `passwd ansible` and edit `vi /etc/sudoers` add following lines

`ansible ALL=(ALL) NOPASSWD: ALL`

then generate SSH Key by `ssh-keygen`



[ansible@centos root]$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/ansible/.ssh/id_rsa):
Created directory '/home/ansible/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/ansible/.ssh/id_rsa.
Your public key has been saved in /home/ansible/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:vRang2xmtnYsWoizc4sEivzGRsajSx4rfOOOLv7+iGI ansible@centos.sample
The key's randomart image is:
+---[RSA 2048]----+
|                 |
|                 |
|                 |
|         .       |
|  o     S o .    |
|o. * . o . =     |
|++= = . O.=      |
|*E*Bo+.*ooo.     |
|BOXB=+o+.o       |
+----[SHA256]-----+
[ansible@centos root]$


Add user and set password by 
```
useradd ansible 
passwd ansible
```
Add 
`vi /etc/sudoers`


ansible ALL=(ALL) NOPASSWD: ALL


ssh-keygen






ssh-copy-id ansible@192.168.144.200

ssh-copy-id ansible@192.168.144.201


## Install ansible

Run `sudo yum install wget` 
then run `wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm`

Now do `“ls”` and 

`yum install epel-release-latest- 7.noarch.rpm –y` and `yum update –y `

Now we have to install all the packages one by one

`yum install git python python-level python-pip openssl ansible –y`

Now go to the hosts file inside ansible server and paste private ip of node1 and node2.
`vi  /etc/ansible/hosts`

Now this hosts file is only working after updating ansible.cfg  file
`vi  /etc/ansible/ansible.cfg`

Uncomment these 
```
#inventory=  /etc/ansible/hosts
#sudo-user= root
```


=========


Before making playbooks (mainifest of commands) , we shall make inventory to define target i.e group, node and all. 

**DB** is a group and DB(0) is first one and DB(n-1) is last in list with range can be defined as DB(0:6) for selecting first to seventh entry

- adhoc
  - Single task but dont intimate for repeatation
- module 
  - Single Tasks with intimation
- playbooks
  - Combination of module




[ansible@ip]$ ansible demo -a "ls"
[ansible@ip]$ ansible demo[0] -a "touch filez"
[ansible@ip]$ ansible all -a "touch file4"
[ansible@ip]$ ansible demo -a "ls -al"
[ansible@ip]$ ansible demo -a "sudo yum install httpd -y"
                                   or 
[ansible@ip]$ ansible demo -ba "yum install httpd -y"
[ansible@ip]$ ansible demo -ba "yum remove httpd -y"


Target - Task - Variable 


---

CREDENTIALS
ansible
ansible