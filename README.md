# Day1_Switching-README.md
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
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name Sales_Dept
Switch(config-vlan)# exit
