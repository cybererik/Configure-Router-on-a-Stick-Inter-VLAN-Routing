# Configure-Router-on-a-Stick-Inter-VLAN-Routing

![Lab Screenshot](https://github.com/user-attachments/assets/86fe0479-0e49-4722-80dc-84f61be9a152)


## Lab Overview
- **Lab Purpose:** This lab demonstrates inter-VLAN routing using a single physical router interface (Router-on-a-Stick). It ensures:
Proper VLAN segmentation.
Routing between VLANs.
Correct switch and router configurations.

- **Lab Objective:** Add VLANs to a Switch, Configure Subinterfaces, Test Connectivity with Inter-VLAN Routing
---
## Network Addressing & VLAN setup
![Screenshot 2025-03-26 213636](https://github.com/user-attachments/assets/97d3d720-f6a7-4c41-bb81-2dfd7bd3ef0c)

---

## Router & Switch Configurations
You can view the full CLI configuration for the Cisco router & switch in this [Gist on GitHub](https://gist.github.com/cybererik/4214923b42a61303b291760c5f184c4c).

---

## Why Inter-VLAN Routing is Important?
Inter-VLAN routing is essential because VLANs naturally isolate traffic, meaning devices in different VLANs can’t communicate without a Layer 3 device. Setting up inter-VLAN routing allows controlled communication between VLANs while keeping network segmentation intact for security and efficiency. This improves traffic management, reduces congestion, and helps enforce security policies by regulating how devices interact across VLANs.

![Router show ip int br](https://github.com/user-attachments/assets/fd022aa8-e09d-41f8-87d6-6ce2f116a52b)


---

## Why changing the default VLAN 1 important?
It's a best practice to move traffic off VLAN 1, renaming it to something like "MANAGE." Since VLAN 1 is the default and widely known, it's a common target for attacks. Changing it and disabling VLAN 1 reduces security risks and aligns with security through obscurity. This helps prevent unauthorized access and improves overall network security.

![Switch sh vlan br](https://github.com/user-attachments/assets/d09d3ecc-5ec2-4397-aee9-ed02e0aca620)

---

## ✅ Verification
If PC1 can successfully ping PC3, it confirms that inter-VLAN routing is correctly configured. This means:  

1. **VLANs are properly assigned** – Both PCs are in separate VLANs with correct IP addressing.  
2. **Trunking is working** – The switch is forwarding tagged traffic between VLANs.  
3. **Router-on-a-stick is functioning** – The router is handling VLAN traffic using subinterfaces with the correct encapsulation (dot1Q).  
4. **Routing is enabled** – The router is forwarding packets between VLANs as expected.  

This verifies that inter-VLAN communication is properly set up.
![Verification](https://github.com/user-attachments/assets/7d83b911-b876-4f0d-97a7-82f8c53aeeb0)


---
