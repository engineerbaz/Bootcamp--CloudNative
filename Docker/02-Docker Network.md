# Network

## Network Driver
- Bridge
- Host
- Overlay 
- IP VLAN
- MAC VLAN

By defualt, Bridge is driver and its docker0 

### Host Driver
- Two main tasks by Driver  



- Overlay 
  - Encryption is optional


- IP VLAN
  - Every member gets seprate MAC 
- MAC VLAN
  - Every member gets same MAC 


++ LAB 

`docker network create --subnet 192.168.3.0/24 z-net`


`systemctl start docker` to start 
`systemctl enable docker` to enable by making 



`docker run -ti --network z-net travelping/nettools bash`

`docker run -ti --hostname c1.docker.lab travelping/nettools bash`


## Namespace isolation 
- User 
- network
- File system
- Runing processes



`docker network create --driver ipvlan --subnet 192.168.144.0/24 --gateway 192.168.144.2 --ip-range 192.168.144.128/25 -o ipvlan_mode=l2 -o parent=ens33 external_ipvlan`

`docker run -d --network external_ipvlan --name cont-ipvlan httpd`


`docker network create --driver macvlan --subnet 192.168.144.0/24 --gateway 192.168.144.2 --ip-range 192.168.144.120/29  -o parent=ens33 external_macvlan`


`nmcli con mod ens33 connection.autoconnect yes ipv4.method manual ipv4.addresses 192.168.144.131/24 ipv4.gateway 192.168.144.2 ipv4.dns 8.8.8.8` 
`nmcli con down ens33` || `nmcli con up ens33` 


====



## DNS Record
- A Record ( For IPv4 Domain Name )
- CNAME (Colonical Name, Like Alias) Pointed domain 
- PTR (Reverse )
- NS (Name Server)
- AAAA (IPv6)
- SOA (Start of Authority)



