🏠 Home Network Lab (Packet Tracer)

This project simulates a Small Office/Home Office (SOHO) network using Cisco Packet Tracer.  
It demonstrates basic VLAN configuration, router-on-a-stick inter-VLAN routing, and end-to-end connectivity.


📌 Topology
- 1 Router (Cisco 2901)  
- 1 Switch (Cisco 2960)  
- 2 PCs (Staff + Guest) 
 


        [ Router ]
            |
            |
            |
            |
        [ Switch ] 
            /\
           /  \
          /    \
         /      \

      PC1      PC2



⚙️ Configuration Summary

VLANs on the Switch
- VLAN 10 – Staff (PC1)  
- VLAN 20 – Guests (PC2)  

vlan 10
 name STAFF
!
vlan 20
 name GUESTS
!
interface fa0/1
 switchport mode access
 switchport access vlan 10
!
interface fa0/2
 switchport mode access
 switchport access vlan 20
!
interface fa0/3
 switchport mode trunk



Router Configuration

interface g0/0
 no shutdown
!
interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
!
interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0



PC IP Settings
	•	PC1 (Staff, VLAN 10)
	•	IP: 192.168.10.10
	•	Subnet Mask: 255.255.255.0
	•	Default Gateway: 192.168.10.1
	•	PC2 (Guest, VLAN 20)
	•	IP: 192.168.20.10
	•	Subnet Mask: 255.255.255.0
	•	Default Gateway: 192.168.20.1


✅ Verification
	•	Ping Tests
	•	PC1 → 192.168.10.1 (gateway) ✅
	•	PC2 → 192.168.20.1 (gateway) ✅
	•	PC1 ↔ PC2 ✅ (Inter-VLAN routing works)
	•	Screenshots included:
	•	screenshots/topology.png (network diagram)

	•	screenshots/ping.png (successful ping test)

🧑‍💻 Skills Demonstrated
- VLAN creation and assignment
- Access vs. Trunk ports
- Router-on-a-stick inter-VLAN routing
- IP addressing and subnetting
- Basic network troubleshooting (ping, show commands)



🚀 How to Use
1. Open home_network_lab.pkt in Cisco Packet Tracer.
2. View the topology and device configs.
3. Use Command Prompt on the PCs to test pings between devices.

This project is part of my Networking Portfolio