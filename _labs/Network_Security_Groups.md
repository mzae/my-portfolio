# 🌐 Lab 02: Network Security Groups & Application Security Groups

**Student:** Daniel Wanjama  
**Lab ID:** ADC-CSS02-25012  
**Program:** Microsoft ADC Cybersecurity Skilling Program  

---

## 🧠 Overview

This lab demonstrates how to secure Azure-based infrastructure using:

- **Network Security Groups (NSGs)** to define traffic rules
- **Application Security Groups (ASGs)** to logically group VMs by role

The objective is to isolate and protect two server roles—**Web Servers** and **Management Servers**—with tailored access controls.

---

## 🛠️ Lab Objectives

- Create virtual networking infrastructure
- Deploy virtual machines (VMs)
- Configure ASGs and NSGs
- Validate traffic filtering

---

## 🏗️ Step-by-Step Walkthrough

### 🔹 1. Create Resource Group

Created a new resource group to contain all lab resources.

📸 **Screenshot 1:** Resource Group creation  
`![Resource Group Creation](assets/lab02/resource-group.png)`

---

### 🔹 2. Create Virtual Network & Subnets

- Created a virtual network named `LabVNet`
- Added two subnets:
  - `WebSubnet` for web servers
  - `MgmtSubnet` for management servers

📸 **Screenshot 2:** Virtual Network and Subnet configuration  
`![Virtual Network Setup](assets/lab02/vnet-subnets.png)`

---

### 🔹 3. Create Application Security Groups (ASGs)

- `WebServers-ASG`: For IIS web servers
- `MgmtServers-ASG`: For remote management VMs

📸 **Screenshot 3:** ASG creation  
`![ASG Creation](assets/lab02/asg-setup.png)`

---

### 🔹 4. Deploy Virtual Machines

#### 🖥️ Web Server VM

- Deployed VM in `WebSubnet`
- Installed IIS
- Assigned to `WebServers-ASG`

📸 **Screenshot 4:** Web Server VM deployment  
`![Web Server VM](assets/lab02/web-vm.png)`

📸 **Screenshot 5:** IIS installation confirmation  
`![IIS Installed](assets/lab02/iis-installed.png)`

#### 🖥️ Management Server VM

- Deployed VM in `MgmtSubnet`
- Assigned to `MgmtServers-ASG`

📸 **Screenshot 6:** Management Server VM deployment  
`![Mgmt Server VM](assets/lab02/mgmt-vm.png)`

---

### 🔹 5. Configure Network Security Groups (NSGs)

#### 🔐 NSG for Web Server

- Allow inbound HTTP (port 80) from internet
- Deny inbound RDP (port 3389)

📸 **Screenshot 7:** NSG rules for Web Server  
`![Web NSG Rules](assets/lab02/web-nsg-rules.png)`

#### 🔐 NSG for Management Server

- Allow inbound RDP (port 3389) from trusted IP
- Deny all other inbound traffic

📸 **Screenshot 8:** NSG rules for Management Server  
`![Mgmt NSG Rules](assets/lab02/mgmt-nsg-rules.png)`

---

### 🔹 6. Associate NSGs with Subnets

Linked NSGs to respective subnets to enforce traffic rules.

📸 **Screenshot 9:** NSG association with subnets  
`![NSG Subnet Association](assets/lab02/nsg-subnet-link.png)`

---

### 🔹 7. Validate Connectivity

- Accessed Web Server via browser to confirm HTTP access
- Attempted RDP to Web Server (denied)
- Successfully connected to Management Server via RDP

📸 **Screenshot 10:** HTTP access to Web Server  
`![Web Server HTTP Access](assets/lab02/http-access.png)`

📸 **Screenshot 11:** RDP denied to Web Server  
`![RDP Denied](assets/lab02/rdp-denied.png)`

📸 **Screenshot 12:** RDP access to Management Server  
`![RDP Success](assets/lab02/rdp-success.png)`

---

## ✅ Key Takeaways

- ASGs simplify rule management by grouping VMs logically
- NSGs enforce traffic control based on server roles
- Security posture improved by minimizing attack surface
- Hands-on experience with Azure-native tools for cloud security

---

## 📁 Portfolio Value

This lab showcases:

- Real-world Azure security configurations
- Role-based access control using NSGs and ASGs
- Practical understanding of cloud infrastructure hardening
- Clean documentation for recruiters and collaborators

---

## 🔗 Related Labs

- [Lab 01: Azure Resource Management](#)
- [Lab 03: Identity & Access Management](#)

---

## 🧾 Author Notes

This walkthrough is part of my cybersecurity lab portfolio.  
For more labs and scripts, visit [my GitHub profile](#).

