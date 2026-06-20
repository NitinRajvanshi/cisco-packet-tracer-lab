# Access Control List (ACL) Demonstration

## Overview

This Cisco Packet Tracer lab demonstrates how Access Control Lists (ACLs) can be used to control network traffic and enforce security policies on routers.

## Objective

- Verify network connectivity.
- Examine an existing ACL.
- Observe how ACLs filter ICMP traffic.
- Remove ACL restrictions.
- Verify restored connectivity.

---

## Tools Used

- Cisco Packet Tracer
- Cisco Routers
- Cisco Switches
- End Devices (PCs)
- DNS Server

---

## Network Topology

Networks Used:

- 192.168.10.0/24
- 192.168.11.0/24
- 192.168.30.0/24
- 192.168.31.0/24
---

## Part 1: Connectivity Verification

### Successful Pings

PC1 successfully communicated with:

- PC2 (192.168.10.11)
- PC3 (192.168.11.10)

### Failed Pings

PC1 could not communicate with:

- PC4 (192.168.30.12)
- DNS Server (192.168.31.12)

Error:

```text
Destination host unreachable
```

---

## Part 2: ACL Analysis

### Existing ACL

```text
Standard IP access list 11
10 deny 192.168.10.0 0.0.0.255
20 permit any
```

### Purpose

The ACL denied traffic originating from the 192.168.10.0/24 network while allowing all other traffic.

---

## Part 3: ACL Removal

### Commands Used

```bash
enable
configure terminal
interface serial0/0/0
no ip access-group 11 out
exit
no access-list 11
end
```

---

## Verification

After removing ACL 11:

- PC1 successfully reached PC4.
- Network communication was restored.

---

## Security Concepts Learned

- Standard ACLs
- Traffic Filtering
- Router Security
- Access Control Policies
- ICMP Filtering

---

## Skills Demonstrated

- Cisco IOS Configuration
- ACL Analysis
- Network Troubleshooting
- Connectivity Testing
- Router Administration

---
## Screenshots 
01_network_topology
<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/43f7712a-6fd8-4173-b643-b17bc541f3f3" />

02_local_connectivity_success
<img width="940" height="949" alt="image" src="https://github.com/user-attachments/assets/950fd352-68bf-4091-a53a-91c9e190c169" />

03_acl_blocks_remote_access
<img width="940" height="423" alt="image" src="https://github.com/user-attachments/assets/b4367ce0-7831-478c-89c7-398150f45ec2" />

04_acl_verification_show_access_list
<img width="940" height="966" alt="image" src="https://github.com/user-attachments/assets/706f17c4-23ad-45ba-9cb0-1de97a5099ba" />

05_acl_removal_interface_command
<img width="940" height="423" alt="image" src="https://github.com/user-attachments/assets/a9367321-8084-4637-961f-94ce001ed779" />

06_acl_deletion_command
<img width="940" height="146" alt="image" src="https://github.com/user-attachments/assets/f3846de0-6083-435b-8aa7-18c1b4de78d8" />

07_connectivity_restored_after_acl_removal
<img width="940" height="311" alt="image" src="https://github.com/user-attachments/assets/4753064e-b7e8-46e9-aab0-273b2b11c0ae" />


## Learning Outcome

This lab demonstrated how Access Control Lists (ACLs) can restrict traffic between networks and how removing ACL rules restores communication. ACLs are a fundamental network security mechanism used to control and protect network resources.
