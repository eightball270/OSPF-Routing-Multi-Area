# OSPF Routing Multi Area
Building on the previous simulation ([Cisco and MikroTik Dynamic Routing](https://github.com/eightball270/Cisco-and-MikroTik-Dynamic-Routing/tree/main?tab=readme-ov-file#cisco-and-mikrotik-dynamic-routing), [Basic VLAN and DHCP Server](https://github.com/eightball270/Basic-VLAN-and-DHCP-Server/tree/main#basic-vlan-and-dhcp-server), and [DHCP Relay Configuration](https://github.com/eightball270/DHCP-Relay-Configuration#dhcp-relay-configuration)), this simulation utilizes the OSPF (Open Shortest Path First) dynamic routing protocol, which is well-suited for large networks due to its support for multiple areas. The DHCP server configuration is centralized, enabling clients in each area to automatically receive IP configuration from the nearest router configured with a DHCP relay.

## Simulator Used
1. Cisco Packet Tracer
2. GNS3 (MikroTik)

## Requirement Nodes
1. 6 or 8 routers*
2. 3 or 4 switches*
3. Client PCs
4. Access Point and Client Wireless devices**

*) according to the number of OSPF routing areas  
**) optional if creating a WLAN connection, but can be replaced with a regular LAN (Client PCs)

## Configuration Done
1. VLANs on routers and switches that directly connected to the clients
2. Assign an IP address to each router as a gateway
3. Inter-router connection
4. All of routers configured static routing to the host (for remote MikroTik via WinBox)
5. DHCP server on main router (R1) and create port forwarding for remote via WinBox (MikroTik)
6. DHCP relay on some another routers that is directly connected to some clients
7. OSPF routing protocol configuration via command-line (Cisco) and WinBox (MikroTik), including process/router ID and area ID
8. SSID and password on a Access Point (for WLAN connection)

## OSPF Multi Area
In OSPF routing, any number of areas can be defined to build a complex network. The example below uses 4 to 5 OSPF areas, with a minimum requirement of one area (area 0, also known as the backbone area).

### Cisco

![OSPF Multi Area.png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/Cisco/OSPF%20Multi%20Area.png)

[Project File Link (Packet Tracer)](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/Cisco/OSPF%20Multi%20Area.pkt)

The result of multi-area OSPF routing using the **traceroute** command from a client in one area to another client representing a different area.

![OSPF Multi Area (1).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/Cisco/OSPF%20Multi%20Area%20(1).png) ![OSPF Multi Area (2).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/Cisco/OSPF%20Multi%20Area%20(2).png) ![OSPF Multi Area (3).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/Cisco/OSPF%20Multi%20Area%20(3).png) ![OSPF Multi Area (4).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/Cisco/OSPF%20Multi%20Area%20(4).png)

### MikroTik

![OSPF Multi Area (MikroTik).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/MikroTik/OSPF%20Multi%20Area%20(MikroTik).png)

[Project File Link (GNS3)](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/MikroTik/OSPF%20Multi%20Area%20(MikroTik).gns3project.rar) (extract the file first)

The result of multi-area OSPF routing using the **trace** command from a client in one area to another client representing a different area.

![OSPF Multi Area (MikroTik) (1).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/MikroTik/OSPF%20Multi%20Area%20(MikroTik)%20(1).png) ![OSPF Multi Area (MikroTik) (2).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/MikroTik/OSPF%20Multi%20Area%20(MikroTik)%20(2).png) ![OSPF Multi Area (MikroTik) (3).png](https://github.com/eightball270/OSPF-Routing-Multi-Area/blob/main/MikroTik/OSPF%20Multi%20Area%20(MikroTik)%20(3).png)
