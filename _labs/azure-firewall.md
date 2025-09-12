---
title: "Azure Firewall Configuration and Testing"
layout: lab
permalink: /labs/azure-firewall/
author: Daniel Wanjama
date: 2025-09-12
---

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

---

## Introduction

This lab explores the deployment and configuration of Azure Firewall using the Learn on Demand portal. Azure Firewall provides centralized, scalable, and stateful network security for cloud environments. The lab covers key tasks including firewall deployment, routing, rule creation, DNS setup, and traffic validation.

---

## Objectives

- Deploy Azure Firewall using an ARM template  
- Configure User Defined Routes (UDRs)  
- Create application and network rules  
- Set up DNS server integration  
- Test firewall functionality  

---

## Prerequisites

- Skillable lab access  
- Azure subscription with admin privileges  
- Familiarity with virtual networks and routing  

---

## Walkthrough

### Task 1: Deploy Lab Environment

- Used ARM template to provision virtual network, subnets, and resources  
- Verified deployment via Azure Portal  

📸 *Screenshot: `task1-arm-template-deployment.png` – ARM template deployment overview*  
[![ARM Deployment](../../assets/images/labs/task1-arm-template-deployment.png)](../../assets/images/labs/task1-arm-template-deployment.png)

---

### Task 2: Deploy Azure Firewall

- Navigated to **Firewall Manager**  
- Created Azure Firewall in the designated subnet  
- Verified firewall provisioning status  

📸 *Screenshot: `task2-firewall-deployment.png` – Azure Firewall creation*  
[![Firewall Deployment](../../assets/images/labs/task2-firewall-deployment.png)](../../assets/images/labs/task2-firewall-deployment.png)

---

### Task 3: Configure Default Route (UDR)

- Created User Defined Route to redirect traffic through firewall  
- Associated route table with subnet  

📸 *Screenshot: `task3-udr-creation.png` – UDR configuration*  
[![UDR Setup](../../assets/images/labs/task3-udr-creation.png)](../../assets/images/labs/task3-udr-creation.png)  
📸 *Screenshot: `task3-route-table-association.png` – Route table association*  
[![Route Table](../../assets/images/labs/task3-route-table-association.png)](../../assets/images/labs/task3-route-table-association.png)

---

### Task 4: Create Application Rules

- Defined Layer 7 rules for FQDN-based access  
- Allowed traffic to `*.microsoft.com` and `*.github.com`  

📸 *Screenshot: `task4-application-rules.png` – Application rule configuration*  
[![App Rules](../../assets/images/labs/task4-application-rules.png)](../../assets/images/labs/task4-application-rules.png)

---

### Task 5: Create Network Rules

- Configured Layer 3/4 rules for IP and port-based access  
- Allowed TCP traffic on port 443 to specific IP ranges  

📸 *Screenshot: `task5-network-rules.png` – Network rule setup*  
[![Network Rules](../../assets/images/labs/task5-network-rules.png)](../../assets/images/labs/task5-network-rules.png)

---

### Task 6: Configure DNS Server

- Enabled DNS proxy on Azure Firewall  
- Verified DNS resolution for outbound traffic  

📸 *Screenshot: `task6-dns-settings.png` – DNS proxy configuration*  
[![DNS Settings](../../assets/images/labs/task6-dns-settings.png)](../../assets/images/labs/task6-dns-settings.png)

---

### Task 7: Test Firewall Functionality

- Validated access to allowed domains  
- Confirmed blocked traffic for unauthorized destinations  
- Used VM browser and command-line tools for testing  

📸 *Screenshot: `task7-allowed-traffic-test.png` – Successful access test*  
[![Allowed Test](../../assets/images/labs/task7-allowed-traffic-test.png)](../../assets/images/labs/task7-allowed-traffic-test.png)  
📸 *Screenshot: `task7-blocked-traffic-test.png` – Blocked traffic confirmation*  
[![Blocked Test](../../assets/images/labs/task7-blocked-traffic-test.png)](../../assets/images/labs/task7-blocked-traffic-test.png)

---

## Conclusion

This lab provided hands-on experience with Azure Firewall, covering deployment, routing, rule creation, DNS configuration, and traffic validation. By completing these tasks, I gained practical insight into securing cloud networks using Azure-native tools. The ability to enforce granular access policies and validate traffic flow is essential for maintaining a secure and compliant cloud infrastructure.

---

Let me know if you'd like a reusable template for future labs or a script to automate screenshot renaming and folder structuring. I can also help you generate a sidebar navigation entry for this lab in your GitHub Pages site.
