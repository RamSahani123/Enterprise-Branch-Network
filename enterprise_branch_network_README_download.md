# Enterprise Branch Network Implementation (Cisco Packet Tracer)

![Topology](screenshots/01-topology-overview.png)

## Project Overview

This project demonstrates the design and implementation of a secure enterprise branch network using Cisco Packet Tracer.

The network was built using industry-standard Layer 2 and Layer 3 technologies including VLAN segmentation, Router-on-a-Stick inter-VLAN routing, DHCP services, EtherChannel (LACP), SSH management, ACL-based security controls, and port security.

---

## Technologies Implemented

- VLAN Segmentation
- Router-on-a-Stick
- Inter-VLAN Routing
- DHCP Services
- EtherChannel (LACP)
- 802.1Q Trunking
- SSH Remote Management
- Access Control Lists (ACLs)
- Port Security (Sticky MAC)
- Voice VLAN
- NAT/PAT
- PVST Spanning Tree
- Management VLAN Design

---

## Network Topology

### Logical Design

![Topology](screenshots/01-topology-overview.png)

### VLAN Structure

| VLAN | Name | Subnet |
|--------|--------|--------|
| 10 | Management | 10.10.10.0/24 |
| 20 | Users | 10.10.20.0/24 |
| 30 | Voice | 10.10.30.0/24 |
| 40 | Servers | 10.10.40.0/24 |
| 50 | Guest | 10.10.50.0/24 |
| 99 | Native / Unused | Native VLAN |

---

## Device Inventory

### Routers
- ISP-R1
- BR-R1

### Switches
- SW1
- SW2

### End Devices
- Admin-PC
- User-PC1
- User-PC2
- User-PC3
- Server-01
- Server-02
- IP-Phone01
- AP-01

---

## Layer 2 Implementation

### VLAN Configuration
![VLANs](screenshots/02-vlan-configuration.png)

### Trunk Verification
![Trunks](screenshots/04-trunk-verification.png)

### EtherChannel (LACP)
![EtherChannel](screenshots/03-etherchannel-lacp.png)

---

## Layer 3 Implementation

### Router-on-a-Stick

Inter-VLAN routing is provided through 802.1Q subinterfaces configured on BR-R1.

![Router-on-a-Stick](screenshots/05-router-on-a-stick.png)

Configured gateways:

| VLAN | Gateway |
|--------|--------|
| 10 | 10.10.10.1 |
| 20 | 10.10.20.1 |
| 30 | 10.10.30.1 |
| 40 | 10.10.40.1 |
| 50 | 10.10.50.1 |

---

## DHCP Services

DHCP pools were configured on BR-R1 for User, Voice, Management, and Guest VLANs.

![DHCP](screenshots/06-dhcp-bindings.png)

---

## Security Controls

### SSH Management

- SSH Version 2
- Local User Authentication
- Management VLAN Restriction

### Port Security

- Sticky MAC Addresses
- Restrict Violation Mode

### Access Control Lists

Management access restricted to VLAN 10.

Guest VLAN isolated from internal branch networks.

![ACL](screenshots/07-acl-security.png)

---

## Validation Tests

### DHCP Client Verification

![DHCP Client](screenshots/08-user-dhcp.png)

### Inter-VLAN Connectivity

Validated successful communication between User VLAN and Server VLAN.

![Connectivity](screenshots/09-connectivity-test.png)

---

## Skills Demonstrated

- Cisco IOS Configuration
- Network Segmentation
- Enterprise Switching
- Inter-VLAN Routing
- DHCP Deployment
- ACL Security Policies
- EtherChannel Deployment
- SSH Hardening
- Port Security
- Network Troubleshooting
- Documentation and Validation

---

## Repository Structure

```text
enterprise-branch-network/
│
├── README.md
│
├── packet-tracer/
│   └── enterprise-branch-network-2026.pkt
│
├── configs/
│   ├── BR-R1.cfg
│   ├── ISP-R1.cfg
│   ├── SW1.cfg
│   └── SW2.cfg
│
└── screenshots/
    ├── 01-topology-overview.png
    ├── 02-vlan-configuration.png
    ├── 03-etherchannel-lacp.png
    ├── 04-trunk-verification.png
    ├── 05-router-on-a-stick.png
    ├── 06-dhcp-bindings.png
    ├── 07-acl-security.png
    ├── 08-user-dhcp.png
    └── 09-connectivity-test.png
```

---

## Author

Ram Sahani

Aspiring Network Engineer | Cisco Networking | Infrastructure | Cybersecurity
