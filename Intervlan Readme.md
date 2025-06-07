# 🌐 Inter-VLAN Routing Summary

## 🧠 What is Inter-VLAN Routing?

**Inter-VLAN Routing** is the process of forwarding traffic between different VLANs. By default, devices in separate VLANs **cannot communicate** because VLANs create isolated Layer 2 broadcast domains. To enable communication between them, we need a **Layer 3 device** (like a router or Layer 3 switch).

## 🔧 Methods of Inter-VLAN Routing

### 1. **Router-on-a-Stick (Legacy Method)**
- Uses a single physical interface on a router configured with **subinterfaces**
- Each subinterface is assigned to a VLAN and IP address
- Connected via a **trunk link** to the switch

interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

2. Layer 3 Switch (Modern Method)

Uses Switched Virtual Interfaces (SVIs) for each VLAN Requires ip routing to be enabled More scalable and performance-friendly for enterprises

interface vlan 10
 ip address 192.168.10.1 255.255.255.0

interface vlan 20
 ip address 192.168.20.1 255.255.255.0

ip routing

🧪 Practical Scenario:
VLAN 10: HR Department – 192.168.10.0/24
VLAN 20: IT Department – 192.168.20.0/24
Switch trunked to router or Layer 3 switch
Inter-VLAN routing configured → HR and IT PCs can now communicate

✅ Key Takeaways:

Feature	Description

Layer 2 Switch	Creates VLANs but cannot route between them
Layer 3 Device	Enables communication between VLANs
Subinterfaces	Used with Router-on-a-Stick for multiple VLANs
SVIs	Used on L3 switches for direct VLAN interfaces
ip routing	Must be enabled on L3 switch to route between VLANs

🔍 Verification Commands
show vlan brief
show ip interface brief
show running-config
ping [destination IP]

For Practial I added Packet tracer file for Intervlan Routing go check it file name Intervlan Rounting(Roas)

Inter-VLAN routing is a crucial skill for any Network Engineer. Whether you're preparing for CCNA or deploying in a live network, understanding how VLANs communicate at Layer 3 is key to building functional, secure, and scalable infrastructures.

Here are some visuals from the lab.
![image](https://github.com/user-attachments/assets/af31185d-3e0d-441b-8bf3-d89cd5d202c1)
![image](https://github.com/user-attachments/assets/bfc35c5e-848e-4a3e-b176-3ec00b192f39)
![image](https://github.com/user-attachments/assets/d894e0fb-f636-427f-95a6-cb3b09baaada)
![image](https://github.com/user-attachments/assets/f6b6b728-8b89-4f4a-945e-f8a774a35b19)
![image](https://github.com/user-attachments/assets/807af078-2f6a-40e1-9543-27aa30c5b65f)
