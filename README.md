# ITI-CCNA-Project

## Overview

This project was created using **Cisco Packet Tracer** to simulate an enterprise network.
It demonstrates several core **CCNA networking concepts** including VLAN configuration, DHCP, dynamic routing using EIGRP, SSH access, Radius authentication, and network security using ACLs.

---

## Network Topology

The network includes:

* 3 Routers
* 4 Switches
* Multiple End Devices
* DNS Server
* Web Server
* Mail Server
* Radius Server

The goal of this topology is to simulate a segmented enterprise network with routing between VLANs and secure access control.

---

## Basic Configuration

The following configurations were applied to all routers and switches:

* Hostnames configured for all devices.
* Domain name set to `ITI.com`.
* Console and VTY passwords configured.
* Password encryption enabled using `service password-encryption`.
* Local user configured for authentication.
* SSH enabled for secure remote access.

Example:

* Hostname configuration
* Domain configuration
* SSH login via VTY lines

---

## VLAN Configuration

### Switch 1

* VLAN 10 → Fa0/1, Fa0/2, Fa0/3
* VLAN 20 → Fa0/4, Fa0/5, Fa0/6
* VLAN 30 → Gi0/1

### Switch 2

* VLAN 40 → Fa0/1, Fa0/2, Fa0/3
* VLAN 50 → Fa0/4, Fa0/5, Fa0/6
* VLAN 60 → Gi0/1

Rapid Spanning Tree Protocol (**RSTP**) was configured on switches for faster convergence.

---

## DHCP Configuration

DHCP was configured on the router to distribute IP addresses dynamically to end devices.

All networks use subnet mask **255.255.255.0 (/24)**.

| VLAN        | Network       | Default Gateway |
| ----------- | ------------- | --------------- |
| VLAN 10     | 192.168.x.0   | 192.168.x.1     |
| VLAN 20     | 192.168.x+1.0 | 192.168.x+1.1   |
| VLAN 30     | 192.168.x+2.0 | 192.168.x+2.1   |
| VLAN 40     | 192.168.x+3.0 | 192.168.x+3.1   |
| VLAN 50     | 192.168.x+4.0 | 192.168.x+4.1   |
| VLAN 60     | 192.168.x+5.0 | 192.168.x+5.1   |
| SW4 Network | 10.10.50.0    | 10.10.50.1      |

DNS Server: **192.168.7.10**

---

## Routing Configuration

Dynamic routing was configured using **EIGRP** between the three routers.

Features implemented:

* Router-to-router communication
* Route advertisement between networks
* Serial connections between routers
* Default routing configuration

---

## Security Configuration

### Radius Authentication

A **Radius Server** was added to provide centralized authentication for network access.

### Access Control Lists (ACL)

The following access restrictions were configured:

* Host **192.168.x.2** is denied access to **DNS services**.
* Network **192.168.x+2.0/24** is denied access to the **Web Server**.
* **VLAN 10** is denied access to the **Mail Server**.

---

## Technologies Used

* VLAN
* Rapid Spanning Tree Protocol (RSTP)
* DHCP
* EIGRP Routing
* SSH
* Radius Authentication
* Access Control Lists (ACL)

---

## Project File

The project file included in this repository:

`project.pkt`

Open it using **Cisco Packet Tracer**.

---

## Author

Mai Wael
System Administrator Trainee at ITI
