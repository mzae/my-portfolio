---
title: Service Endpoints and Securing Storage
layout: default
date: 2025-09-04
---

# Lab 6: Service Endpoints and Securing Storage

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

## Introduction

This walkthrough guides you through Lab 06 of the Microsoft ADC Cybersecurity Skilling Program, focusing on securing Azure Storage using Service Endpoints and Network Security Groups (NSGs). The lab demonstrates how to restrict access to Azure Storage accounts by leveraging virtual network subnets, ensuring traffic remains within the Azure backbone and preventing unauthorized external access. By the end, you will have hands-on experience configuring secure storage solutions in Microsoft Azure.

**Objectives:**
- Configure Azure Service Endpoints for a storage account.
- Set up Network Security Groups to control subnet access.
- Deploy virtual machines in isolated subnets to test connectivity.
- Validate secure access to Azure Storage.

## Prerequisites
- An active Azure subscription.
- Basic knowledge of Azure Portal, virtual networks, and storage accounts.
- Access to Azure Cloud Shell or PowerShell for command-line tasks.

## Walkthrough

### Step 1: Create a Storage Account
1. Log in to the [Azure Portal](https://portal.azure.com).
2. Navigate to **Storage accounts** > **Create**.
3. Configure the basics:
   - **Subscription**: Select your subscription.
   - **Resource group**: Create or select a resource group (e.g., `Lab06-RG`).
   - **Storage account name**: Enter a unique name (e.g., `lab06storage`).
   - **Region**: Choose a region (e.g., East US).
   - **Performance**: Standard.
   - **Redundancy**: Locally-redundant storage (LRS).
4. Click **Next** through other tabs, leaving defaults, and click **Create**.
   - *Screenshot: [lab6_page12.png](/assets/images/labs/lab6_page12.png) - Creating storage account basics.*

### Step 2: Create a Virtual Network
1. In the Azure Portal, go to **Virtual networks** > **Create**.
2. Configure the virtual network:
   - **Name**: `Lab06-VNet`.
   - **Address space**: `10.0.0.0/16`.
   - **Resource group**: Use the same as the storage account.
3. Add two subnets:
   - **PublicSubnet**: `10.0.1.0/24`.
   - **PrivateSubnet**: `10.0.2.0/24`.
4. Click **Create**.
   - *Screenshot: [lab6_page4.png](/assets/images/labs/lab6_page4.png) - Creating virtual network and public subnet.*
   - *Screenshot: [lab6_page6.png](/assets/images/labs/lab6_page6.png) - Adding private subnet.*

### Step 3: Configure Network Security Groups (NSGs)
1. Go to **Network security groups** > **Create**.
2. Create NSG for the private subnet:
   - **Name**: `Private-NSG`.
   - **Resource group**: Same as above.
3. Add inbound and outbound rules:
   - **Inbound**: Allow traffic from `PrivateSubnet` (e.g., source `10.0.2.0/24`, destination `Storage`, port `445` for SMB).
   - **Outbound**: Allow traffic to `Storage` service tag.
   - *Screenshot: [lab6_page7.png](/assets/images/labs/lab6_page7.png) - Outbound rules for private NSG.*
   - *Screenshot: [lab6_page8.png](/assets/images/labs/lab6_page8.png) - Inbound rules for private NSG.*
4. Associate `Private-NSG` to `PrivateSubnet`.
   - *Screenshot: [lab6_page9.png](/assets/images/labs/lab6_page9.png) - Associating NSG to private subnet.*
5. Create NSG for the public subnet:
   - **Name**: `Public-NSG`.
   - Add inbound rules to allow RDP (port `3389`) but deny `Storage` access.
   - *Screenshot: [lab6_page10.png](/assets/images/labs/lab6_page10.png) - Creating public NSG.*
   - *Screenshot: [lab6_page11.png](/assets/images/labs/lab6_page11.png) - Inbound rules for public NSG.*

### Step 4: Configure Storage Account Networking
1. Navigate to the storage account (`lab06storage`).
2. Go to **Networking** > **Firewalls and virtual networks**.
3. Select **Enabled from selected virtual networks and IP addresses**.
4. Add the virtual network:
   - Select `Lab06-VNet` and `PrivateSubnet`.
   - Enable **Microsoft.Storage** service endpoint for `PrivateSubnet`.
5. Save changes.
   - *Screenshot: [lab6_page15.png](/assets/images/labs/lab6_page15.png) - Configuring storage networking.*
   - *Screenshot: [lab6_page18.png](/assets/images/labs/lab6_page18.png) - Adding virtual network to storage firewall.*

### Step 5: Create a File Share
1. In the storage account, go to **File shares** > **+ File share**.
2. Name the file share (e.g., `lab06share`).
3. Click **Create**.
   - *Screenshot: [lab6_page13.png](/assets/images/labs/lab6_page13.png) - Creating file share.*
   - *Screenshot: [lab6_page14.png](/assets/images/labs/lab6_page14.png) - File share created.*

### Step 6: Deploy Virtual Machines
1. Create a VM in the private subnet:
   - Go to **Virtual machines** > **Create** > **Azure virtual machine**.
   - **Name**: `Private-VM`.
   - **Subnet**: `PrivateSubnet`.
   - Use defaults for other settings (e.g., Windows Server, Standard_D2s_v3).
   - Enable RDP access.
   - *Screenshot: [lab6_page19.png](/assets/images/labs/lab6_page19.png) - Creating VM in private subnet.*
2. Create a VM in the public subnet:
   - **Name**: `Public-VM`.
   - **Subnet**: `PublicSubnet`.
   - *Screenshot: [lab6_page20.png](/assets/images/labs/lab6_page20.png) - Creating VM in public subnet.*
3. Verify VM deployment.
   - *Screenshot: [lab6_page21.png](/assets/images/labs/lab6_page21.png) - VM deployment and RDP connection.*
   - *Screenshot: [lab6_page22.png](/assets/images/labs/lab6_page22.png) - VM login screen.*

### Step 7: Test Connectivity
1. Connect to `Private-VM` via RDP.
2. Open PowerShell and run the following to test file share access:
   ```powershell
   net use Z: \\lab06storage.file.core.windows.net\lab06share /u:AZURE\lab06storage <storage-key>
   ```
   - Replace `<storage-key>` with the storage account access key (found in **Storage account** > **Access keys**).
   - *Screenshot: [lab6_page17.png](/assets/images/labs/lab6_page17.png) - Testing file share access.*
3. Verify access succeeds (drive `Z:` mounts).
4. Connect to `Public-VM` via RDP and repeat the test.
   - Access should fail due to NSG and storage firewall rules.
   - *Screenshot: [lab6_page23.png](/assets/images/labs/lab6_page23.png) - Running PowerShell script.*
   - *Screenshot: [lab6_page24.png](/assets/images/labs/lab6_page24.png) - Failed access test on public VM.*

### Step 8: Validate Security Configuration
- Confirm that `Private-VM` accesses the file share successfully, while `Public-VM` is blocked.
- Verify NSG rules and storage firewall settings align with the principle of least privilege.

## Conclusion
This lab demonstrated how to secure Azure Storage using Service Endpoints and NSGs. By configuring a virtual network with public and private subnets, enabling a storage service endpoint, and applying NSG rules, we ensured that only trusted resources could access the storage account. The Azure backbone was used for secure communication, reducing exposure to the public internet. Testing with VMs validated the security configuration, confirming that only the private subnet had access. These skills are critical for implementing secure, compliant cloud architectures in real-world scenarios.

*Note: Place this Markdown file in the `_labs` directory as `Lab_6_Service_Endpoints_and_Securing_Storage.md`. Ensure screenshots are saved in `assets/images/labs/` with the referenced filenames (e.g., `lab6_page2.png`).*
