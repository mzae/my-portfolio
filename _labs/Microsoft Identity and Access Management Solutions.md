---
title: "Microsoft Identity and Access Management Solutions"
layout: lab
author: Wanjama Daniel
permalink: /labs/microsoft-identity-and-access-management-solutions/
date: 2025-09-09
---

## Introduction

This lab explores core components of Microsoft's identity and access management solutions, including Microsoft Entra ID (formerly Azure AD), Self-Service Password Reset (SSPR), Conditional Access, and Privileged Identity Management (PIM). Through hands-on tasks, I configured user settings, enabled audit logging, enforced access policies, and managed privileged roles to strengthen cloud security posture.

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

📸 *Screenshot: Admin sign-in to Microsoft Entra*
![Microsoft Entra admin center login interface showing successful authentication](../../assets/images/labs/entra-signin.png)
*Sign In*

---

### Task 2: Explore User Settings

- Navigated to **Users > All Users**
- Reviewed user roles and authentication methods
- Modified settings for selected accounts

📸 *Screenshot: Viewing user settings*
![Microsoft Entra Users page showing user list with roles and authentication status](../../assets/images/labs/entra-user-settings.png)
*User Settings*

---

### Task 3: Enable Microsoft 365 Audit Logging

- Opened **Microsoft 365 Defender > Audit**
- Verified audit logging was already enabled
- Enabled file monitoring for compliance

📸 *Screenshot: Audit log status*
![Microsoft 365 Defender audit page showing enabled audit logging for compliance tracking](../../assets/images/labs/audit-log-enabled.png)
*Audit Log*

📸 *Screenshot: File monitoring enabled*
![Microsoft 365 Defender showing file monitoring configuration for document access tracking](../../assets/images/labs/file-monitoring-enabled.png)
*File Monitoring*

---

### Task 4: Configure Self-Service Password Reset (SSPR)

- Accessed **Password Reset > Properties**
- Enabled SSPR for all users
- Defined authentication methods (email, phone)

📸 *Screenshot: SSPR configuration*
![Microsoft Entra SSPR properties page showing authentication methods and user scope](../../assets/images/labs/sspr-properties.png)
*SSPR Properties*

---

### Task 5: Test SSPR Functionality

- Simulated password reset from user portal
- Verified multi-factor authentication prompts
- Confirmed successful password change

📸 *Screenshot: Reset process flow*
![SSPR reset process showing authentication methods and password change confirmation](../../assets/images/labs/sspr-reset-process.png)
*SSPR Reset*

---

### Task 6: Create Conditional Access Policy

- Navigated to **Security > Conditional Access**
- Created policy targeting risky sign-ins
- Required MFA for access to sensitive apps

📸 *Screenshot: Policy creation*
![Conditional Access policy creation interface showing risky sign-in targeting](../../assets/images/labs/conditional-access-policy.png)
*Conditional Access*

---

### Task 7: Assign Conditions and Controls

- Selected user group and cloud apps
- Applied sign-in risk condition
- Enabled control: Require MFA

📸 *Screenshot: Assigning controls*
![Conditional Access controls page showing MFA requirement for risky sign-ins](../../assets/images/labs/conditional-access-controls.png)
*Access Controls*

---

## Summary

This lab successfully demonstrated Microsoft's identity and access management capabilities. SSPR enabled user autonomy, Conditional Access enforced adaptive security, and audit logging ensured compliance tracking.

---

## References

- [Microsoft Entra ID Documentation](https://learn.microsoft.com/en-us/entra/identity/)
- [Self-Service Password Reset](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-sspr-howitworks)
- [Conditional Access Policies](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview)
- [Privileged Identity Management](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/)
