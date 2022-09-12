# Red Hat Enterprise Linux

Linux is extension-free and case sensitive

## User
- Normal
- Super 
- System



## Path
Absolute
-  /root/home/Desktop 

Relative
- home/Desktop

## Commands 

` cd ..`
For taking one step back

` cd `
Takes you to home

` cd - `
Takes you to last location from we have chaged


### History Commands

`history ` To see last executed commands

for example

```
1 histoy
2 cd
3 cd -
```

you may run last executed commands by pressing `![number]` 

# File System



`CRTL + ALT + (F1 ~ F6)` 

`CRTL + ALT + F1` For Login user
`CRTL + ALT + F2` For Desktop
`CRTL + ALT + F3` For CLI

also you can change by command ` chvt [number of vty]` like `chvt 3`


## Vi 
Two modes
- Command (By default) --> by pressing ` i,a,o`
- Edit/Insert --> ESC mode 


## Useful Commands

#### Grep
For searching data (string) in a file.
`grep "[word]" [file location]`


`grep -i "[word]" [file location]` for ignoring case


### Diff
For finding difference 

### File
`file [file name]` for checking file type/content


### Tail 
`tail [file]` to show last 10 lines
`tail -n [number of row] abc.txt` 

### Head
`head [file]` to show top 10 lines
`head -n [number of row] abc.txt` 


### Find 
`find [location] -type -size -name`
`find /etc/ -type f -size 100c` shows files of size under 100 bytes


## CALENDAR

`cal`
`cal -y 2022`

## Date 

## Joining Commands

`mkdir test && cd mkdir` run first command than do second command if first completed.
` mkdir hi; date` run first command than do second  



## service

Daemon

`systemctl restart sshd` restarting SSH Daemon (sshd)

* Generate Keygen
`ssh-keygen` 
pasphrase for enctyption

* filename.pub is Public Key
* id_rsa for Private Key

`ssh-copy-id [remoteuser]@[remoteID]` copy your public key to remote machine so next time Authentication/authorization can be done easily

`-i` is used for making unique public key for services with pasphrase



# Extra

* Nagivation within document/file 

*/* is for moving downward
*?* for going upward

- y for Copy
- yy for copying line
- v for visual (selection)
- p for paste
- u for undo
- CTRL + r for redo
- dG
- GG

`%s/{Replace word}/{To be replaced}

`%s%/{Replace word}/{To be replaced}/g -- for all occurences



`echo "[TEXT]" > File name` redirection for adding in text file

`echo "[TEXT]" >> File name` redirection for adding in text file


`du -sh [location]` Director Usuage 


`head -n 5 [file] | tail -n 1` Shows only 5th line 

`less [filename]` to display content of file 


`which [file]` tells location of file 


`touch file{1...6}.txt` Create 6 files i.e file1.txt and file2.txt 



## Vimtutor 
For tutorial for learning


  

## Man - Manual 
` man [command]` for learning about command  
 

