# Lab 001: Two subnets routed by one router

## Goal
Build two separate IPv4 subnets and route traffic between them.

## Why this matters (real work translation)
- Subnets are how companies separate networks (departments, VLANs, security zones).
- Routing is how traffic moves between those networks (router, firewall, or L3 switch does this).
- Validation (ping + show commands) is the difference between “I configured stuff” and “it works”.

## Tools
- Cisco Packet Tracer (simulation lab)

## Topology
- 1 Router
- 1 Switch
- 2 PCs

## IP plan
Subnet A: 192.168.10.0/24
- Router G0/0: 192.168.10.1
- PC0: 192.168.10.10, GW 192.168.10.1

Subnet B: 192.168.20.0/24
- Router G0/1: 192.168.20.1
- PC1: 192.168.20.10, GW 192.168.20.1

## Validation target
From PC1:
- ping 192.168.10.1
- ping 192.168.20.1
- ping 192.168.20.10

Router:
- show ip interface brief (both interfaces up/up with correct IPs)

## Evidence to capture
- topology screenshot (topology.png)
- ping proof screenshot (ping-proof.png)
- router output pasted into router-outputs.txt
- Packet Tracer file (lab-001.pkt)

##Results
  Ping PC0 → PC1 succeeded after initial ARP timeout 

  Router interfaces up/up”

