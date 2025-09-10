---
title: "Azure Key Vault & Always Encrypted"
layout: archive
permalink: /labs/Azure-Key-Vault-and-Always-Encrypted/
---

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

## Introduction

This lab demonstrates how to secure sensitive data in Azure SQL Database using:

- **Azure Key Vault** to manage encryption keys and secrets  
- **Always Encrypted** to protect sensitive columns in SQL Server  

The objective is to deploy infrastructure, configure secure key management, and encrypt SQL data using client-side encryption backed by Azure Key Vault.

## Objectives

- Deploy virtual infrastructure using ARM templates  
- Create and configure Azure Key Vault  
- Register an application and assign access policies  
- Encrypt SQL columns using Always Encrypted  
- Validate encryption and key storage

## Prerequisites

- Azure subscription  
- Familiarity with Azure Portal and PowerShell  
- Access to Azure Cloud Shell or local PowerShell  
- SQL Server Management Studio (SSMS) installed on VM  

## Walkthrough

### Task 1: Deploy Infrastructure via ARM Template

Deployed a virtual machine and SQL Database using a custom ARM template.  
📸 *Screenshot: `01-custom-deployment.png` – Custom template deployment*  
![Custom Deployment](../../assets/images/labs/01-custom-deployment.png)

📸 *Screenshot: `02-load-template.png` – Template loaded into editor*  
![Load Template](../../assets/images/labs/02-load-template.png)

---

### Task 2: Create Azure Key Vault

Used PowerShell to create a new Key Vault with a unique name.  
📸 *Screenshot: `04-create-keyvault.png` – Key Vault creation via PowerShell*  
![Create Key Vault](../../assets/images/labs/04-create-keyvault.png)

---

### Task 3: Configure Access Policies

Granted permissions to manage keys and secrets.  
📸 *Screenshot: `06-access-policy.png` – Access policy configuration*  
![Access Policy](../../assets/images/labs/06-access-policy.png)

---

### Task 4: Add Key and Secret to Vault

Created a key named `MyLabKey` and a secret named `SQLPassword`.  
📸 *Screenshot: `09-add-secret.png` – Secret added to Key Vault*  
![Add Secret](../../assets/images/labs/09-add-secret.png)

---

### Task 5: Register Application in Entra ID

Registered an app named `sqlApp` and generated a client secret.  
📸 *Screenshot: `11-app-registration.png` – App registration in Entra ID*  
![App Registration](../../assets/images/labs/11-app-registration.png)

---

### Task 6: Grant App Access to Key Vault

Used PowerShell to assign access to the registered app.

```powershell
Set-AZKeyVaultAccessPolicy -VaultName $kvName -ServicePrincipalName $applicationId -PermissionsToSecrets get, list
```

---

### Task 7: Connect to SQL Server via SSMS

Used RDP to access the VM and connected to SQL Server using SSMS.  
📸 *Screenshot: `14-connect-ssms.png` – SSMS connection to SQL Server*  
![Connect SSMS](../../assets/images/labs/14-connect-ssms.png)

---

### Task 8: Create Patients Table

Created a table with sensitive columns to be encrypted.

```sql
CREATE TABLE [dbo].[Patients] (
  [PatientId] INT IDENTITY(1,1),
  [SSN] CHAR(11) NOT NULL,
  [FirstName] NVARCHAR(50),
  [LastName] NVARCHAR(50),
  [BirthDate] DATE NOT NULL,
  PRIMARY KEY CLUSTERED ([PatientId])
);
```

---

### Task 9: Use Always Encrypted Wizard

Used SSMS wizard to encrypt `SSN` and `BirthDate` columns.  
📸 *Screenshot: `16-encrypt-columns.png` – Column encryption wizard*  
![Encrypt Columns](../../assets/images/labs/16-encrypt-columns.png)

---

### Task 10: Configure Master Key with Azure Key Vault

Selected Azure Key Vault as the key store during encryption setup.  
📸 *Screenshot: `17-master-key-config.png` – Master key configuration*  
![Master Key Config](../../assets/images/labs/17-master-key-config.png)

---

### Task 11: Complete Encryption Wizard

Reviewed summary and completed encryption process.  
📸 *Screenshot: `18-encryption-summary.png` – Encryption summary*  
![Encryption Summary](../../assets/images/labs/18-encryption-summary.png)

---
