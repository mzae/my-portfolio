---
title: Service Endpoints and Securing Storage
layout: lab
author: Wanjama Daniel
date: 2025-09-04
permalink: /labs/service-endpoints-and-securing-storage/
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
![Creating storage account basics showing subscription, resource group, and storage account configuration](../../assets/images/labs/lab6_page12.png)
*Caption: Creating storage account basics*

---

### 🌐 Step 2: Create a Virtual Network

1. Navigate to **Virtual networks** → **Create**
2. Configure:
   - **Name**: `Lab06-VNet`
   - **Resource group**: `Lab06-RG`
   - **Region**: East US
3. Create subnets:
   - **Subnet-1**: `10.0.1.0/24` (default)
   - **Subnet-2**: `10.0.2.0/24` (for isolated access)
4. Click **Create**

**Screenshot:**
![Virtual network creation with subnet configuration for Lab 06](../../assets/images/labs/lab6_page13.png)
*Caption: Creating virtual network and subnets*

---

### 🔐 Step 3: Configure Service Endpoint

1. Open the storage account created in Step 1
2. Navigate to **Networking** → **Firewalls and virtual networks**
3. Select **Selected networks**
4. Click **Add existing virtual network**
5. Select `Lab06-VNet` and `Subnet-1`
6. Enable **Service Endpoint** for **Microsoft.Storage**
7. Click **Add**

**Screenshot:**
![Service endpoint configuration showing virtual network and subnet selection](../../assets/images/labs/lab6_page14.png)
*Caption: Enabling Service Endpoint for storage account*

---

### 🚀 Step 4: Deploy Virtual Machines

1. Create two VMs:
   - **VM-Allowed**: In `Subnet-1` (has service endpoint access)
   - **VM-Denied**: In `Subnet-2` (no service endpoint)

2. Configure networking:
   - Assign to respective subnets
   - Enable RDP access

**Screenshot:**
![Virtual machine deployment in Lab06-VNet with subnet assignment](../../assets/images/labs/lab6_page15.png)
*Caption: Deploying VMs in isolated subnets*

---

### ✅ Step 5: Validate Secure Access

1. RDP into **VM-Allowed**
2. Attempt to access storage account using `az storage account show`
3. Verify successful access
4. RDP into **VM-Denied**
5. Attempt the same access - should fail

**Screenshots:**
![Successful storage account access from VM-Allowed in subnet with service endpoint](../../assets/images/labs/lab6_page16.png)
*Caption: VM-Allowed successfully accessing storage account*

![Access denied error when attempting to access storage from VM-Denied](../../assets/images/labs/lab6_page17.png)
*Caption: VM-Denied blocked from accessing storage account*

---

## Conclusion

This lab demonstrated how to secure Azure Storage using Service Endpoints and NSGs. By isolating access through subnets and enforcing firewall rules, you ensured that only trusted resources could connect. These configurations are essential for building secure, compliant cloud architectures.

---

## References

- [Azure Storage Security](https://learn.microsoft.com/en-us/azure/storage/common/storage-network-security)
- [Microsoft Learn: Virtual Networks](https://learn.microsoft.com/en-us/azure/virtual-network/)
- [Service Endpoints](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview)
