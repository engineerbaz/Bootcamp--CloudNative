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
