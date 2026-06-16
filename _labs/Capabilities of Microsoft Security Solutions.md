---
title: "Capabilities of Microsoft Security Solutions"
layout: lab
author: Wanjama Daniel
permalink: /labs/capabilities-microsoft-security-solutions/
date: 2025-09-12
---

## Introduction

This lab explores key Microsoft security solutions including Network Security Groups (NSGs), Microsoft Defender for Cloud, Microsoft Sentinel, and Microsoft Defender for Cloud Apps. Through hands-on configuration and testing, I demonstrated how these tools work together to provide comprehensive cloud security across Azure environments.

---

## Objectives

- Configure NSGs to control network traffic
- Deploy and configure Microsoft Defender for Cloud
- Set up Microsoft Sentinel for threat detection
- Explore Microsoft Defender for Cloud Apps capabilities
- Validate security policies and remediation workflows

---

## Prerequisites

- Azure subscription with admin access
- Skillable lab environment
- Familiarity with Azure Portal and security concepts

---

## Walkthrough

### Lab 1: Network Security Groups

#### Task 1: Create NSG and Rules
1. Create NSG named **NSG-SC900**
2. Add inbound rule to allow RDP (port 3389) from specific source
3. Add outbound rule to block internet traffic

![NSG creation interface showing rule configuration for RDP access and outbound filtering](../../assets/images/labs/lab1-nsg-task1-create-nsg.png)
*Creating NSG with RDP rule*

---

#### Task 2: Associate NSG with Subnet
1. Navigate to virtual network
2. Select subnet for VM deployment
3. Associate **NSG-SC900**
4. Verify association status

![NSG association interface showing subnet selection and successful firewall rule binding](../../assets/images/labs/lab1-nsg-task2-associate-subnet.png)
*Associating NSG with subnet*

---

#### Task 3: Test NSG Rules
1. Deploy VM in protected subnet
2. Test RDP connectivity (should succeed)
3. Test outbound internet access (should fail)

![Network connectivity testing showing RDP success and internet access blocked](../../assets/images/labs/lab1-nsg-task3-rdp-connectivity-test.png)
*Testing RDP connectivity*

![Outbound access test demonstrating blocked internet traffic enforcement](../../assets/images/labs/lab1-nsg-task3-outbound-access-check.png)
*Testing outbound access*

---

#### Task 4: Block Outbound Internet
1. Create an outbound rule in **NSG-SC900** to deny traffic to the Internet service tag
2. Test by attempting to access `www.bing.com` from the VM (access should fail)

![Outbound deny rule configuration showing Internet service tag blocking](../../assets/images/labs/lab1-nsg-task4-block-outbound-rule.png)
*Blocking outbound internet rule*

![Browser test showing blocked access to bing.com via NSG rule enforcement](../../assets/images/labs/lab1-nsg-task4-test-blocked-access.png)
*Testing blocked access*

---

### Lab 2: Microsoft Defender for Cloud

#### Task 1: Explore Defender Dashboard
1. Navigate to **Microsoft Defender for Cloud** in the Azure Portal
2. Review the secure score, assessed resources, and security recommendations

![Defender for Cloud dashboard showing secure score and resource assessment summary](../../assets/images/labs/lab2-defender-overview.png)
*Defender for Cloud dashboard*

---

#### Task 2: Review Recommendations
1. Select a VM resource and view remediation steps for identified security issues

![Security recommendations interface showing remediation steps and risk severity levels](../../assets/images/labs/lab2-defender-security-recommendations.png)
*Security recommendations*

---

#### Task 3: Enable Defender Plans
1. Enable the Cloud Security Posture Management (CSPM) and Server protection plans

![Defender for Cloud plans configuration showing CSPM and server protection enablement](../../assets/images/labs/lab2-defender-enable-plans.png)
*Enabling Defender plans*

---

### Lab 3: Microsoft Sentinel

#### Task 1: Create Sentinel Instance
1. Create a Log Analytics workspace named **SC900-LogAnalytics-workspace**
2. Enable **Microsoft Sentinel** in the workspace

![Log Analytics workspace and Sentinel creation interface showing successful provisioning](../../assets/images/labs/lab3-sentinel-task1-create-instance.png)
*Creating Sentinel instance*

---

#### Task 2: Assign Roles
1. In the resource group **SC900-Sentinel-RG**, assign built-in Sentinel roles via Identity and Access Management (IAM)

![IAM role assignment interface showing Sentinel contributor and viewer role options](../../assets/images/labs/lab3-sentinel-task2-role-assignment.png)
*Assigning Sentinel roles*

---

#### Task 3: Connect Defender for Cloud
1. Navigate to **Content Hub** in Microsoft Sentinel
2. Deploy the **Defender for Cloud** solution and configure the connector
3. Verify alert ingestion from Defender for Cloud

![Sentinel Content Hub showing Defender for Cloud solution deployment interface](../../assets/images/labs/lab3-sentinel-task3-connect-content-hub.png)
*Accessing Content Hub*

![Defender for Cloud solution deployment in Microsoft Sentinel showing connector configuration](../../assets/images/labs/lab3-sentinel-task3-defender-solution-deploy.png)
*Deploying Defender solution*

---

### Lab 4: Microsoft Defender for Cloud Apps

#### Task 1: Explore Cloud Discovery
1. Access the **Microsoft 365 Defender** portal
2. Navigate to the **Cloud Discovery** dashboard to review discovered apps

![Cloud Discovery dashboard showing discovered applications and risk assessment data](../../assets/images/labs/lab4-defender-apps-cloud-discovery.png)
*Cloud Discovery dashboard*

---

#### Task 2: Review App Catalog
1. View discovered apps, their risk scores, and usage statistics in the app catalog

![App catalog interface showing cloud application risk scores and usage metrics](../../assets/images/labs/lab4-defender-apps-app-catalog.png)
*Reviewing app catalog*

---

#### Task 3: Investigate Findings
1. Use investigation tools and filters to analyze app-related findings

![Investigation tools interface showing filtering options and app analysis capabilities](../../assets/images/labs/lab4-defender-apps-investigation-tools.png)
*Investigation tools*

---

#### Task 4: Configure Policies
1. Create Cloud Discovery anomaly detection policy
2. Set alert thresholds and notification preferences

---

## Summary

This lab successfully demonstrated Microsoft's comprehensive security solutions. NSGs provided network-level protection, Defender for Cloud assessed security posture, Sentinel enabled threat detection, and Defender for Cloud Apps monitored cloud application risks.

---

## References

- [Network Security Groups](https://learn.microsoft.com/en-us/azure/virtual-network/network-security-groups-overview)
- [Microsoft Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/)
- [Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/)
- [Microsoft Defender for Cloud Apps](https://learn.microsoft.com/en-us/defender-cloud-apps/)
