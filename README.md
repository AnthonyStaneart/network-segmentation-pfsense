# 🔒 Network Segmentation Lab (pfSense Firewall)

## Overview
This project demonstrates how to enhance network security through segmentation using pfSense, an open-source firewall/router. I segmented a home lab into three zones—LAN, DMZ, and Guest—each with custom access rules enforced by pfSense. The lab simulates real-world security architecture with controlled inter-network communication, validated using Nmap and Wireshark.

## Tools Used
- **pfSense** – Firewall and router configuration
- **Nmap** – Network scanning and port validation
- **Wireshark** – Packet capture and traffic analysis
- **VirtualBox** – Virtual lab environment

## Setup Instructions
1. **Network Design**
   - LAN: `10.0.1.0/24`
   - DMZ: `10.0.2.0/24`
   - Guest: `10.0.3.0/24`
2. **pfSense Configuration**
   - Assign interfaces to each subnet
   - Configure firewall rules:
     - LAN → DMZ (HTTP only)
     - DMZ → No outbound
     - Guest → WAN only
3. **Test Hosts**
   - Ubuntu (LAN), Apache Web Server (DMZ), Kali Linux (Guest)

## Analysis / Findings
- **Nmap** scans validated only HTTP (port 80) was open from LAN to DMZ
- **Wireshark** confirmed packet drops for restricted ports and clean TCP handshakes for allowed traffic
- **Firewall logs** matched expected connection attempts and policy blocks

## Key Takeaways
- Applied defense-in-depth by isolating network zones
- Practiced rule configuration and troubleshooting in pfSense
- Demonstrated least-privilege networking principles
- Captured validation using industry-standard tools

