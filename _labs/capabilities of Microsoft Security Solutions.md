---
layout: lab
title: "Describe the Capabilities of Microsoft Security Solutions"
date: 2025-08-27
categories: [Azure, Security, Labs]
author: Daniel Wanjama
---

## 🧭 Introduction

This lab explores Microsoft’s cloud security tools including Microsoft 365 tenant setup, Azure Network Security Groups (NSGs), Microsoft Defender for Cloud, Microsoft Sentinel, and Microsoft Defender for Cloud Apps. Each tool plays a role in protecting identities, networks, applications, and data in the cloud.

---

## 🔐 Lab 1: Azure Network Security Groups (NSGs)

### Task 1: View VM Details
- Access the Azure portal and locate the pre-created VM.
- Review VM configuration and network interface.
- ![VM Details](/assets/images/labs/lab1-nsg-task1-vm-details.png)

### Task 2: Create NSG and Add RDP Rule
- Create a new NSG named `NSG-SC900`.
- Associate it with the VM’s NIC.
- Add inbound rule for RDP (port 3389).
- ![Create NSG](/assets/images/labs/lab1-nsg-task2-create-nsg.png)
- ![Add RDP Rule](/assets/images/labs/lab1-nsg-task2-add-rdp-rule.png)

### Task 3: Test RDP and Outbound Access
- Use “Check Access” to verify RDP connectivity.
- Connect via Native RDP and test outbound internet access.
- ![RDP Test](/assets/images/labs/lab1-nsg-task3-rdp-connectivity-test.png)
- ![Outbound Access](/assets/images/labs/lab1-nsg-task3-outbound-access-check.png)

### Task 4: Block Outbound Internet
- Create outbound rule to deny traffic to `Internet` service tag.
- Test by attempting to access `www.bing.com` from the VM.
- ![Block Outbound Rule](/assets/images/labs/lab1-nsg-task4-block-outbound-rule.png)
- ![Test Blocked Access](/assets/images/labs/lab1-nsg-task4-test-blocked-access.png)

---

## 🛡️ Lab 2: Microsoft Defender for Cloud

### Task 1: Explore Defender Dashboard
- Navigate to Defender for Cloud in Azure.
- Review secure score, assessed resources, and recommendations.
- ![Defender Overview](/assets/images/labs/lab2-defender-overview.png)

### Task 2: Review Recommendations
- Select VM resource and view remediation steps.
- ![Security Recommendations](/assets/images/labs/lab2-defender-security-recommendations.png)

### Task 3: Enable Defender Plans
- Enable CSPM and Server protection plans.
- ![Enable Defender Plans](/assets/images/labs/lab2-defender-enable-plans.png)

---

## 🧠 Lab 3: Microsoft Sentinel

### Task 1: Create Sentinel Instance
- Create Log Analytics workspace named `SC900-LogAnalytics-workspace`.
- Enable Microsoft Sentinel.
- ![Create Sentinel](/assets/images/labs/lab3-sentinel-task1-create-instance.png)

### Task 2: Assign Roles
- Assign built-in Sentinel roles via IAM in `SC900-Sentinel-RG`.
- ![Role Assignment](/assets/images/labs/lab3-sentinel-task2-role-assignment.png)

### Task 3: Connect Defender for Cloud
- Use Content Hub to deploy Defender for Cloud solution.
- Configure connector and verify alert ingestion.
- ![Content Hub](/assets/images/labs/lab3-sentinel-task3-connect-content-hub.png)
- ![Deploy Solution](/assets/images/labs/lab3-sentinel-task3-defender-solution-deploy.png)

---

## ☁️ Lab 4: Microsoft Defender for Cloud Apps

### Task 1: Explore Cloud Discovery
- Navigate to Microsoft 365 Defender portal.
- Access Cloud Discovery dashboard.
- ![Cloud Discovery](/assets/images/labs/lab4-defender-apps-cloud-discovery.png)

### Task 2: Review App Catalog
- View discovered apps, risk scores, and usage stats.
- ![App Catalog](/assets/images/labs/lab4-defender-apps-app-catalog.png)

### Task 3: Investigate Findings
- Use investigation tools and filters.
- ![Investigation Tools](/assets/images/labs/lab4-defender-apps-investigation-tools.png)

### Task 4: Configure Policies
- Tag apps as sanctioned/unsanctioned.
- Enable file monitoring under Information Protection.
- ![Policy Controls](/assets/images/labs/lab4-defender-apps-policy-controls.png)

---

## 🧾 Conclusion

Completing these labs provided hands-on experience with Microsoft’s cloud security ecosystem. Key takeaways include:

- Identity and access management via Microsoft 365
- Traffic control using NSGs
- Threat detection with Defender and Sentinel
- App governance through Defender for Cloud Apps

Security is a layered approach—these tools work together to protect cloud environments from evolving threats. This lab was a major step in my cloud security journey, and I’m excited to apply what I’ve learned in real-world scenarios.



