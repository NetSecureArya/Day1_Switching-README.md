## 🧪 Lab: Basic VLAN Configuration in Cisco Packet Tracer

### 🔍 Objective:
To demonstrate a simple VLAN configuration on a Cisco switch, where two PCs are assigned to two different VLANs (VLAN 10 and VLAN 20) using access ports. This lab showcases how VLANs segment broadcast domains and isolate traffic between devices.
This is Basic Switching Lab In this Lab you we will be learn about how vlan create and how to assing in switchport.
---
### 🧱 Topology Overview:
- **4 PCs** (PC1,PC2,PC3,PC4)
- **1 Cisco Switch**
- **VLAN 10**: Assigned to PC1,PC2
- **VLAN 20**: Assigned to PC3,PC4
---
### ⚙️ Key Configurations:
- Created VLAN 10 and VLAN 20
- Assigned ports Fa0/1,FO/2 and Fa0/3,F0/4 to VLANs
- Configured access mode on switch ports
- Verified VLAN assignments using `show vlan brief`
---
### 💻 Commands Used:

Switch(config)# vlan 10
Switch(config-vlan)# name HR
Switch(config)# vlan 20
Switch(config-vlan)# name IT

Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

Switch(config)# interface fa0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

Switch(config)# interface fa0/3
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20

Switch(config)# interface fa0/4
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20


![image](https://github.com/user-attachments/assets/65394580-142d-4410-9088-3f4e364f73ca)
![image](https://github.com/user-attachments/assets/43eea61f-b411-47e8-b661-40d049bba8c4)

📌 Purpose: This lab helps you understand VLAN basics, switchport modes, and traffic separation in a local network — core concepts for both CCNA certification and real-world switching environments.

