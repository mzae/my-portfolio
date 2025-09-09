| title | layout | permalink |
| ----- | ------ | --------- |
| Microsoft Identity and Access Management Solutions | lab | /labs/microsoft-identity-and-access-management-solutions/ |

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

---

## Introduction

This lab explores core components of Microsoft’s identity and access management solutions, including Microsoft Entra ID (formerly Azure AD), Self-Service Password Reset (SSPR), Conditional Access, and Privileged Identity Management (PIM). Through hands-on tasks, I configured user settings, enabled audit logging, enforced access policies, and managed privileged roles to strengthen cloud security posture.

---

## Objectives

- Configure Microsoft Entra ID user settings and roles  
- Enable Microsoft 365 audit logging and file monitoring  
- Implement Self-Service Password Reset (SSPR)  
- Create Conditional Access policies  
- Manage privileged roles using PIM  

---

## Prerequisites

- Azure subscription with admin access  
- Skillable lab environment  
- Familiarity with Microsoft 365 and Azure Portal  

---

## Walkthrough

### Task 1: Sign In to Microsoft Entra Admin Center

- Accessed the Microsoft Entra admin portal  
- Verified tenant and user access  

📸 *Screenshot: `entra-signin.png` – Admin sign-in to Microsoft Entra*  
[![Sign In](../../assets/images/labs/entra-signin.png)](../../assets/images/labs/entra-signin.png)

---

### Task 2: Explore User Settings

- Navigated to **Users > All Users**  
- Reviewed user roles and authentication methods  
- Modified settings for selected accounts  

📸 *Screenshot: `entra-user-settings.png` – Viewing user settings*  
[![User Settings](../../assets/images/labs/entra-user-settings.png)](../../assets/images/labs/entra-user-settings.png)

---

### Task 3: Enable Microsoft 365 Audit Logging

- Opened **Microsoft 365 Defender > Audit**  
- Verified audit logging was already enabled  
- Enabled file monitoring for compliance  

📸 *Screenshot: `audit-log-enabled.png` – Audit log status*  
[![Audit Log](../../assets/images/labs/audit-log-enabled.png)](../../assets/images/labs/audit-log-enabled.png)  
📸 *Screenshot: `file-monitoring-enabled.png` – File monitoring enabled*  
[![File Monitoring](../../assets/images/labs/file-monitoring-enabled.png)](../../assets/images/labs/file-monitoring-enabled.png)

---

### Task 4: Configure Self-Service Password Reset (SSPR)

- Accessed **Password Reset > Properties**  
- Enabled SSPR for all users  
- Defined authentication methods (email, phone)  

📸 *Screenshot: `sspr-properties.png` – SSPR configuration*  
[![SSPR Properties](../../assets/images/labs/sspr-properties.png)](../../assets/images/labs/sspr-properties.png)

---

### Task 5: Test SSPR Functionality

- Simulated password reset from user portal  
- Verified multi-factor authentication prompts  
- Confirmed successful password change  

📸 *Screenshot: `sspr-reset-process.png` – Reset process flow*  
[![SSPR Reset](../../assets/images/labs/sspr-reset-process.png)](../../assets/images/labs/sspr-reset-process.png)

---

### Task 6: Create Conditional Access Policy

- Navigated to **Security > Conditional Access**  
- Created policy targeting risky sign-ins  
- Required MFA for access to sensitive apps  

📸 *Screenshot: `conditional-access-policy.png` – Policy creation*  
[![Conditional Access](../../assets/images/labs/conditional-access-policy.png)](../../assets/images/labs/conditional-access-policy.png)

---

### Task 7: Assign Conditions and Controls

- Selected user group and cloud apps  
- Applied sign-in risk condition  
- Enabled control: Require MFA  

📸 *Screenshot: `conditional-access-controls.png` – Assigning controls*  
[![Access Controls](../../assets/images/labs/conditional-access-controls.png)](../../assets/images/labs/conditional-access-controls.png)

---

### Task 8: Test Conditional Access Enforcement

- Attempted sign-in from unmanaged device  
- Triggered MFA prompt  
- Verified access was granted only after compliance  

📸 *Screenshot: `conditional-access-test.png` – Policy enforcement test*  
[![Policy Test](../../assets/images/labs/conditional-access-test.png)](../../assets/images/labs/conditional-access-test.png)

---

### Task 9: Explore Privileged Identity Management (PIM)

- Accessed **Microsoft Entra > PIM**  
- Reviewed eligible and active roles  
- Assigned just-in-time access to Global Administrator  

📸 *Screenshot: `pim-dashboard.png` – PIM dashboard overview*  
[![PIM Dashboard](../../assets/images/labs/pim-dashboard.png)](../../assets/images/labs/pim-dashboard.png)

---

### Task 10: Activate Role and Review Audit Logs

- Activated Global Admin role for limited duration  
- Verified approval workflow  
- Reviewed audit logs for role activation  

📸 *Screenshot: `pim-role-activation.png` – Role activation flow*  
[![Role Activation](../../assets/images/labs/pim-role-activation.png)](../../assets/images/labs/pim-role-activation.png)  
📸 *Screenshot: `pim-audit-log.png` – Audit log review*  
[![Audit Log](../../assets/images/labs/pim-audit-log.png)](../../assets/images/labs/pim-audit-log.png)

---

## Conclusion

This lab provided hands-on experience with Microsoft’s identity and access management tools. I configured user settings, enabled audit logging, implemented SSPR, enforced Conditional Access policies, and managed privileged roles using PIM. These tasks reinforced key concepts in identity governance, Zero Trust, and secure access control—critical for protecting cloud environments.

---

