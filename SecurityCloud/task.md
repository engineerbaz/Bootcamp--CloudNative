---
- name: Making Partition 
  hosts: all
  become: true
  tasks:
    - name:  Creating Partition 
      parted:
        device: /dev/sdb
        number: 1
        flags: [ lvm ]
        state: present
        part_end: 2GB

    - name: Installing lvm2 dependency
      package:
        name: lvm2
        state: present

    - name: Creating volume group
      lvg:
          vg: bazVG
          pvs: /dev/sdb1
          pesize: 16

    - name: Creating logical volume
      lvol:
          vg: bazVG
          lv:  bazlv
          size: 1g
          force: yes

    - name: Create directory  
      file:
        path: /taskansible
        state: directory
        mode: '0755'

    - name: format the xfs filesystem
      filesystem:
        fstype: xfs
        dev: /dev/bazVG/bazlv

    - name: mount the lv 
      mount:
        path: /taskansible
        src: /dev/bazVG/bazlv
        fstype: xfs
        state: mounted

