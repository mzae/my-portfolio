---
title: "Azure Network Security Groups & Application Security Groups"
layout: lab
author: Wanjama Daniel
permalink: /labs/azure-nsg-asg-lab/
date: 2025-09-16
---

## Introduction

This lab demonstrates how to secure Azure virtual machines using **Network Security Groups (NSGs)** and **Application Security Groups (ASGs)**. By logically grouping VMs and applying targeted inbound rules, I isolated traffic for **Web Servers** and **Management Servers**, enhancing role-based access control and overall cloud security posture.

---

## Objectives

- Create resource group and virtual network
- Define Application Security Groups (ASGs)
- Deploy virtual machines for web and management roles
- Associate NICs with ASGs
- Configure NSGs with role-based inbound rules
- Validate traffic filtering and rule enforcement

---

## Prerequisites

- Azure subscription with contributor or admin access
- Skillable lab environment or Azure sandbox
- Familiarity with Azure Portal and VM deployment

---

## Walkthrough

### Task 1: Create Resource Group & Virtual Network

- Created resource group `RG-SecurityLab` in East Africa
- Deployed virtual network `VNet-SecurityLab` with subnets for Web and Management servers

📸 *Screenshot: Resource group creation*
![Azure Portal showing resource group creation with region and subscription details](../../assets/images/labs/step01-resource-group.png)
*Resource Group*

📸 *Screenshot: Virtual network setup*
![Virtual network configuration showing subnets for web servers and management servers](../../assets/images/labs/step01-virtual-network.png)
*Virtual Network*

---

### Task 2: Create Application Security Groups

- Created ASG `ASG-Web` for web servers
- Created ASG `ASG-Management` for management servers

📸 *Screenshot: ASG for web servers*
![Application Security Group creation interface for web server group](../../assets/images/labs/step02-asg-web.png)
*ASG - Web*

📸 *Screenshot: ASG for management servers*
![Application Security Group creation interface for management server group](../../assets/images/labs/step02-asg-management.png)
*ASG - Management*

---

### Task 3: Deploy Virtual Machines

- Deployed Web Server VM with IIS installed
- Deployed Management Server VM configured for RDP access

📸 *Screenshot: Web VM deployment*
![Virtual machine deployment interface showing web server configuration with IIS](../../assets/images/labs/step03-web-vm.png)
*Web VM*

📸 *Screenshot: Management VM deployment*
![Virtual machine deployment interface showing management server configuration for RDP](../../assets/images/labs/step03-management-vm.png)
*Management VM*

---

### Task 4: Associate NICs with ASGs

- Associated Web VM NIC with `ASG-Web`
- Associated Management VM NIC with `ASG-Management`

📸 *Screenshot: NIC association with ASGs*
![Network interface configuration showing ASG association for web and management VMs](../../assets/images/labs/step04-nic-asg.png)
*NIC Association*

---

### Task 5: Configure Network Security Groups

- Created NSG for Web servers: allowed HTTP (port 80), blocked RDP
- Created NSG for Management servers: allowed RDP (port 3389) from trusted IPs, blocked HTTP

📸 *Screenshot: NSG for web access*
![NSG rules configuration showing HTTP 80 allowed and RDP blocked for web servers](../../assets/images/labs/step05-nsg-web.png)
*NSG - Web*

📸 *Screenshot: NSG for management access*
![NSG rules configuration showing RDP 3389 allowed and HTTP blocked for management servers](../../assets/images/labs/step05-nsg-management.png)
*NSG - Management*

---

### Task 6: Validate Traffic Filtering

- Tested HTTP access to Web VM (successful)
- Tested RDP access to Management VM (successful)
- Attempted cross-VM traffic (blocked as configured)

📸 *Screenshot: Successful HTTP access to Web Server*
![Browser showing successful HTTP connection to web server on port 80](../../assets/images/labs/step06-http-test-web.png)
*HTTP Access to Web Server*

📸 *Screenshot: Successful RDP connection to Management Server*
![RDP client showing successful connection to management server on port 3389](../../assets/images/labs/step06-rdp-test-management.png)
*RDP Access to Management Server*

---

## Summary

This lab successfully demonstrated how to use NSGs and ASGs to implement role-based network security. Web servers were isolated to HTTP only, while management servers were restricted to RDP with proper rule enforcement.

---

## References

- [Network Security Groups Documentation](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)
- [Application Security Groups](https://learn.microsoft.com/en-us/azure/virtual-network/application-security-groups)
- [Security Best Practices](https://learn.microsoft.com/en-us/azure/security/fundamentals/network-best-practices)
