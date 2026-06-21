# DHCP, DNS & Web Server Integration Lab using Cisco Packet Tracer

## Overview

This project demonstrates the implementation of Dynamic Host Configuration Protocol (DHCP), Domain Name System (DNS), and HTTP Web Server services in Cisco Packet Tracer. The lab simulates a small enterprise network where a Cisco Router acts as a DHCP Server, while a dedicated server provides DNS and Web services.

The objective is to understand automatic IP address allocation, hostname resolution, inter-network routing, and web service accessibility.

---

## Technologies Used

* Cisco Packet Tracer
* Cisco 2901 Router
* Cisco 2960 Switch
* DHCP
* DNS
* HTTP Web Server
* IPv4 Addressing
* Static Routing Between Networks

---

## IP Addressing Scheme

### Client Network

| Device | Interface | IP Address      |
| ------ | --------- | --------------- |
| Router | G0/0      | 192.168.10.1/24 |
| PC0    | DHCP      | 192.168.10.x    |
| PC1    | DHCP      | 192.168.10.x    |

Network ID:

```text
192.168.10.0/24
```

Broadcast Address:

```text
192.168.10.255
```

---

### Server Network

| Device | Interface | IP Address        |
| ------ | --------- | ----------------- |
| Router | G0/1      | 192.168.20.1/24   |
| Server | Fa0       | 192.168.20.100/24 |

Network ID:

```text
192.168.20.0/24
```

Broadcast Address:

```text
192.168.20.255
```

---

## DHCP Configuration

Router configured as DHCP Server.

### DHCP Pool

```text
Pool Name: VLAN10
Network: 192.168.10.0/24
Default Gateway: 192.168.10.1
DNS Server: 192.168.20.100
```

### Excluded Addresses

```text
192.168.10.1
192.168.20.1
192.168.20.100
```

---

## DNS Server Configuration

DNS Service enabled on Server.

### DNS Record

```text
www.veltech.in → 192.168.20.100
```

Purpose:

* Hostname Resolution
* Domain-to-IP Mapping

---

## Web Server Configuration

HTTP Service enabled on Server.

Users can access the website using:

```text
http://www.veltech.in
```

or

```text
http://192.168.20.100
```

---

## Verification Performed

### DHCP Verification

```bash
ipconfig /renew
ipconfig /all
```

Verified:

* IP Address Assignment
* Subnet Mask
* Default Gateway
* DNS Server Information

---

### DNS Verification

```bash
ping www.veltech.in
nslookup www.veltech.in
```

Verified:

* Successful Name Resolution
* DNS Record Mapping

---

### Connectivity Verification

```bash
ping 192.168.10.1
ping 192.168.20.100
```

Verified:

* Inter-network Communication
* Router Connectivity

---

### HTTP Verification

Opened Web Browser:

```text
http://www.veltech.in
```

Verified successful webpage loading through DNS resolution.

---

## Concepts Practiced

* IPv4 Addressing
* Subnetting
* DHCP Configuration
* DHCP Address Exclusion
* DNS Configuration
* DNS Name Resolution
* HTTP Server Configuration
* Inter-network Routing
* Default Gateway Operation
* ARP Resolution
* Troubleshooting DHCP Issues
* Troubleshooting DNS Issues

---

## Learning Outcomes

After completing this lab, I gained practical experience in:

* Configuring a Cisco Router as a DHCP Server
* Deploying DNS and HTTP services
* Understanding the DHCP DORA Process
* Implementing Hostname-to-IP Resolution
* Verifying Network Connectivity using Cisco Troubleshooting Commands
* Understanding Communication Between Multiple IP Networks

---

## Author

**Gokulakannan V**
B.Tech Computer Science & Engineering
Vel Tech Rangarajan Dr. Sagunthala R&D Institute of Science and Technology

**Cisco CCNA Learning Lab Series**
