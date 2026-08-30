# Enterprise Network Security Lab

## Overview

This project demonstrates the design and security implementation of an enterprise network using **Cisco Packet Tracer**. The network consists of one Cisco 1941 router and two Cisco 2960 switches representing the headquarters and branch network.

The project focuses on network segmentation, inter-VLAN communication, secure remote management, automatic IP address assignment, and Layer 2 security.

## Network Technologies

* VLAN Segmentation
* Static Trunking
* DTP Disable
* Native VLAN 97
* VTP Server and Client
* Router-on-a-Stick
* Inter-VLAN Routing
* DHCP
* SSH
* Port Security with Sticky MAC
* DHCP Snooping
* NTP
* PortFast
* BPDU Guard

## VLAN Structure

| VLAN    | Department         | Network       |
| ------- | ------------------ | ------------- |
| VLAN 2  | SMM                | 10.10.2.0/24  |
| VLAN 3  | Developers         | 10.10.3.0/24  |
| VLAN 4  | HR                 | 10.10.4.0/24  |
| VLAN 99 | Admin / Management | 10.10.99.0/29 |

## Network Configuration

* Configured VLANs for different departments.
* Established static trunk links between switches.
* Disabled DTP on trunk connections.
* Used VLAN 97 as the native VLAN.
* Configured VTP with the domain `mitacademy.az`.
* Configured the headquarters switch as the VTP Server and the branch switch as the VTP Client.
* Implemented Router-on-a-Stick for communication between VLANs.
* Configured DHCP pools for VLAN clients.
* Reserved the first 10 IP addresses of each data VLAN for static assignment.
* Used `8.8.8.8` as the DNS server.
* Configured VLAN 99 for administrative and management access.

## Security Implementation

* Configured secure remote management using SSH.
* Restricted SSH access to the Admin/Management VLAN.
* Applied Port Security with Sticky MAC addresses.
* Disabled unused switch ports.
* Configured DHCP Snooping.
* Enabled PortFast on access ports.
* Enabled BPDU Guard for Layer 2 protection.
* Configured encrypted local authentication credentials.

## Time Synchronization

An NTP server was configured to provide time synchronization for network devices.

**NTP Server:** `10.2.2.2`

## Inter-VLAN Gateways

* VLAN 2: `10.10.2.254`
* VLAN 3: `10.10.3.254`
* VLAN 4: `10.10.4.254`
* VLAN 99: `10.10.99.6`

## Testing

Client devices were configured to obtain IP addresses through DHCP. Connectivity between devices in different VLANs was tested to verify the Router-on-a-Stick and inter-VLAN routing configuration.

## Tools

* Cisco Packet Tracer
* Cisco IOS CLI
* GitHub
