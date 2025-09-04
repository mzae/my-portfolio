---
title: Service Endpoints and Securing Storage  
layout: default  
date: 2025-09-04  
---

# Lab 6: Service Endpoints and Securing Storage

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

---

## Introduction

This walkthrough guides you through Lab 06 of the Microsoft ADC Cybersecurity Skilling Program, focusing on securing Azure Storage using Service Endpoints and Network Security Groups (NSGs). You'll restrict access to storage accounts via virtual network subnets, ensuring traffic stays within the Azure backbone.

---

## Objectives

- Configure Azure Service Endpoints for a storage account  
- Set up Network Security Groups to control subnet access  
- Deploy virtual machines in isolated subnets to test connectivity  
- Validate secure access to Azure Storage  

---

## Prerequisites

- Active Azure subscription  
- Familiarity with Azure Portal, virtual networks, and storage accounts  
- Access to Azure Cloud Shell or PowerShell  

---

## Walkthrough

### 🗂️ Step 1: Create a Storage Account

1. Log in to [Azure Portal](https://portal.azure.com)  
2. Navigate to **Storage accounts** → **Create**  
3. Fill in:
   - **Subscription**: Your active subscription  
   - **Resource group**: `Lab06-RG`  
   - **Storage account name**: `lab06storage`  
   - **Region**: East US  
   - **Performance**: Standard  
   - **Redundancy**: LRS  
4. Click **Create**  
**Screenshot:**  
`![lab6_page12.png](/assets/images/labs/lab6_page12.png)`  
*Caption: Creating storage account basics*

---

### 🌐 Step 2: Create a Virtual Network

... *(and so on for each step, matching the formatting of your IAM lab)*

---

## Conclusion

This lab demonstrated how to secure Azure Storage using Service Endpoints and NSGs. By isolating access through subnets and enforcing firewall rules, you ensured that only trusted resources could connect. These configurations are essential for building secure, compliant cloud architectures.

---

## References

- [Azure Storage Security](https://learn.microsoft.com/en-us/azure/storage/common/storage-network-security)  
- [Microsoft Learn: Virtual Networks](https://learn.microsoft.com/en-us/azure/virtual-network/)  
```
