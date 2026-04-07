VLAN-based segmentation
# 🏘 Multi-ISP Residential Network Design

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Simulation](https://img.shields.io/badge/Cisco-Packet_Tracer-1ba0d7)
![Networking](https://img.shields.io/badge/Networking-Multi--ISP-blue)

![Network Topology](./https://github.com/eshaan007-tech/multi-isp-residential-network/blob/main/ISP%20Topology.png)

---

## 📑 Contents

- [What this project is about](#-what-this-project-is-about)
- [Technologies used](#-technologies-used)
- [Process](#-process)
- [What I learned](#-what-i-learned)
- [How it can be improved](#-how-it-can-be-improved)
- [How to run the project](#-how-to-run-the-project)
- [Repository structure](#-repository-structure)

---

## 📖 What this project is about

A simulation of a real-world residential neighborhood network with **multiple ISPs**, **VLAN-based segmentation**, and **dual-ISP redundancy** for high availability. Built in Cisco Packet Tracer.

The design includes 3 ISP junctions (two ACT, one Airtel), 10 houses with isolated LANs, and one house (House 6) connected to two different ISPs for redundancy modeling.

✅ **Verified:** PC in House 1 can ping PC in House 4 across WAN.

---

## 🛠 Technologies used

- Cisco Packet Tracer
- Static WAN routing
- VLAN (access ports, multilayer switching)
- DHCP (IPv4 pools)
- WPA2-PSK wireless security
- IP subnetting (VLSM)
- Default gateway design

---

## ⚙️ Process

1. **Planned IP addressing**  
   - WAN: `10.1.0.0/24` (ACT1), `10.2.0.0/24` (Airtel), `10.3.0.0/24` (ACT2)  
   - LAN: Each house gets a unique private `/24` (`192.168.x.0/24`)

2. **Configured ISP junctions**  
   - Multilayer switches with VLANs per house  
   - Access ports assigned to residential routers

3. **Set up WAN on each house router**  
   - Static IP on WAN interface (e.g., `10.1.0.10/24`, gateway `10.1.0.1`)

4. **Configured LAN + DHCP on each house router**  
   - Router LAN IP = `.1` of its `/24` subnet  
   - DHCP pool: `.100 – .149`

5. **Added wireless**  
   - Unique SSID per house, WPA2-PSK, DHCP enabled

6. **Dual ISP for House 6**  
   - Two routers: Airtel (WAN `10.2.0.6`, LAN `192.168.110.1`) and ACT (WAN `10.3.0.6`, LAN `192.168.111.1`)

7. **Verified connectivity**  
   - ICMP tests between LAN devices and across WAN

---

## 📚 What I learned

- How to separate LAN and WAN with static routing
- VLAN-based subscriber isolation in a multi-ISP setup
- Designing DHCP scopes without overlap
- Modeling residential dual-provider redundancy
- Real-world IP planning constraints (private vs public, gateway selection)

---

## 🔧 How it can be improved

- Add **dynamic routing** (OSPF) between ISP junctions
- Implement **NAT overload** on house routers for internet access simulation
- Add **redundant links** with failover detection
- Include **syslog server** for centralized logging
- Automate config generation via Python/Ansible

---

## 🚀 How to run the project

1. Install **Cisco Packet Tracer** (v8.0 or later)
2. Download `Multi-ISP_Residential_Network.pkt`
3. Open the file in Packet Tracer
4. Go to **Simulation** or **Realtime** mode
5. Click on any PC → Desktop → Command Prompt → `ping <gateway>` or cross-house IP
6. To inspect configs: click a router → CLI → `show running-config`

> Full IP addressing tables available in the detailed documentation.

---

## 📁 Repository structure

