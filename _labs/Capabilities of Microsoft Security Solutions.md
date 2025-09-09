---
title: "Capabilities of Microsoft Security Solutions"
layout: lab
date: 2025-08-27
author: Daniel Wanjama
---

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

---

## Introduction

This lab explores Microsoft’s cloud security tools, including Microsoft 365 tenant setup, Azure Network Security Groups (NSGs), Microsoft Defender for Cloud, Microsoft Sentinel, and Microsoft Defender for Cloud Apps. Each tool plays a critical role in protecting identities, networks, applications, and data in Azure cloud environments. The lab provides hands-on experience in configuring and managing these security solutions to ensure robust protection against evolving threats.

---

## Objectives

- Understand and configure Azure Network Security Groups for traffic control.  
- Explore Microsoft Defender for Cloud to assess and improve security posture.  
- Set up Microsoft Sentinel for threat detection and response.  
- Investigate app governance using Microsoft Defender for Cloud Apps.  

---

## Prerequisites

- An active Azure subscription.  
- Basic knowledge of Azure Portal, virtual networks, and Microsoft 365.  
- Access to Azure Cloud Shell or PowerShell for command-line tasks.  

---

## Walkthrough

### Lab 1: Azure Network Security Groups (NSGs)

#### Task 1: View VM Details
1. Log in to the Azure Portal.  
2. Locate the pre-created virtual machine (VM) in the portal.  
3. Review the VM’s configuration and network interface settings.  

![Viewing VM details](../../assets/images/labs/lab1-nsg-task1-vm-details.png)

---

#### Task 2: Create NSG and Add RDP Rule
1. Navigate to **Network security groups > Create**.  
2. Create a new NSG named **NSG-SC900**.  
3. Associate it with the VM’s network interface card (NIC).  
4. Add an inbound rule to allow RDP (port 3389).  

![Creating NSG](../../assets/images/labs/lab1-nsg-task2-create-nsg.png)  
![Adding RDP rule](../../assets/images/labs/lab1-nsg-task2-add-rdp-rule.png)

---

#### Task 3: Test RDP and Outbound Access
1. Use the **Check Access** feature to verify RDP connectivity.  
2. Connect to the VM via Native RDP and test outbound internet access (e.g., browsing a website).  

![Testing RDP connectivity](../../assets/images/labs/lab1-nsg-task3-rdp-connectivity-test.png)  
![Testing outbound access](../../assets/images/labs/lab1-nsg-task3-outbound-access-check.png)

---

#### Task 4: Block Outbound Internet
1. Create an outbound rule in **NSG-SC900** to deny traffic to the Internet service tag.  
2. Test by attempting to access `www.bing.com` from the VM (access should fail).  

![Blocking outbound internet rule](../../assets/images/labs/lab1-nsg-task4-block-outbound-rule.png)  
![Testing blocked access](../../assets/images/labs/lab1-nsg-task4-test-blocked-access.png)

---

### Lab 2: Microsoft Defender for Cloud

#### Task 1: Explore Defender Dashboard
1. Navigate to **Microsoft Defender for Cloud** in the Azure Portal.  
2. Review the secure score, assessed resources, and security recommendations.  

![Defender for Cloud dashboard](../../assets/images/labs/lab2-defender-overview.png)

---

#### Task 2: Review Recommendations
1. Select a VM resource and view remediation steps for identified security issues.  

![Security recommendations](../../assets/images/labs/lab2-defender-security-recommendations.png)

---

#### Task 3: Enable Defender Plans
1. Enable the Cloud Security Posture Management (CSPM) and Server protection plans.  

![Enabling Defender plans](../../assets/images/labs/lab2-defender-enable-plans.png)

---

### Lab 3: Microsoft Sentinel

#### Task 1: Create Sentinel Instance
1. Create a Log Analytics workspace named **SC900-LogAnalytics-workspace**.  
2. Enable **Microsoft Sentinel** in the workspace.  

![Creating Sentinel instance](../../assets/images/labs/lab3-sentinel-task1-create-instance.png)

---

#### Task 2: Assign Roles
1. In the resource group **SC900-Sentinel-RG**, assign built-in Sentinel roles via Identity and Access Management (IAM).  

![Assigning Sentinel roles](../../assets/images/labs/lab3-sentinel-task2-role-assignment.png)

---

#### Task 3: Connect Defender for Cloud
1. Navigate to **Content Hub** in Microsoft Sentinel.  
2. Deploy the **Defender for Cloud** solution and configure the connector.  
3. Verify alert ingestion from Defender for Cloud.  

![Accessing Content Hub](../../assets/images/labs/lab3-sentinel-task3-connect-content-hub.png)  
![Deploying Defender solution](../../assets/images/labs/lab3-sentinel-task3-defender-solution-deploy.png)

---

### Lab 4: Microsoft Defender for Cloud Apps

#### Task 1: Explore Cloud Discovery
1. Access the **Microsoft 365 Defender** portal.  
2. Navigate to the **Cloud Discovery** dashboard to review discovered apps.  

![Cloud Discovery dashboard](../../assets/images/labs/lab4-defender-apps-cloud-discovery.png)

---

#### Task 2: Review App Catalog
1. View discovered apps, their risk scores, and usage statistics in the app catalog.  

![Reviewing app catalog](../../assets/images/labs/lab4-defender-apps-app-catalog.png)

---

#### Task 3: Investigate Findings
1. Use investigation tools and filters to analyze app-related findings.  

![Investigation tools](../../assets/images/labs/lab4-defender-apps-investigation-tools.png)

---

#### Task 4: Configure Policies
1. Tag apps as sanctioned or unsanctioned.  
2. Enable file monitoring under **Information Protection**.  

![Configuring policy controls](../../assets/images/labs/lab4-defender-apps-policy-controls.png)

---

