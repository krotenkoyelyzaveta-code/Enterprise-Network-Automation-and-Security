# Enterprise Campus Network Infrastructure — Phase 1

A scalable and highly available multi-tier Enterprise Campus Network architecture designed and simulated within **EVE-NG**. This repository contains the fully functional baseline infrastructure (routing, switching, redundancy, and IP management) for a large-scale corporate network consisting of **20 devices**.
---
## Network Topology
!(topology.png)
---
##  Network Architecture (20 Devices)
The infrastructure mimics a real-world enterprise deployment, split into functional layers to ensure traffic isolation, redundancy, and easy scaling:

* **Edge Layer (2 Devices):** Perimeter routing and external connectivity baseline.

* **Server Farm (2 Devices):** Dedicated segment for internal corporate servers and resources.

* **Core Layer (2 Devices):** High-speed switching backbone handling core routing protocols.

* **Distribution Layer (4 Devices):** Aggregates Access layer switches and provides gateway redundancy.

* **Access Layer (8 Devices):** End-user connectivity layer providing access to local network segments.
---
##  Phase 1: Core Features Implemented & Working

* **Hierarchical Topology:** Full 3-tier campus network design (Core, Distribution, Access) + Edge and Server Farm blocks.

* **First-Hop Redundancy (HSRP):** Configured on the Distribution layer to provide default gateway redundancy and high availability for end-users.

* **Layer 2 Optimization (Spanning Tree):** Configured to prevent network loops, optimize traffic paths, and ensure fast convergence across all 14 switches.

* **VLAN & Trunking:** Logical network segmentation via VLANs with standard 802.1Q trunking links between switches.

* **IP Address Management:** Centralized DHCP pools configured to automatically assign IP addresses to end devices across different VLANs.

* **Inter-VLAN Routing:** Seamless communication between different departments/VLANs routed via the core layers.
---
##  Repository Structure

* `Edge_Routers.txt` — Edge routing configurations.

* `Farm_Switches.txt` — Server infrastructure connectivity baseline.

* `Core_Switches.txt` — Core backbone routing configurations.

* `Distribution_Switches.txt` — Distribution layer with HSRP and VLAN routing.

* `Access_Switches.txt` — Standardized Access layer configuration templates with Spanning Tree settings.
---
##  Roadmap (Next Phases)
### Phase 2: Advanced Services, Security & Redundancy Testing

* **Internet Edge & Security:** Implement NAT/PAT and Access Control Lists (ACLs) to enable secure internet access for internal segments.

* **High Availability Validation:** Perform rigorous failover testing of HSRP gateways and path redundancy to ensure zero-downtime traffic forwarding.

* **Embedded Automation (EEM):** Deploy Cisco Embedded Event Manager (EEM) applets for basic automated troubleshooting and logging on network devices.

* **VLAN Architecture Deep-Dive:** Restructure and optimize the switching environment by analyzing Local vs. End-to-End VLAN models.

* **Enterprise Server Farm Integration:** Connect a Windows Server workstation to the corporate network, deploy Active Directory Domain Services (AD DS), and configure the Domain Controller.

* **Network Backup & Recovery:** Implement an automated configuration backup system (via TFTP/SFTP or specialized scripts) for all network equipment.
