# Links

- Hard links 
  - Points to an inode
  - Only made for files , not for directory
  - only for same filesystem
  - Usecase
    - 
- Symbolic link 
  - also called Soft link
  - points to a file 
  - make with Absolute path 


- blocks 
  - Location of storing date
- inode 
  - A pointer / Block address number


`ls -li` for checking inode number

## Hard Link 
`ln [Source File] [Destination of link]` for creating link between files

`lsdk`

`stat [file]` for checking status of links 


## Symbolic link 
`ln -s [Source File with Absolute path] [Destination with Absolute path]` for creating Symbolic link 



## SSH Authentication 
- Key based 
- Password based 

`ssh [user]@[ip or name]` 


## User
- Root user has UID is zero (0)
- 1 - 200 Static System
- 201 - 999 System user 
- 1000 - Regular User
  

`id` for checking details of users

`user add`
`usermod -aG [group] [user]` -aG = append group

`passwd` for setting Password

`/etc/passwd` for checking users 

- `/etc/skel/` is available for all users 

`useradd junaid -c "Junaid Ali" -s /sbin/nologin -u 4449 -G wheel`  User junaid with UID 4449 in Wheel group with nologin facility


`/etc/shadow/` for saving Password

## Group
- Group user has UID is zero (0)

`id` for checking details of users

* wheel * has rights like administrator in Red Hat  

`%` shows group 



