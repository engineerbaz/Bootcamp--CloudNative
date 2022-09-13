# RHEL

- SHA 512 is being used.


`/etc/security/pwquality` for Password



----


image.png

-----


UGO = User, Group, Others
```
_rw_r__r__. 1 root root 697879 Apr 12 09:22 hello-world.txt 


r=4
w=2
x=1

+,-,= are operations 

`chmod u+x [file]` Give permission of eXecute also to User

`chmod g-w [file]` remove permission of Write to group

`chmod u=r [file]` only Give permission to read to User

`chmod ugo=--- [file]` REmove all permission to User/group/owner



