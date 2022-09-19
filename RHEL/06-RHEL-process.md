# RHEL 

## Firewall

`firewall-cmd --add-port=443/tcp` add rules in firewall 
`firewall-cmd --list-all` 

`firewall-cmd --list-all-zone

`firewall-cmd --reload` ` 

===============

# SELinux

- Security Feature
- Security Enhanced Linux
- SELinux protect resources 


`/tmp` flushes in 30 days and it is available for all user

`/var/tmp` flushes in 10 days


`getenforce` check status of SELinux , if working it will show *enforcing* & in *permissive* mode it will allow but logs being made.

`setenforce` for setting mode to *enforcing* or *permissive* mode

`/etc/selinux/config`  for making changes permenent

`ls -lZ` for showing ls with context label

`semanage fcontext -a -t httpd_sys_rw_t "(/var/www/hml/.*)?"` for changing

`restorecon -Rv [folder]` add record 

=====


`/var/log/messages`
`/var/log/secure`
`dmessage` for System /root related messages


`journalctl --since today` 

`/etc/systemctl/journal.conf` 

====

# Break Root Password 

First Boot Linux, when Grub screen comes, select Latest Kernel 
press *e* and move to end of lines (before $ ) and write rd.break and press *CTRL+X* 
write *mount* on screen and see hard disk partition (rhel-boot) [here its showing read only]

write `mount -o rw,remount /sysroot` press *enter*
write mount again to see status
Write `chroot /sysroot/` and `ls -l`
write `echo "password" | passwd --stdin root` 
write `touch /.autorelabel` 


=============


# LVM

- Physical Volume 
- Virtual Group
- Logical Volume  
 
`set 1 lvm on `


`pvcreate /dev/sda1`
`pvs`

`vgcreatw data /dev/sda1`

`vgs`
`vgdisplay data`

`lvcreate -n project -L 5 GiB`



