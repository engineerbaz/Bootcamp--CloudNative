# RHEL
## permission

- SHA 512 is being used.
`/etc/security/pwquality` for Password

UGO = User, Group, Others
```
_rw_r__r__. 1 root root 697879 Apr 12 09:22 hello-world.txt 


r=4
w=2
x=1

+,-,= are operations 

```

`chown [user] [filename]` Change user owner

`chown [user]:[group] [filename]` Change user owner

`chgrp[user] [filename]` Change Group owner

## Change Modify permission

- Symbolic Method 
- Numeric Method

### Symbolic Method

`chmod u+x [file]` Give permission of eXecute also to User

`chmod g-w [file]` remove permission of Write to group

`chmod u=r [file]` only Give permission to read to User

`chmod ugo=--- [file]` REmove all permission to User/group/owner


### Numeric Method
`chmod 777 [file]` Give all permission to UGO 


## umask

By default we create file /directory , default permission is 666/777 respectively 
if no Change in umask 

- Regular User == 0002
- Root user = 0022

so if regular creates a file it's permission will be 666 - 002 = 664
so if regular creates a directory it's permission will be 777 - 002 = 775



## Special Permission

- SUID
  - Only eXecute with owner permission
- SGID
- Pticky


- Symbolic Method
  - SUID = u+s 
  - SGID =  g+s
  - Sticky =  T 

- Numeric
  - SUID = 4
  - SGID = 2
  - Sticky = 1



`chmod g+s [directory] -r` For sticky permission 

sticky means only Owner can delete file 


`chmod +t [directory] -r` For sticky permission 


`chmod 6664 [directory] -r` For sticky permission 

