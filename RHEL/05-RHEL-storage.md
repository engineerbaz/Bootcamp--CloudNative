# STORAGE

Type of storage in Linux
- xfs
- ext4
- ext3
- ext2
- fat 

`findmnt` for showing details on mounts

- LVM 
  - Logical Partition manager 
- SWAP
  - Like Virtual memory 


`free -h` for showing free memory

`/etc/fstab/` for saving permenent entry for mount

- MBR 
  - It has only 4 Partition
  - 3 Primary and 1 Secondary
  - 16 bit memory so can have 2TiB memory 
- GPT
  - Ideally have more space 
  - 8 ZiB memory can be addresses

Now RHEL suggestes to use 

`parted` uses for partitioning and 

`parted/ev/sda` for running partitioning tool



`uevadm settle` for settling disks


