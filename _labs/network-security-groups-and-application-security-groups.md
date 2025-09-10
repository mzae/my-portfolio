---
title: "Network Security Groups & Application Security Groups"
layout: lab
permalink: /labs/Network-Security-Groups-and-Application-Security-Groups/
---

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

## Introduction

This lab demonstrates how to secure Azure-based infrastructure using:

- **Network Security Groups (NSGs)** to define traffic rules  
- **Application Security Groups (ASGs)** to logically group VMs by role  

The objective is to isolate and protect two server roles—**Web Servers** and **Management Servers**—with tailored access controls.

## Objectives

- Create virtual networking infrastructure  
- Deploy virtual machines (VMs)  
- Configure ASGs and NSGs  
- Validate traffic filtering

## Prerequisites

- Azure subscription  
- Familiarity with Azure Portal and virtual networks  
- Access to Azure Cloud Shell or PowerShell  

## Walkthrough

### Task 1: Create Resource Group

Created a new resource group to contain all lab resources.  
📸 *Screenshot: `resource-group.png` – Resource Group creation*  
![Resource Group](../../assets/images/labs/resource-group.png)

---

### Task 2: Create Virtual Network & Subnets

- Created a virtual network named `LabVNet`  
- Added two subnets: `WebSubnet` and `MgmtSubnet`  
📸 *Screenshot: `vnet-subnets.png` – Virtual Network and Subnet configuration*  
![Virtual Network](../../assets/images/labs/vnet-subnets.png)

---

### Task 3: Create Application Security Groups (ASGs)

- `WebServers-ASG`: For IIS web servers  
- `MgmtServers-ASG`: For remote management VMs  
📸 *Screenshot: `asg-setup.png` – ASG creation*  
![ASG Setup](../../assets/images/labs/asg-setup.png)

---

### Task 4: Deploy Virtual Machines

#### Web Server VM

- Deployed VM in `WebSubnet`  
- Installed IIS  
- Assigned to `WebServers-ASG`  
📸 *Screenshot: `web-vm.png` – Web Server VM deployment*  
![Web VM](../../assets/images/labs/web-vm.png)

📸 *Screenshot: `iis-installed.png` – IIS installation confirmation*  
![IIS Installed](../../assets/images/labs/iis-installed.png)

#### Management Server VM

- Deployed VM in `MgmtSubnet`  
- Assigned to `MgmtServers-ASG`  
📸 *Screenshot: `mgmt-vm.png` – Management Server VM deployment*  
![Mgmt VM](../../assets/images/labs/mgmt-vm.png)

---

### Task 5: Configure Network Security Groups (NSGs)

#### NSG for Web Server

- Allow inbound HTTP (port 80) from internet  
- Deny inbound RDP (port 3389)  
📸 *Screenshot: `web-nsg-rules.png` – NSG rules for Web Server*  
![Web NSG](../../assets/images/labs/web-nsg-rules.png)

#### NSG for Management Server

- Allow inbound RDP (port 3389) from trusted IP  
- Deny all other inbound traffic  
📸 *Screenshot: `mgmt-nsg-rules.png` – NSG rules for Management Server*  
![Mgmt NSG](../../assets/images/labs/mgmt-nsg-rules.png)

---

### Task 6: Associate NSGs with Subnets

Linked NSGs to respective subnets to enforce traffic rules.  
📸 *Screenshot: `nsg-subnet-link.png` – NSG association with subnets*  
![NSG Subnet Link](../../assets/images/labs/nsg-subnet-link.png)

---

### Task 7: Validate Connectivity

- Accessed Web Server via browser to confirm HTTP access  
- Attempted RDP to Web Server (denied)  
- Successfully connected to Management Server via RDP  

📸 *Screenshot: `http-access.png` – HTTP access to Web Server*  
![HTTP Access](../../assets/images/labs/http-access.png)

📸 *Screenshot: `rdp-denied.png` – RDP denied to Web Server*  
![RDP Denied](../../assets/images/labs/rdp-denied.png)

📸 *Screenshot: `rdp-success.png` – RDP access to Management Server*  
![RDP Success](../../assets/images/labs/rdp-success.png)

---

## Conclusion

This lab provided hands-on experience with Azure-native security tools, focusing on NSGs and ASGs to enforce traffic control and role-based access. Key takeaways include:

- Using ASGs to simplify rule management  
- Applying NSGs to enforce traffic policies  
- Validating connectivity and access restrictions  

These skills are directly applicable to real-world cloud security scenarios and strengthen my expertise in Azure infrastructure protection.

