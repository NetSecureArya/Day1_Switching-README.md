# Day1_Switching
# VLANs: Virtualizing Your Network for Efficiency and Security

## 📘 What is a VLAN?

A **VLAN (Virtual Local Area Network)** is a Layer 2 technology used to logically segment a switch into multiple independent networks. Devices within the same VLAN can communicate as if they were on the same switch—even if physically separated—while being isolated from devices in other VLANs.

### 🔍 Why VLANs Are Essential:
- ✅ **Improved Performance**: Reduces broadcast traffic.
- 🔒 **Enhanced Security**: Isolates traffic between groups.
- 🧠 **Simplified Management**: Logical grouping, easier MACs.
- 💰 **Cost Efficient**: Reduces need for extra switches.
- 📈 **Scalable**: Easily expand network logically.
- 🛠️ **Troubleshooting Made Easier**: Smaller segments.

---

## 🔑 Types of VLANs

| VLAN Type          | Purpose                                                                 |
|--------------------|-------------------------------------------------------------------------|
| **Data VLAN**       | Carries user-generated traffic (e.g., PCs, printers).                  |
| **Voice VLAN**      | Used for VoIP traffic with QoS prioritization.                         |
| **Management VLAN** | For remote management (e.g., VLAN 99 with SVI).                        |
| **Native VLAN**     | Untagged VLAN on trunk links (must match on both sides).               |
| **Black Hole VLAN** | Assign unused ports to this VLAN to prevent unauthorized access.       |

---

## ⚙️ Cisco IOS Configuration Commands

### 1. 🎯 **Creating a VLAN**

Switch(config)# vlan 10
Switch(config-vlan)# name Sales_Dept
Switch(config-vlan)# exit


2. 🔗 Assigning Access Ports

Switch(config)# interface Gi0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
Switch(config-if)# spanning-tree portfast
Switch(config-if)# description PC_Sales_UserA
Switch(config-if)# exit

3. 🌐 Configuring Trunk Ports

Switch(config)# interface Gi0/24
Switch(config-if)# switchport trunk encapsulation dot1q
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20,30
Switch(config-if)# switchport trunk native vlan 100
Switch(config-if)# description Uplink_to_Core_Switch
Switch(config-if)# end

4. 🛡️ Management VLAN (SVI)

Switch(config)# interface vlan 99
Switch(config-if)# ip address 192.168.99.10 255.255.255.0
Switch(config-if)# no shutdown

🔍 Show Commands for Verification
Command	Purpose
show vlan brief	Displays all VLANs and assigned ports.
show interfaces trunk	Shows trunk ports and allowed VLANs.
show interface Gi0/1 switchport	Detailed port configuration.
show interface vlan 99	SVI status and IP address.
`show running-config	section vlan`
copy running-config startup-config	Save your config!

🧠 Summary
VLANs are a fundamental part of modern networking, offering security, segmentation, and performance gains. Proper configuration—including trunking, native VLANs, and port roles—is essential for scalable, enterprise-ready networks.






