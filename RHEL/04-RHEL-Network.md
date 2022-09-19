# RHEL
`ip link` show link details 

`ip link -s` show link details 


`ip addr` shows IP address details 


`ping6 ::` ping ipv6 address

`ip route` routing table 


`/etc/sysconfig/network-scripts`
`/etc/resolve.conf/`


`ifcfg` in  `/etc/sysconfig/network-scripts`


`nmcli`

## Assignment 
sudo -i vs su - 


---
NETWORK 
------

`/etc/sysconfig/network-scripts/` for all available nw 


`ip link show` or `nmcli device status` to view devices


`nmcli connection add con-name VMNET06 connection.autoconnect yes ipv4.method auto ifname ens160 type ethernet` for configuring network profile 

`less /etc/sysconfig/network-scripts/ifcfg-VMNET06` to view configuration of network

`nmcli connection modify VMNET06 ipv4.method manual ipv4.addresses 10.20.10.0/24 ipv4.dns "10.20.0.1,8.8.8.8" ipv4.gateway 10.20.10.1` for modify ip network settings 

`nmcli connection down VMNET06 && nmcli connection up VMNET06` Refresh network settings
or `nmcli connection reload` 


add duplicate IPs 


`nmcli device show ens160`

## NMTUI


===

## REPO

- Local Repos
- Always have extension `.repo`

`lsblk` shows list of devices 

`mount /ev/Sr0 /DVD`


```
[Base-OS]
name=base-os 
baseurl=file:///DVD/BaseOS/
enabled=1
gpgcheck=0

[AppStream]
name=App-Stream 
baseurl=file:///DVD/AppStream/
enabled=1
gpgcheck=0

```
`yum repolist`

`repo.d`


===
`subscription-manager subscribe` 


==

## Repo Group 
