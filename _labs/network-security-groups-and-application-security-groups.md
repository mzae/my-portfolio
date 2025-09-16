---
title: "Azure Network Security Groups & Application Security Groups"
layout: lab
permalink: /labs/azure-nsg-asg-lab/
author: Daniel Wanjama
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
📸 *Screenshot: `step01-resource-group.png` – Resource group creation*  
![Resource Group](../../assets/images/labs/step01-resource-group.png)

📸 *Screenshot: `step01-virtual-network.png` – Virtual network setup*  
![Virtual Network](../../assets/images/labs/step01-virtual-network.png)

---

### Task 2: Create Application Security Groups

- Created ASG `ASG-Web` for web servers  
- Created ASG `ASG-Management` for management servers  
📸 *Screenshot: `step02-asg-web.png` – ASG for web servers*  
![ASG - Web](../../assets/images/labs/step02-asg-web.png)

📸 *Screenshot: `step02-asg-management.png` – ASG for management servers*  
![ASG - Management](../../assets/images/labs/step02-asg-management.png)

---

### Task 3: Deploy Virtual Machines

- Deployed Web Server VM with IIS installed  
- Deployed Management Server VM configured for RDP access  
📸 *Screenshot: `step03-web-vm.png` – Web VM deployment*  
![Web VM](../../assets/images/labs/step03-web-vm.png)

📸 *Screenshot: `step03-management-vm.png` – Management VM deployment*  
![Management VM](../../assets/images/labs/step03-management-vm.png)

---

### Task 4: Associate NICs with ASGs

- Associated Web VM NIC with `ASG-Web`  
- Associated Management VM NIC with `ASG-Management`  
📸 *Screenshot: `step04-nic-asg.png` – NIC association with ASGs*  
![NIC Association](../../assets/images/labs/step04-nic-asg.png)

---

### Task 5: Configure Network Security Groups

- Created NSG for Web servers: allowed HTTP (port 80), blocked RDP  
- Created NSG for Management servers: allowed RDP (port 3389) from trusted IPs, blocked HTTP  
📸 *Screenshot: `step05-nsg-web.png` – NSG for web access*  
![NSG - Web](../../assets/images/labs/step05-nsg-web.png)

📸 *Screenshot: `step05-nsg-management.png` – NSG for management access*  
![NSG - Management](../../assets/images/labs/step05-nsg-management.png)

---

### Task 6: Validate Traffic Filtering

- Verified Web Server accessible via browser on port 80  
- Verified Management Server accessible via RDP from admin workstation  
📸 *Screenshot: `step06-iis-access.png` – IIS access test*  
![IIS Access](../../assets/images/labs/step06-iis-access.png)

📸 *Screenshot: `step06-rdp-access.png` – RDP access test*  
![RDP Access](../../assets/images/labs/step06-rdp-access.png)

---

### Task 7: Final Validation

- Used Azure Network Watcher to confirm traffic flow matches NSG rules  
📸 *Screenshot: `step07-network-watcher.png` – Network Watcher validation*  
![Network Watcher](../../assets/images/labs/step07-network-watcher.png)

---

## Key Learnings

- ASGs simplify rule management by grouping VMs logically  
- NSGs enforce traffic filtering based on ASG membership  
- Role-based access improves security posture in cloud environments  

---
