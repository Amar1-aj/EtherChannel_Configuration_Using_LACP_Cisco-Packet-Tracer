# EtherChannel Configuration Using LACP – Cisco Packet Tracer

## Project Overview

This project demonstrates the configuration of **EtherChannel using Link Aggregation Control Protocol (LACP)** between two Cisco switches in Cisco Packet Tracer.

EtherChannel combines multiple physical links into one logical link to increase available bandwidth and provide link redundancy. LACP dynamically negotiates the formation of the EtherChannel between switches.

## Network Topology

The topology consists of two Cisco switches connected through two Gigabit Ethernet links.

- Switch S1
- Switch S2
- Two Gigabit Ethernet connections (G0/1 and G0/2)
- One logical EtherChannel interface (Port-Channel 1)

## Technologies and Concepts Used

- Cisco Packet Tracer
- Cisco IOS CLI
- EtherChannel
- Link Aggregation Control Protocol (LACP)
- VLAN Configuration
- VLAN Trunking
- Native VLAN
- Port-Channel Configuration
- Network Redundancy and Link Aggregation

## VLAN Configuration

The following VLANs were configured on both switches:

| VLAN ID | VLAN Name | Purpose |
|---|---|---|
| 10 | Students | Student network |
| 20 | Staff | Staff network |
| 99 | Native | Native VLAN for trunk link |

## Switch Port Configuration

Access ports were assigned to the respective VLANs on both switches.

| Interface | VLAN | Purpose |
|---|---|---|
| Fa0/1 | 10 | Students |
| Fa0/2 | 20 | Staff |
| G0/1–G0/2 | EtherChannel | LACP links |

## EtherChannel Configuration

LACP was configured on both switches using active mode.

```bash
interface range g0/1-2
channel-group 1 mode active
```

This configuration creates EtherChannel group 1 and negotiates link aggregation using LACP.

## Trunk Configuration

Port-Channel 1 was configured as a trunk interface to carry multiple VLANs between the switches.

```bash
interface port-channel 1
switchport mode trunk
switchport trunk native vlan 99
switchport trunk allowed vlan 10,20,99
```

## Verification Commands

The following commands were used to verify the configuration:

```bash
show etherchannel summary
show interfaces trunk
show ip interface brief
show vlan brief
```

These commands help verify EtherChannel status, trunk configuration, VLAN assignments, and interface status.

## Project Objectives

- Configure VLANs on two Cisco switches.
- Assign access ports to different VLANs.
- Establish EtherChannel using LACP.
- Configure trunking over the logical Port-Channel interface.
- Allow multiple VLANs to communicate across the switch-to-switch connection.
- Understand link aggregation and redundancy in switching networks.

## Learning Outcomes

Through this project, I gained practical experience in:

- Configuring EtherChannel using LACP.
- Understanding active negotiation mode.
- Combining multiple physical links into one logical connection.
- Configuring VLAN trunking over Port-Channel interfaces.
- Verifying EtherChannel and troubleshooting switching configurations.

## Conclusion

This project helped me understand how EtherChannel and LACP improve network link utilization and provide redundancy between switches. It also strengthened my practical knowledge of VLANs, trunking, and Cisco switch configuration using Cisco IOS CLI.

**Tool Used:** Cisco Packet Tracer
