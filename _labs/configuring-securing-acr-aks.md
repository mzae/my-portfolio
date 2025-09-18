---
title: "Lab 4: Configuring and Securing ACR and AKS"
layout: lab
permalink: /labs/configuring-securing-acr-aks/
author: Daniel Wanjama
date: 2025-09-18
---

## Introduction

This lab walkthrough documents the configuration and security of Azure Container Registry (ACR) and Azure Kubernetes Service (AKS), including role assignments, firewall rules, DNS settings, and validation steps. It demonstrates real-world cloud security practices using Azure CLI, PowerShell, and the Azure Portal.

---

## Step 1: Launch Cloud Shell and Prepare for AKS Deployment

I began by launching Azure Cloud Shell and reviewing the tutorial instructions for deploying AKS and ACR. This step sets the foundation for the lab.

📸 *Screenshot:*  
![Step 1 – Cloud Shell and AKS Setup](../../assets/images/labs//step01-cloudshell-aks-setup.png)

---

## Step 2: Troubleshoot Deployment Policy Restriction

While deploying the AKS cluster, I encountered a policy error due to location restrictions. Azure Policy blocked the resource creation, which I resolved by selecting an approved region.

📸 *Screenshot:*  
![Step 2 – Deployment Policy Error](../../assets/images/labs/step02-policy-error.png)

---

## Step 3: View Resource Groups in Azure Portal

I reviewed existing resource groups to confirm the correct environment and subscription context before proceeding with cluster and registry setup.

📸 *Screenshot:*  
![Step 3 – Resource Groups Overview](../../assets/images/labs/step03-resource-groups-list.png)

---

## Step 4: Assign AcrPull Role to AKS Identity

To allow AKS to pull images from ACR securely, I assigned the `AcrPull` role to the cluster’s managed identity using the Azure Portal.

📸 *Screenshot:*  
![Step 4 – AcrPull Role Assignment](../../assets/images/labs/step04-role-assignment-acrpull.png)

---

## Step 5: Configure Azure Firewall Application Rule

I created an application rule collection named `AllowGvn` to permit outbound HTTPS access to specific domains like Google and Bing.

📸 *Screenshot:*  
![Step 5 – Firewall Application Rule](../../assets/images/labs/step05-firewall-application-rule.png)

---

## Step 6: Add Network Rule Collection

To control internal traffic, I added a network rule collection that allows UDP traffic between defined IP ranges and ports.

📸 *Screenshot:*  
![Step 6 – Network Rule Collection](../../assets/images/labs/step06-network-rule-udp.png)

---

## Step 7: Configure Custom DNS Servers

I configured custom DNS servers (Google and Cloudflare) on the `nic-firewall` network interface to ensure reliable name resolution.

📸 *Screenshot:*  
![Step 7 – Custom DNS Settings](../../assets/images/labs/step07-dns-settings-nic-firewall.png)

---

## Step 8: Validate Firewall Rules from Test VM

Using `nslookup` and `curl` from the test VM, I validated that outbound traffic was correctly routed through Azure Firewall.

📸 *Screenshot:*  
![Step 8 – Firewall Validation from VM](../../assets/images/labs/step08-firewall-validation-terminal.png)

---

## Step 9: Create Virtual Network and Subnets

I created a virtual network named `FirewallVNet` with three subnets: `AzureFirewallSubnet`, `Workload-SN`, and `Jump-SN`, to segment traffic and enforce security boundaries.

📸 *Screenshot:*  
![Step 9 – VNet and Subnets](../../assets/images/labs/step09-server-manager-vnet-subnets.png)

---

## Step 10: Test Access to Workload VM

I logged into the workload VM (`rsrv-lwrk`) via Remote Desktop and confirmed connectivity and profile loading.

📸 *Screenshot:*  
![Step 10 – RDP Login to Workload VM](../../assets/images/labs/step10-rdp-login-profile-service.png)

---

## Step 11: Confirm Public IP Routing via Browser

From the VM, I browsed to `http://10.0.1.4` and `http://10.0.2.4` to test firewall rules. The first succeeded, the second was blocked — confirming rule enforcement.

📸 *Screenshot:*  
![Step 11 – Public IP Validation](../../assets/images/labs/step11-server-manager-ip-check.png)

---

## Step 12: Terminate Remote Desktop Sessions and Begin Cleanup

After validation, I terminated all RDP sessions and began resource cleanup to avoid unnecessary charges.

📸 *Screenshot:*  
![Step 12 – Session Termination and Cleanup](../../assets/images/labs/step12-rdp-session-termination.png)

---

## Step 13: Create Resource Group via PowerShell

Using Azure Cloud Shell, I created a new resource group named `AZ500LabRG`.

```powershell
New-AzResourceGroup -Name "AZ500LabRG" -Location "East US"
```

📸 *Screenshot:*  
![Step 13 – Create Resource Group](../../assets/images/labs/step13-cloudshell-create-rg.png)

---

## Step 14: Remove AzureFirewallRG via PowerShell

I removed the `AzureFirewallRG` resource group using PowerShell to clean up lab resources.

```powershell
Remove-AzResourceGroup -Name AzureFirewallRG -Force -AsJob
```

📸 *Screenshot:*  
![Step 14 – Remove Resource Group](../../assets/images/labs/step14-cloudshell-remove-rg.png)

---

## Step 15: Verify Azure Firewall Deployment

Finally, I verified the Azure Firewall deployment status using PowerShell.

```powershell
Get-AzFirewall -ResourceGroupName AzureResourceGroup
```

📸 *Screenshot:*  
![Step 15 – Firewall Status Verified](../../assets/images/labs/step15-get-firewall-status.png)

---

## Conclusion

This lab demonstrates end-to-end deployment and security configuration for ACR and AKS, including:

- Role-based access control  
- DNS and firewall rule enforcement  
- Network segmentation  
- Real-world validation from VMs  
- Resource cleanup using PowerShell

It reflects my ability to troubleshoot, automate, and document technical workflows in a cloud security context.

---
Let me know if you'd like help generating a sidebar link, `_data/labs.yml` entry, or a landing page summary. You're ready to publish this as a top-tier portfolio piece.
