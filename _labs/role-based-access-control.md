---
title: Role-Based Access Control in Azure
layout: lab
author: Wanjama Daniel
date: 2025-09-04
permalink: /labs/role-based-access-control/
---

# Lab 9: Role-Based Access Control (RBAC)

**Student Name:** Daniel Wanjama
**Student ID:** ADC-CSS02-25012

---

## Introduction

This lab demonstrates how to implement Role-Based Access Control (RBAC) in Microsoft Azure. RBAC restricts access based on user roles, enforcing the principle of least privilege. You'll create security groups, assign roles, validate access, and review governance policies — all within a real-world cloud security scenario.

---

## Objectives

- Create role-specific security groups
- Assign users to appropriate groups
- Apply RBAC using built-in Azure roles
- Validate access control through VM management
- Review audit logs and policy compliance
- Reinforce least privilege and governance principles

---

## Walkthrough

### 👥 Step 1: Create Security Groups

Three security groups were created:

- **Senior Admins** — Member: *Joseph Price*
- **Junior Admins** — Member: *Isabel Garcia*
- **Service Desk** — Member: *Dylan Williams*

**Screenshot:**
![Security group creation interface showing three groups with assigned members for RBAC implementation](../../assets/images/labs/rbac_group_creation.png)
*Page 2 – Creating security groups and assigning members*

---

### 🔐 Step 2: Assign RBAC Roles

Assigned the **Virtual Machine Contributor** role to the **Service Desk** group.

**Steps:**
1. Navigate to the resource group
2. Open **Access Control (IAM)**
3. Click **+ Add role assignment**
4. Select **Virtual Machine Contributor**
5. Assign to **Service Desk** group
6. Save and confirm

**Screenshots:**
![IAM role assignment interface showing Virtual Machine Contributor role selection](../../assets/images/labs/rbac_role_assignment.png)
*Page 3 – Assigning role to Service Desk group*

![Confirmation screen showing successful role assignment to Service Desk group](../../assets/images/labs/rbac_assignment_confirmation.png)
*Page 4 – Role assignment confirmation*

---

### 🧪 Step 3: Validate Access Control

Logged in as a Service Desk member to test access:

- Able to start, stop, and restart VMs
- Blocked from deleting or modifying critical resources

**Screenshots:**
![VM dashboard visible to Service Desk user showing VM management options](../../assets/images/labs/rbac_vm_dashboard.png)
*Page 5 – VM dashboard visible to Service Desk user*

![Service Desk user successfully starting a virtual machine](../../assets/images/labs/rbac_vm_start.png)
*Page 6 – Starting VM with contributor privileges*

![Permission denied error when attempting VM deletion demonstrating access restrictions](../../assets/images/labs/rbac_vm_restricted_action.png)
*Page 7 – Attempt to delete VM blocked due to insufficient permissions*

---

### 🧭 Step 4: Review Role Assignments

Verified role assignments across all groups:

- Senior Admins: Full access
- Junior Admins: Read-only access
- Service Desk: VM Contributor only

**Screenshot:**
![IAM overview showing role assignments for all security groups with respective permissions](../../assets/images/labs/rbac_group_roles_overview.png)
*Page 8 – Role assignments overview for all groups*

---

### 🛡️ Step 5: Governance and Compliance Check

Reviewed access governance policies and audit logs:

- Confirmed alignment with least privilege
- Validated audit trail and role boundaries
- Ensured compliance with internal security standards
- Reviewed policy enforcement and alerts in Azure Security Center
- Verified that role assignments were logged and traceable

**Screenshots:**
![RBAC policy compliance review showing least privilege alignment](../../assets/images/labs/rbac_policy_review.png)
*Page 9 – Reviewing RBAC policy compliance*

![Azure Security Center highlighting RBAC configuration and recommendations](../../assets/images/labs/rbac_security_center.png)
*Page 10 – Azure Security Center highlighting RBAC configuration*

![Audit log displaying role assignment and access activity tracking](../../assets/images/labs/rbac_audit_log.png)
*Page 11 – Audit log showing role assignment and access activity*

---

## Summary

This lab successfully demonstrated RBAC implementation in Azure, showing how to create security groups, assign roles based on job functions, validate permissions, and maintain audit compliance. The principle of least privilege was enforced throughout all configurations.

---

## References

- [Azure RBAC Documentation](https://learn.microsoft.com/en-us/azure/role-based-access-control/)
- [Built-in Azure Roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)
- [Least Privilege Principle](https://learn.microsoft.com/en-us/azure/security/fundamentals/identity-management-best-practices)
