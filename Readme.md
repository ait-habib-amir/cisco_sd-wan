
# SD-WAN Cisco Automation Project

Automated deployment of a complete Cisco SD-WAN lab (vEdge, vSmart, vBond, vManage) using QEMU/KVM and Shell scripting.  
This project was developed as part of my Master 2 in Networks & Security at Sorbonne Université to simulate and automate SD-WAN infrastructures for learning and experimentation.

## Overview

This repository provides an automated and reproducible SD-WAN lab environment using Cisco virtual appliances and Linux network interfaces.  
The setup allows for:
- Virtualized SD-WAN components (vEdge, vSmart, vBond, vManage)
- Automated launch and configuration through Bash scripts
- Network interconnection via TAP and bridge interfaces
- Performance and connectivity testing with iperf
- Monitoring through Cisco vManage GUI

## Architecture

```mermaid
graph TD
  Host[Host OS (Linux)]
  subgraph SD-WAN VMs
    vEdge[vEdge]
    vSmart[vSmart]
    vBond[vBond]
    vManage[vManage]
  end
  Host --- vEdge
  Host --- vSmart
  Host --- vBond
  Host --- vManage
  Host --> Bridges[Linux bridges & TAP interfaces]



## Features

- Full virtual SD-WAN setup (vEdge, vBond, vSmart, vManage)
- Automated launch of all components using a single Shell script
- Dynamic network configuration (bridges, TAP interfaces)
- Integrated monitoring via vManage
- Traffic performance testing with iperf
- Compatible with QEMU/KVM and AlmaLinux

## Tech Stack

| Category | Tools / Technologies |
|-----------|----------------------|
| Virtualization | QEMU/KVM |
| Automation | Bash scripts |
| OS | AlmaLinux |
| Network Monitoring | vManage, iperf |
| Networking | TAP, Bridge, DHCP, VPN, BGP, OSPF |



## Usage

### Requirements
- Linux system (tested on AlmaLinux / Ubuntu 22.04)
- QEMU / KVM installed
- bridge-utils and iproute2
- Cisco SD-WAN images (vEdge, vSmart, vBond, vManage)
- Root privileges

### Setup
```bash
git clone https://github.com/ait-habib-amir/SDWAN-main.git
cd SDWAN-main/scripts
chmod +x *.sh

