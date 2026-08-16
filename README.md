# Enterprise Campus Network Infrastructure

## Overview
A highly available **enterprise campus network** designed and implemented in **Cisco Packet Tracer** to simulate a multi-floor corporate network environment.

The design incorporates **multi-area OSPF routing, dual-ISP connectivity, departmental VLAN segmentation, Layer 2 switching, wireless access, and structured IPv4 addressing** to provide scalable and reliable communication across the campus.

## Network Topology

The campus network is divided into **three floors**, with each floor serving different departments and users.

### Floor 1

* Reception — VLAN 22 — `192.168.22.0/24`
* Merchandise — VLAN 23 — `192.168.23.0/24`
* Dining — VLAN 24 — `192.168.24.0/24`

### Floor 2

* Finance — VLAN 25 — `192.168.25.0/24`
* HR — VLAN 26 — `192.168.26.0/24`
* Marketing — VLAN 27 — `192.168.27.0/24`

### Floor 3

* VLAN 28 — `192.168.28.0/24`
* Administration — VLAN 29 — `192.168.29.0/24`

Each departmental network is logically separated using VLANs to create independent broadcast domains and improve network organization.

## Network Architecture

The network uses a hierarchical campus design consisting of:

* Cisco routers for Layer 3 connectivity and routing
* Cisco switches for access-layer connectivity
* Wireless access points for mobile devices
* End-user PCs and laptops
* Network printers
* Smartphones and tablets
* Two external ISP routers providing redundant WAN connectivity

The internal routers are interconnected using point-to-point serial links with `/30` networks.

## WAN Connectivity

The campus network connects to two separate ISP routers:

### ISP 1

```text
ISP 1: 100.100.100.1
Campus Router: 100.100.100.2
Network: 100.100.100.0/16
```

### ISP 2

```text
ISP 2: 200.200.200.1
Campus Router: 200.200.200.2
Network: 200.200.200.0/16
```

The dual-ISP architecture provides an additional path toward external networks and demonstrates WAN redundancy in the simulated environment.

## Routing

**OSPF** is used as the internal dynamic routing protocol.

The network demonstrates **multi-area OSPF**, allowing the campus routing domain to be divided into multiple logical areas.

Point-to-point router links use `/30` subnets, including networks in the `10.65.47.0/30` range shown in the topology.

OSPF provides:

* Dynamic route advertisement
* Automatic route learning
* Scalability for multiple network segments
* Reduced dependency on manually configured routes
* Faster adaptation to topology changes

## VLAN Segmentation

Departmental traffic is separated using VLANs.

| VLAN | Department         | Network           |
| ---: | ------------------ | ----------------- |
|   22 | Reception          | `192.168.22.0/24` |
|   23 | Merchandise        | `192.168.23.0/24` |
|   24 | Dining             | `192.168.24.0/24` |
|   25 | Finance            | `192.168.25.0/24` |
|   26 | HR                 | `192.168.26.0/24` |
|   27 | Marketing          | `192.168.27.0/24` |
|   28 | Department Network | `192.168.28.0/24` |
|   29 | Administration     | `192.168.29.0/24` |

This segmentation separates departmental broadcast domains and provides a structured foundation for implementing network security policies.

## Wireless Connectivity

Wireless access points are deployed on the campus floors to provide connectivity for mobile and wireless devices, including:

* Laptops
* Smartphones
* Tablets

This allows both wired and wireless users to access the appropriate campus network resources.

## IP Addressing

The addressing scheme uses separate IPv4 networks for each department.

Departmental networks use `/24` subnet masks:

```text
255.255.255.0
```

Router-to-router point-to-point links use `/30` networks:

```text
255.255.255.252
```

Using `/30` networks for point-to-point connections minimizes address wastage while providing the two usable addresses required by each router interface.

## Network Verification

Network connectivity and routing can be verified using Cisco IOS commands such as:

```text
show ip interface brief
show ip route
show ip ospf neighbor
show ip ospf interface
show vlan brief
show interfaces trunk
show mac address-table
```

End-to-end connectivity can be tested using:

```text
ping <destination-ip>
traceroute <destination-ip>
```

These commands can be used to verify interface status, VLAN configuration, OSPF neighbor relationships, routing tables, Layer 2 forwarding, and end-to-end connectivity.

## Troubleshooting Methodology

A structured troubleshooting approach was used to identify network connectivity problems:

1. Verify physical and logical connections.
2. Check interface status using `show ip interface brief`.
3. Verify IP addresses and subnet masks.
4. Check VLAN assignments.
5. Verify OSPF neighbor relationships.
6. Inspect the routing table.
7. Test connectivity using `ping`.
8. Use `traceroute` to identify routing paths.
9. Check MAC address learning on switches.
10. Correct configuration issues and retest connectivity.

## Technologies & Skills

### Networking

* IPv4 addressing
* Subnetting
* VLANs
* Ethernet switching
* Inter-VLAN communication
* OSPF
* Multi-area OSPF
* WAN connectivity
* Point-to-point networks
* Network redundancy
* Wireless networking

### Cisco

* Cisco IOS
* Router configuration
* Switch configuration
* Interface configuration
* VLAN configuration
* OSPF configuration
* Network verification
* CLI-based troubleshooting

### Tools

* Cisco Packet Tracer
```

## Key Learning Outcomes

This project provided hands-on experience in designing and configuring a simulated enterprise network and strengthened practical knowledge of **routing, switching, VLAN segmentation, OSPF, IP addressing, WAN connectivity, wireless networking, and network troubleshooting**.
