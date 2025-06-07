📘 Lab Summary: VTP & DTP – Protocols for Layer 2 Automation

🧠 Purpose:
This lab demonstrates the use of two Cisco Layer 2 automation protocols — VLAN Trunking Protocol (VTP) and Dynamic Trunking Protocol (DTP) — using two distinct scenarios to understand their real-world application, behavior, and security implications.

🔷 Scenario 1: VTP Configuration (Top Topology)
🌐 Objective:
To automate VLAN distribution across multiple switches using VTP within a defined domain.

🛠️ Topology:
ASW1 – VTP Mode: Server
ASW2 – VTP Mode: Transparent
ASW3 – VTP Mode: Client
VTP Domain: Cisco.com
All switches connected via trunk links

🔑 Key Outcomes:
VLANs created on the server (ASW1) are automatically learned by the client (ASW3).
The transparent switch (ASW2) forwards VTP advertisements but does not update its VLAN database.
Demonstrates the centralized VLAN management advantage of VTP.

📷 Visual Diagram:
![image](https://github.com/user-attachments/assets/978ca9da-28b2-4b53-a41a-1ad2e1ceb7d3)

![image](https://github.com/user-attachments/assets/b76038bf-8a66-4468-9152-3cc7368c677f)

![image](https://github.com/user-attachments/assets/9e6d0847-a1eb-477b-920e-c586b4a0aed7)

![image](https://github.com/user-attachments/assets/77a10580-1a55-4b63-8f86-8c5a172a0fee)

🔸 Scenario 2: DTP Configuration (Bottom Topology)

To explore how DTP dynamically negotiates trunking between switches based on port modes.

🛠️ Topology:
SW1 (G0/1) – dynamic desirable
SW2 (G0/1) – dynamic auto
SW2 (G0/2) – trunk (ON)
SW3 (G0/2) – dynamic auto

🔑 Key Outcomes:
Trunk link is successfully formed between desirable and auto (SW1 ↔ SW2).
No trunk forms between two auto modes (SW2 ↔ SW3), demonstrating passive behavior.
Illustrates the importance of explicit trunking or desirable mode for automatic negotiation.

📷 Visual Diagram:

![image](https://github.com/user-attachments/assets/3db630b3-f3fe-4d20-a63a-7fcf33e8f4ee)

![image](https://github.com/user-attachments/assets/de8c0512-94ed-4996-becd-ca04cd0527df)

![image](https://github.com/user-attachments/assets/92c5a90a-5074-4166-bff9-3a81f2a6d15f)


✅ Key Takeaways:
VTP simplifies VLAN propagation but must be handled carefully to avoid accidental VLAN deletions.
DTP eases trunk setup, but it's a security risk if left unconfigured — always disable unused trunk negotiation (switchport nonegotiate).
Real-world engineers often use manual trunking and VTP Transparent mode for better control.


