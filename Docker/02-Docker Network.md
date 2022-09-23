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
- FS
- Runing processes