# 🔐 Azure Lab Walkthrough: Network Security Groups & Application Security Groups

**Author:** Daniel Wanjama  
**Lab ID:** ADC-CSS02-25012  
**Focus:** Azure Cloud Security – NSGs & ASGs  
**Tools Used:** Azure Portal, Virtual Machines, NSGs, ASGs

---

## 🧭 Lab Overview

This lab demonstrates how to secure Azure virtual machines using **Network Security Groups (NSGs)** and **Application Security Groups (ASGs)**. The goal is to isolate traffic for **Web Servers** and **Management Servers** using role-based access controls.

---

## 🛠️ Step 1: Create Resource Group & Virtual Network

Create a new resource group and virtual network to host your infrastructure.

![Resource Group](../../assets/images/labs/step01-resource-group.png)  
*Resource group `RG-SecurityLab` created in East Africa.*

![Virtual Network](../../assets/images/labs/step01-virtual-network.png)  
*Virtual network `VNet-SecurityLab` with subnets for Web and Management servers.*

---

## 🧩 Step 2: Create Application Security Groups

Define ASGs to logically group VMs by role.

![ASG - Web](../../assets/images/labs/step02-asg-web.png)  
*Application Security Group `ASG-Web` created.*

![ASG - Management](../../assets/images/labs/step02-asg-management.png)  
*Application Security Group `ASG-Management` created.*

---

## 💻 Step 3: Deploy Virtual Machines

Deploy two VMs: one for web hosting and one for management tasks.

![Web VM](../../assets/images/labs/step03-web-vm.png)  
*Web Server VM with IIS installed.*

![Management VM](../../assets/images/labs/step03-management-vm.png)  
*Management Server VM configured for RDP access.*

---

## 🔗 Step 4: Associate NICs with ASGs

Assign each VM’s network interface to the appropriate ASG.

![NIC Association](../../assets/images/labs/step04-nic-asg.png)  
*Web VM NIC associated with `ASG-Web`; Management VM NIC with `ASG-Management`.*

---

## 🚦 Step 5: Configure Network Security Groups

Create NSGs and define inbound rules based on ASG membership.

![NSG - Web](../../assets/images/labs/step05-nsg-web.png)  
*Allow HTTP (port 80) from Internet to `ASG-Web`. Block RDP.*

![NSG - Management](../../assets/images/labs/step05-nsg-management.png)  
*Allow RDP (port 3389) from trusted IPs to `ASG-Management`. Block HTTP.*

---

## 🔍 Step 6: Validate Traffic Filtering

Test access to each VM to confirm NSG rules are working.

![IIS Access](../../assets/images/labs/step06-iis-access.png)  
*Web Server accessible via browser on port 80.*

![RDP Access](../../assets/images/labs/step06-rdp-access.png)  
*Management Server accessible via RDP from admin workstation.*

---

## ✅ Final Validation

Use Azure Network Watcher or connection tests to verify rule enforcement.

![Network Watcher](../../assets/images/labs/step07-network-watcher.png)  
*Network Watcher confirms traffic flow matches NSG rules.*

---

## 🧠 Key Learnings

- ASGs simplify rule management by grouping VMs logically.
- NSGs enforce traffic filtering based on ASG membership.
- Role-based access improves security posture in cloud environments.

---
