# SELinux
- Secure Enhanced Linux
- Acknowledged by DoD
- 

If we change parameter from standards , then need to inform SELinux as well 

`semanage `

- Move caries same context label of source 
- copy makes same context label as of destination


`semanage fcontext -a -t http_sys_content_t /var/www/html/date.txt`

`ls -lZ` List all files with context 

`restorecon -vRF /file` to refereshing   

`semanage permissive -a httpd_t` only making permissive for http
`semanage -l` for showing list


`semanage user -l` listing users of SELinux 

Mapping of user to SELinux user 




=============

setsebool -P user_exec_content off

semanage login -m -s user_u -r s0 __default__

===================


## Scanning Tool

Scanning tool for 
- OpenSCAP
- Nessus

OpenSCAP = Security Content Automation 
- SCAP Benmark = GUI    

SSG = Security Compilance Guide is predefined collection

==========

For enhancing security we can have a password on GRUB Loader as well. 
