# Given Industries Enterprise Network (Cisco Packet Tracer)

## Overview
This project is a Cisco Packet Tracer simulation of an enterprise network for **Given Industries**, featuring VLAN-based segmentation, centralized DHCP and DNS services, wireless access, and connectivity to an external organization (**Maroks Communications**).

The network demonstrates best practices in IP addressing, inter-VLAN routing, service hosting, and DNS name resolution.

---

## Tools & Technologies
- Cisco Packet Tracer
- Multilayer Switch (MLS)
- Cisco Routers
- VLANs & Trunking
- DHCP & DNS Servers
- Web Servers
- Wireless LAN
- TCP/IP Networking

---

## Network Addressing Scheme

### Internal Network (Given Industries)
- **Address Block:** `172.16.0.0/24`

### External Network (Maroks Communications)
- **Address Block:** `192.168.10.0/24`

---

## VLAN Configuration (Given Industries)

| VLAN ID | Department / Purpose | Subnet |
|------|----------------------|--------|
| 10   | Customer Service     | 172.16.10.0/24 |
| 20   | Finance              | 172.16.20.0/24 |
| 30   | Administrators       | 172.16.30.0/24 |
| 60   | Servers              | 172.16.60.0/24 |

---

## Server Configuration

### Given Industries (VLAN 60)

| Server Type | IP Address | Description |
|-----------|-----------|------------|
| Web Server | 172.16.60.2 | Hosts **www.given.com** |
| DHCP Server | 172.16.60.2 | Provides dynamic IP addressing |
| DNS Server | 172.16.60.5 | Resolves internal & external domains |

> The DNS server in Given Industries resolves both **www.given.com** and **www.maroks.co.za**.

---

### Maroks Communications (External Network)

| Server Type | IP Address | Description |
|-----------|-----------|------------|
| Web Server | 192.168.10.2 | Hosts **www.maroks.co.za** |
| DHCP Server | 192.168.10.3 | Provides IP addresses for Maroks PCs |

---

## End Devices (Dynamic IPs)

### Given Industries PCs

| Department | Device | IP Address |
|---------|-------|-----------|
| Customer Service | CS PC | 172.16.10.2 |
| Finance | Finance PC | 172.16.20.2 |
| Administrators | Admin PC | 172.16.30.2 |

---

### Maroks Communications PCs (Dynamic IPs)

| Device | IP Address |
|------|-----------|
| Mosa PC | 192.168.10.4 |
| Marokane PC | 192.168.10.3 |

---

## Wireless Network (Given Industries)

- **SSID:** `GivenIndustries-Corp1`
- **Security:** WPA2-PSK
- **Password:** `cisco12345`
- **IP Assignment:** DHCP (dynamic)

Laptops connect wirelessly and receive IP addresses automatically from the DHCP server.

---

## DNS & Website Configuration

| Website | Hosted On | Resolved By |
|------|-----------|------------|
| www.given.com | Given Industries Web Server | Given Industries DNS |
| www.maroks.co.za | Maroks Communications Web Server | Given Industries DNS |

> Devices in Maroks Communications may also access services using direct IP addresses.

---

## Example Traffic Flow
**CS PC accessing www.maroks.co.za**

[CS PC (172.16.10.2) > ping (192.168.10.2)]
→ VLAN 10 Gateway (172.16.10.1 – MLS)
→ MLS Trunk Interface
→ Router Interface (172.16.50.101)
→ Router Interface (100.128.0.2)
→ Router Interface (100.128.0.1)
→ Router Interface (192.168.10.1)
→ Maroks Web Server (192.168.10.2)


This demonstrates successful **inter-VLAN routing, multi-router traversal, and external network access**.

---

## How to Open the Project
1. Install **Cisco Packet Tracer**
2. Download or clone this repository
3. Open the `.pkt` file
4. Use **Simulation Mode** to observe DHCP, DNS, and HTTP traffic

---

## Testing & Verification
- DHCP address assignment verified
- DNS name resolution tested
- Inter-VLAN communication confirmed
- Web services tested using browser
- External network connectivity validated

---

## Learning Objectives
- Design and implement VLAN-based networks
- Configure DHCP and DNS services
- Enable inter-VLAN and external routing
- Secure and deploy wireless LANs
- Document enterprise network infrastructure

---

## Author
**Given Thulare**  
GitHub: https://github.com/giventhulare15

---

## License
This project is for educational and demonstration purposes.
