---
title: Capabilities of Microsoft Security Solutions
layout: single
date: 2025-08-27
author: Daniel Wanjama
---

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

## Introduction

This lab explores Microsoft’s cloud security tools, including Microsoft 365 tenant setup, Azure Network Security Groups (NSGs), Microsoft Defender for Cloud, Microsoft Sentinel, and Microsoft Defender for Cloud Apps. Each tool plays a critical role in protecting identities, networks, applications, and data in Azure cloud environments. The lab provides hands-on experience in configuring and managing these security solutions to ensure robust protection against evolving threats.

**Objectives:**
- Understand and configure Azure Network Security Groups for traffic control.
- Explore Microsoft Defender for Cloud to assess and improve security posture.
- Set up Microsoft Sentinel for threat detection and response.
- Investigate app governance using Microsoft Defender for Cloud Apps.

## Prerequisites
- An active Azure subscription.
- Basic knowledge of Azure Portal, virtual networks, and Microsoft 365.
- Access to Azure Cloud Shell or PowerShell for command-line tasks.

## Walkthrough

### Lab 1: Azure Network Security Groups (NSGs)

#### Task 1: View VM Details
1. Log in to the [Azure Portal](https://portal.azure.com).
2. Locate the pre-created virtual machine (VM) in the portal.
3. Review the VM’s configuration and network interface settings.
   - *Screenshot: [lab1-nsg-task1-vm-details.png](/assets/images/labs/lab1-nsg-task1-vm-details.png) - Viewing VM details.*

#### Task 2: Create NSG and Add RDP Rule
1. Navigate to **Network security groups** > **Create**.
2. Create a new NSG named `NSG-SC900`.
3. Associate it with the VM’s network interface card (NIC).
4. Add an inbound rule to allow RDP (port `3389`).
   - *Screenshot: [lab1-nsg-task2-create-nsg.png](/assets/images/labs/lab1-nsg-task2-create-nsg.png) - Creating NSG.*
   - *Screenshot: - ![Adding RDP rule](/assets/images/labs/lab1-nsg-task2-add-rdp-rule.png)- Adding RDP rule.*

#### Task 3: Test RDP and Outbound Access
1. Use the **Check Access** feature to verify RDP connectivity.
2. Connect to the VM via Native RDP and test outbound internet access (e.g., browsing a website).
   - *Screenshot: [lab1-nsg-task3-rdp-connectivity-test.png](/assets/images/labs/lab1-nsg-task3-rdp-connectivity-test.png) - Testing RDP connectivity.*
   - *Screenshot: [lab1-nsg-task3-outbound-access-check.png](/assets/images/labs/lab1-nsg-task3-outbound-access-check.png) - Testing outbound access.*

#### Task 4: Block Outbound Internet
1. Create an outbound rule in `NSG-SC900` to deny traffic to the `Internet` service tag.
2. Test by attempting to access `www.bing.com` from the VM (access should fail).
   - *Screenshot: [lab1-nsg-task4-block-outbound-rule.png](/assets/images/labs/lab1-nsg-task4-block-outbound-rule.png) - Blocking outbound internet rule.*
   - *Screenshot: [lab1-nsg-task4-test-blocked-access.png](/assets/images/labs/lab1-nsg-task4-test-blocked-access.png) - Testing blocked access.*

### Lab 2: Microsoft Defender for Cloud

#### Task 1: Explore Defender Dashboard
1. Navigate to **Microsoft Defender for Cloud** in the Azure Portal.
2. Review the secure score, assessed resources, and security recommendations.
   - *Screenshot: [lab2-defender-overview.png](/assets/images/labs/lab2-defender-overview.png) - Defender for Cloud dashboard.*

#### Task 2: Review Recommendations
1. Select a VM resource and view remediation steps for identified security issues.
   - *Screenshot: [lab2-defender-security-recommendations.png](/assets/images/labs/lab2-defender-security-recommendations.png) - Security recommendations.*

#### Task 3: Enable Defender Plans
1. Enable the Cloud Security Posture Management (CSPM) and Server protection plans.
   - *Screenshot: [lab2-defender-enable-plans.png](/assets/images/labs/lab2-defender-enable-plans.png) - Enabling Defender plans.*

### Lab 3: Microsoft Sentinel

#### Task 1: Create Sentinel Instance
1. Create a Log Analytics workspace named `SC900-LogAnalytics-workspace`.
2. Enable Microsoft Sentinel in the workspace.
   - *Screenshot: [lab3-sentinel-task1-create-instance.png](/assets/images/labs/lab3-sentinel-task1-create-instance.png) - Creating Sentinel instance.*

#### Task 2: Assign Roles
1. In the resource group `SC900-Sentinel-RG`, assign built-in Sentinel roles via Identity and Access Management (IAM).
   - *Screenshot: [lab3-sentinel-task2-role-assignment.png](/assets/images/labs/lab3-sentinel-task2-role-assignment.png) - Assigning Sentinel roles.*

#### Task 3: Connect Defender for Cloud
1. Navigate to **Content Hub** in Microsoft Sentinel.
2. Deploy the Defender for Cloud solution and configure the connector.
3. Verify alert ingestion from Defender for Cloud.
   - *Screenshot: [lab3-sentinel-task3-connect-content-hub.png](/assets/images/labs/lab3-sentinel-task3-connect-content-hub.png) - Accessing Content Hub.*
   - *Screenshot: [lab3-sentinel-task3-defender-solution-deploy.png](/assets/images/labs/lab3-sentinel-task3-defender-solution-deploy.png) - Deploying Defender solution.*

### Lab 4: Microsoft Defender for Cloud Apps

#### Task 1: Explore Cloud Discovery
1. Access the Microsoft 365 Defender portal.
2. Navigate to the **Cloud Discovery** dashboard to review discovered apps.
   - *Screenshot: [lab4-defender-apps-cloud-discovery.png](/assets/images/labs/lab4-defender-apps-cloud-discovery.png) - Cloud Discovery dashboard.*

#### Task 2: Review App Catalog
1. View discovered apps, their risk scores, and usage statistics in the app catalog.
   - *Screenshot: [lab4-defender-apps-app-catalog.png](/assets/images/labs/lab4-defender-apps-app-catalog.png) - Reviewing app catalog.*

#### Task 3: Investigate Findings
1. Use investigation tools and filters to analyze app-related findings.
   - *Screenshot: [lab4-defender-apps-investigation-tools.png](/assets/images/labs/lab4-defender-apps-investigation-tools.png) - Investigation tools.*

#### Task 4: Configure Policies
1. Tag apps as sanctioned or unsanctioned.
2. Enable file monitoring under **Information Protection**.
   - *Screenshot: [lab4-defender-apps-policy-controls.png](/assets/images/labs/lab4-defender-apps-policy-controls.png) - Configuring policy controls.*

## Conclusion

This lab provided hands-on experience with Microsoft’s cloud security ecosystem, including Azure Network Security Groups, Microsoft Defender for Cloud, Microsoft Sentinel, and Microsoft Defender for Cloud Apps. Key takeaways include:
- Configuring NSGs to control network traffic and enforce security policies.
- Using Defender for Cloud to assess and improve security posture through recommendations.
- Setting up Sentinel for centralized threat detection and response.
- Governing cloud apps with Defender for Cloud Apps to ensure compliance and data protection.

These tools collectively form a layered security approach, protecting Azure environments from evolving threats. The skills gained are directly applicable to real-world scenarios, strengthening my expertise in Azure cloud security.

*Note: Place this Markdown file in the `_labs` directory as `Capabilities_of_Microsoft_Security_Solutions.md`. Ensure screenshots are saved in `assets/images/labs/` with the referenced filenames (e.g., `lab1-nsg-task1-vm-details.png`).*



