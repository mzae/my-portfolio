## 🔧 Exercise 1: Deploy Base Infrastructure via ARM Template

### Step 1: Deploy Custom Template
Navigate to Azure Portal → Search “Deploy a custom template”.  
![Custom Deployment](assets/images/lab7/01-custom-deployment.png)

### Step 2: Load ARM Template
Load `az-500-10_azuredeploy.json` into the editor and deploy the resources.  
![Load Template](assets/images/lab7/02-load-template.png)

---

## 🔐 Exercise 2: Configure Azure Key Vault

### Step 3: Create Key Vault via PowerShell
Use PowerShell to create a new Key Vault with a unique name.

```powershell
$kvName = 'az500kv' + $(Get-Random)
New-AzKeyVault -VaultName $kvName -ResourceGroupName '<YourResourceGroup>'
```

![Create Key Vault](assets/images/lab7/04-create-keyvault.png)

### Step 4: Add Access Policy
Grant permissions to manage keys and secrets.

![Access Policy](assets/images/lab7/06-access-policy.png)

### Step 5: Add Key and Secret to Vault
Create a key named `MyLabKey` and a secret named `SQLPassword`.

```powershell
Add-AZKeyVaultKey -VaultName $kvName -Name 'MyLabKey' -Destination 'Software'

$secretvalue = ConvertTo-SecureString 'Pa55w.rd1234' -AsPlainText -Force
Set-AZKeyVaultSecret -VaultName $kvName -Name 'SQLPassword' -SecretValue $secretvalue
```

![Add Secret](assets/images/lab7/09-add-secret.png)

---

## 🧩 Exercise 3: Register Application and Configure Access

### Step 6: Register App in Microsoft Entra ID
Create an app registration named `sqlApp` and generate a client secret.

![App Registration](assets/images/lab7/11-app-registration.png)

### Step 7: Grant App Access to Key Vault
Use PowerShell to assign access to the registered app.

```powershell
Set-AZKeyVaultAccessPolicy -VaultName $kvName -ServicePrincipalName $applicationId -PermissionsToSecrets get, list
```

---

## 🖥️ Exercise 4: Encrypt SQL Columns with Always Encrypted

### Step 8: Connect to SQL Server via SSMS
Use RDP to access the VM and connect to SQL Server using SSMS.

![Connect SSMS](assets/images/lab7/14-connect-ssms.png)

### Step 9: Create Patients Table
Define a table with sensitive columns like SSN and BirthDate.

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

### Step 10: Use Always Encrypted Wizard
Right-click the table → Encrypt Columns → Select `SSN` and `BirthDate`.

![Encrypt Columns](assets/images/lab7/16-encrypt-columns.png)

### Step 11: Configure Master Key with Azure Key Vault
Sign in and select your Key Vault to store the encryption key.

![Master Key Config](assets/images/lab7/17-master-key-config.png)

### Step 12: Complete Encryption Wizard
Review summary and finish the encryption process.

![Encryption Summary](assets/images/lab7/18-encryption-summary.png)

---

## ✅ Final Result

You’ve successfully:
- Deployed infrastructure using ARM templates.
- Configured Azure Key Vault with keys and secrets.
- Registered and secured an app with access policies.
- Encrypted sensitive SQL columns using Always Encrypted.

Your data is now protected both at rest and in transit, with keys securely managed in Azure Key Vault.

---

## 🔗 Key Vault URIs (Examples)
- Vault URI: `https://<vaultname>.vault.azure.net/`
- Key Identifier: `https://<vaultname>.vault.azure.net/keys/MyLabKey/<version>`
- Secret URI: `https://<vaultname>.vault.azure.net/secrets/SQLPassword/<version>`

---

## 👨‍💻 Author

**Daniel Wanjama**  
Student ID: ADC-CSS02-25012  
Cyber Shujaa Program  
Location: Nairobi, Kenya
```

---
