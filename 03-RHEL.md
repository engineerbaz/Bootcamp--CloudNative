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




`chmod u+x [file]` Give permission of eXecute also to User

`chmod g-w [file]` remove permission of Write to group

`chmod u=r [file]` only Give permission to read to User

`chmod ugo=--- [file]` REmove all permission to User/group/owner





## umask


`chmod g+s [directory] -r` For sticky permission 

sticky means only Owner can delete file 
