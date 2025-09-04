---
title: Microsoft Identity and Access Management Solutions  
layout: default  
date: 2025-09-04  
---

# Lab 2: Microsoft Identity and Access Management Solutions

**Student Name:** Daniel Wanjama  
**Student ID:** ADC-CSS02-25012  

---

## Introduction

This lab explores Microsoft Entra ID (formerly Azure Active Directory) and its role in identity and access management. You'll configure user settings, test self-service password reset (SSPR), implement conditional access policies, and manage privileged roles using Privileged Identity Management (PIM).

---

## Objectives

- Configure and test Self-Service Password Reset (SSPR)  
- Create and validate Conditional Access policies  
- Implement Privileged Identity Management (PIM)  
- Understand Zero Trust principles in identity security  

---

## Walkthrough

### 🔐 1. Configure Self-Service Password Reset (SSPR)

**Steps:**
1. Navigate to **Microsoft Entra Admin Center** → **Password Reset**  
2. Enable SSPR for selected users  
3. Define authentication methods (e.g., email, phone)  
4. Save and apply settings  

**Test:**
- Sign in as a test user  
- Click “Forgot Password”  
- Complete verification steps  
- Reset password successfully  

**Screenshot:**  
`![lab2_sspr_test.png](/assets/images/labs/lab2_sspr_test.png)`  
*Caption: SSPR test completed successfully*

---

### 🛡️ 2. Create Conditional Access Policy

**Steps:**
1. Go to **Microsoft Entra Admin Center** → **Security** → **Conditional Access**  
2. Click **+ New Policy**  
3. Name the policy: `Block Legacy Authentication`  
4. Assign users/groups  
5. Select cloud apps (e.g., Microsoft 365)  
6. Set conditions:  
   - Client apps: **Legacy authentication clients**  
7. Grant access: **Block access**  
8. Enable policy  

**Validation:**
- Attempt login using legacy protocol  
- Confirm access is blocked  

**Screenshot:**  
`![lab2_conditional_access.png](/assets/images/labs/lab2_conditional_access.png)`  
*Caption: Conditional Access policy blocking legacy authentication*

---

### 👑 3. Implement Privileged Identity Management (PIM)

**Steps:**
1. Navigate to **Microsoft Entra Admin Center** → **Roles and Administrators**  
2. Select a role (e.g., Global Administrator)  
3. Click **Assign** → **Eligible assignment**  
4. Configure activation settings (MFA, justification, etc.)  
5. Save changes  

**Test:**
- Sign in as eligible user  
- Activate role  
- Perform admin task  
- Role auto-deactivates after time limit  

**Screenshot:**  
`![lab2_pim_activation.png](/assets/images/labs/lab2_pim_activation.png)`  
*Caption: PIM role activated with MFA and justification*

---

## Conclusion

This lab demonstrated how Microsoft Entra ID supports secure identity management through SSPR, Conditional Access, and PIM. These features align with Zero Trust principles by enforcing least privilege, verifying explicitly, and assuming breach. Proper configuration of these tools strengthens organizational security posture and reduces identity-related risks.

---

## References

- [Microsoft Learn: Identity and Access Management](https://learn.microsoft.com/en-us/entra/)  
- [Zero Trust Architecture](https://learn.microsoft.com/en-us/security/zero-trust/)  
```

---

