# Cloud Security

There is no patch for human stupidity
ROE - Rule of Engagement

NIST cloud Stake holder
1. Cloud consumer
2. Cloud provider
3. Cloud carrier
4. Cloud auditor
5. Cloud broker

Core Security Objects

1. Data Security
2. Compliance
3. Cost
4. Scalability


# Cloud Security Issues 


What is Vendor Lock-In in Cloud Computing? 
Vendor lock-in is the common term for a situation where an organization wishes to transfer its business away from one of its current vendors but is unable to do so due to the projected cost, duration, or complexity of switching.

CIA = Confidential Integrity and Availibility

## Security Categories
1. Security Issues faced by cloud providers
2. Security Issues faced bu cloud consumers

## Security Methods
1. Security Issues in SaaS
2. Security Issues in PaaS
3. Security Issues in IaaS

## Security Deminsions
1. Security Vulnerabilities
2. Security Risk
3. Security Threats

### owasp for security risks in cloud

Penetration testing
Performance Assessment Network (PAN) Testing

https://owasp.org/

---

Kavin Mitnick 
War games


---


| 0.0.0.0 ~ 0.255.255.255 | IPv4 Stack |
| 1.0.0.0 ~ 126.255.255.255 | Class A |
| 127.0.0.0 ~ 127.255.255.255 | Loopback |
| 128.0.0.0 ~ 169.253.255.255 | Class B |
| 169.254. 0.0 to 169.254.255.255  | APIPA  |
| 169.255.0.0 ~ 191.255.255.255 | Class B continued|
| 192.0.0.0 ~ 223.255.255.255 | Class C |
| 224.0.0.0 ~ 238.255.255.255 | Class D Multicast|
| 239.0.0.0 ~ 255.255.255.254 | Class E Expperimental|
| 255.255.255.255 | Broadcast|



APIPA = Automatic Private IP Addressing) The Windows function that provides DHCP autoconfiguration addressing. 



**Class A | 0.0.0.0 ~ 126.255.255.255 | **
- 0.0.0.0 ~ 0.255.255.255 IPv4 Stack 
- 0.0.0.0 as a default route address, meaning any network.
- 10.0.0.0 ~ 10.255.255.255 for Private-Use
- 127.0.0.0 ~ 127.255.255.255 for Loopback 
- 127.0.0.1 (that is only for local machine)

**Class B | 128.0.0.0 ~ 191.255.255.255 | **
- 169.254. 0.0 ~ 169.254.255.255  for  APIPA (for LinkLocal)  
- 172.16.0.0 ~ 172.31. 255.255	Private-Use


**Class C | 192.0.0.0 ~ 223.255.255.255 | **
- 192.168.0.0 ~ 192.168.255.255 for Private Use 


**Class D | 224.0.0.0 ~ 238.255.255.255 | Class D Multicast|

Class E| 239.0.0.0 ~ 255.255.255.254 | Class E Expperimental|**
- 255.255.255.255 | Broadcast|


====


- VPC
- Internet Gateway
  - associate with VPC 
- Subent 01
- Subent 02
- Route Table (public)
  - Edit route (0.0.0.0 --> IGW)
  - Subnet associate (public)
- Route Table (private)
  - Edit route (0.0.0.0 --> NAT GW)
  - Subnet associate (private)

