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

![ARM template deployment overview](../../assets/images/labs/task1-arm-template-deployment.png)

---

### Task 2: Deploy Azure Firewall

- Navigated to **Firewall Manager**  
- Created Azure Firewall in the designated subnet  
- Verified firewall provisioning status  

![Azure Firewall creation](../../assets/images/labs/task2-firewall-deployment.png)

---

### Task 3: Configure Default Route (UDR)

- Created User Defined Route to redirect traffic through firewall  
- Associated route table with subnet  

![UDR configuration](../../assets/images/labs/task3-udr-creation.png)  
![Route table association](../../assets/images/labs/task3-route-table-association.png)

---

### Task 4: Create Application Rules

- Defined Layer 7 rules for FQDN-based access  
- Allowed traffic to `*.microsoft.com` and `*.github.com`  

![Application rule configuration](../../assets/images/labs/task4-application-rules.png)

---

### Task 5: Create Network Rules

- Configured Layer 3/4 rules for IP and port-based access  
- Allowed TCP traffic on port 443 to specific IP ranges  

![Network rule setup](../../assets/images/labs/task5-network-rules.png)

---

### Task 6: Configure DNS Server

- Enabled DNS proxy on Azure Firewall  
- Verified DNS resolution for outbound traffic  

![DNS proxy configuration](../../assets/images/labs/task6-dns-settings.png)

---

### Task 7: Test Firewall Functionality

- Validated access to allowed domains  
- Confirmed blocked traffic for unauthorized destinations  
- Used VM browser and command-line tools for testing  

![Successful access test](../../assets/images/labs/task7-allowed-traffic-test.png)  
![Blocked traffic confirmation](../../assets/images/labs/task7-blocked-traffic-test.png)

---
