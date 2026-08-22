# Basic-networking-Lab
# Inter-VLAN Routing (Router-on-a-Stick) Lab
Basic network topology with switches and routers using Cisco Packet Tracer. Day-01 Topology is Virtual-LAN and router-on-a Stick.
## 📌 Project Overview
This lab demonstrates the implementation of **Virtual LANs (VLANs)** and **Inter-VLAN Routing** using the **Router-on-a-Stick (ROAS)** configuration in Cisco Packet Tracer. The objective is to isolate local traffic within distinct broadcast domains while enabling secure communication across subnets via sub-interfaces on a Cisco Router.

---

## 🛠️ Network Architecture & Components
* **Routing Device:** Cisco 2811 Integrated Services Router (ISR)
* **Switching Layer:** Cisco Catalyst 2950-24 Switches
* **End Devices:** Generic PCs (PC0 - PC5)
* **Simulation Tool:** Cisco Packet Tracer

---

## 🗺️ Topology Diagram
Basic_Topology_Diagram.png

---

## ⚙️ Key Configuration Highlights

### 1. Switch Configuration (VLANs & 802.1Q Trunking)
```cisco
Switch(config)# vlan 10
Switch(config-vlan)# name Sales
Switch(config)# vlan 20
Switch(config-vlan)# name IT
Switch(config)# interface FastEthernet0/1
Switch(config-if)# switchport mode trunk
Router(config)# interface FastEthernet0/0.10
Router(config-subif)# encapsulation dot1Q 10
Router(config-subif)# ip address 192.168.10.1 255.255.255.0

Router(config)# interface FastEthernet0/0.20
Router(config-subif)# encapsulation dot1Q 20
Router(config-subif)# ip address 192.168.20.1 255.255.255.0

