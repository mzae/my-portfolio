---
title: "Azure Firewall Configuration and Testing"
layout: lab
author: Wanjama Daniel
permalink: /labs/azure-firewall/
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

![ARM template showing successful deployment of virtual network, subnets, and firewall resources](../../assets/images/labs/task1-arm-template-deployment.png)
*ARM template deployment overview*

---

### Task 2: Deploy Azure Firewall

- Navigated to **Firewall Manager**
- Created Azure Firewall in the designated subnet
- Verified firewall provisioning status

![Azure Firewall creation interface showing successful provisioning and configuration](../../assets/images/labs/task2-firewall-deployment.png)
*Azure Firewall creation*

---

### Task 3: Configure Default Route (UDR)

- Created User Defined Route to redirect traffic through firewall
- Associated route table with subnet

![User Defined Route configuration showing traffic redirection to Azure Firewall](../../assets/images/labs/task3-udr-creation.png)
*UDR configuration*

![Route table association demonstrating subnet-level routing policies](../../assets/images/labs/task3-route-table-association.png)
*Route table association*

---

### Task 4: Create Application Rules

- Defined Layer 7 rules for FQDN-based access
- Allowed traffic to `*.microsoft.com` and `*.github.com`

![Application rule configuration showing FQDN-based filtering for allowed domains](../../assets/images/labs/task4-application-rules.png)
*Application rule configuration*

---

### Task 5: Create Network Rules

- Configured Layer 3/4 rules for IP and port-based access
- Allowed TCP traffic on port 443 to specific IP ranges

![Network rule setup showing TCP port 443 filtering for specific IP ranges](../../assets/images/labs/task5-network-rules.png)
*Network rule setup*

---

### Task 6: Configure DNS Server

- Enabled DNS proxy on Azure Firewall
- Verified DNS resolution for outbound traffic

![DNS proxy configuration interface showing enabled DNS proxy settings](../../assets/images/labs/task6-dns-settings.png)
*DNS proxy configuration*

---

### Task 7: Test Firewall Functionality

- Validated access to allowed domains
- Confirmed blocked traffic for unauthorized destinations
- Used VM browser and command-line tools for testing

![Successful access test showing allowed traffic to whitelisted domains](../../assets/images/labs/task7-allowed-traffic-test.png)
*Successful access test*

![Blocked traffic confirmation demonstrating firewall blocking unauthorized access](../../assets/images/labs/task7-blocked-traffic-test.png)
*Blocked traffic confirmation*

---

## Summary

This lab successfully demonstrated Azure Firewall deployment, configuration, and testing. All application and network rules were properly configured and validated, demonstrating centralized security enforcement.

---

## References

- [Azure Firewall Documentation](https://learn.microsoft.com/en-us/azure/firewall/)
- [User Defined Routes](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-udr-overview)
- [Application and Network Rules](https://learn.microsoft.com/en-us/azure/firewall/rule-processing)
