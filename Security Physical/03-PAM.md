# PAM

Pluggable Authentication Module 

grep -e include -e substack /etc/pam.d/login
grep -e include -e substack /etc/pam.d/sshd


- SSSD = Security System Service Daemon 
- Its like proxy while LDAP, AAA or Kerbos are available


`cat /etc/pam.d/password-auth ` for viewing details for 


`man pam_faildelay` for Manual 


`cat /etc/login.defs`

vi /etc/security/time.conf

sshd|login;*;!root&baz;Al1143-1159 #Allow only specified time 

Deny during that time

sshd|login;*;!root&baz;!Al1143-1159




==================== CHAPTER 06 ===============

- Log
- Event 
- Incident
  

### Setting File System Rule 


`auditctl -w <file> -p <permission> -k <key>` for creating log when permission of a file is modified

`auditctl -w /etc/passwd -p wa -k user-edit` for creating log when permission of a /etc/passwd is modified


 `ausearch -k user-edit` for searching 


`auditctl -w /bin -p x` for creating log when /bin is modified

`auditctl -a exit,always -F arch=32


1.3

auditctl -w /etc/ -p wa -k config-change
tail /var/log/audit/audit.log


touch /etc/sysconfig/testfile
`

## File System 

AIDE = 

### Crontab

minutes hours       day-of-the-month        month       DOW     task 


# For details see man 4 crontabs

# Example of job definition:
|.--------------- minute (0 - 59) <br>
|  .------------- hour (0 - 23) <br>
|  |  .---------- day of month (1 - 31) <br>
|  |  |  .------- month (1 - 12) OR jan,feb,mar,apr <br>
|  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat <br>
|  |  |  |  | <br>
-  -  -  -  - user-name  command to be executed <br>



===========


```shell
[root@ansibleMaster ~]# tail /var/log/audit/audit.log
type=SYSCALL msg=audit(1666689834.381:694): arch=c000003e syscall=44 success=yes exit=60 a0=3 a1=7ffd1f08e8d0 a2=3c a3=0 items=0 ppid=88461 pid=88471 auid=4294967295 uid=0 gid=0 euid=0 suid=0 fsuid=0 egid=0 sgid=0 fsgid=0 tty=(none) ses=4294967295 comm="auditctl" exe="/usr/sbin/auditctl" subj=system_u:system_r:unconfined_service_t:s0 key=(null)ARCH=x86_64 SYSCALL=sendto AUID="unset" UID="root" GID="root" EUID="root" SUID="root" FSUID="root" EGID="root" SGID="root" FSGID="root"
```


---
SALT
Adding some random bits for making two same password iin hash form 


---
**WEBSITE**

https://centralops.net/co/EmailDossier.aspx

https://www.virustotal.com/gui/home/upload

https://www.netcraft.com/
-------------
QUESTION TO BE ASKED 


North - South === Internal 
East - West ==== External 