---
title: Role-Based Access Control in Azure  
layout: archive 
date: 2025-09-04  
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
![rbac_group_creation.png](/assets/images/labs/rbac_group_creation.png)  
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
![rbac_role_assignment.png](/assets/images/labs/rbac_role_assignment.png)  
*Page 3 – Assigning role to Service Desk group*

![rbac_assignment_confirmation.png](/assets/images/labs/rbac_assignment_confirmation.png)  
*Page 4 – Role assignment confirmation*

---

### 🧪 Step 3: Validate Access Control

Logged in as a Service Desk member to test access:

- Able to start, stop, and restart VMs  
- Blocked from deleting or modifying critical resources  

**Screenshots:**  
![rbac_vm_dashboard.png](/assets/images/labs/rbac_vm_dashboard.png)  
*Page 5 – VM dashboard visible to Service Desk user*

![rbac_vm_start.png](/assets/images/labs/rbac_vm_start.png)  
*Page 6 – Starting VM with contributor privileges*

![rbac_vm_restricted_action.png](/assets/images/labs/rbac_vm_restricted_action.png)  
*Page 7 – Attempt to delete VM blocked due to insufficient permissions*

---

### 🧭 Step 4: Review Role Assignments

Verified role assignments across all groups:

- Senior Admins: Full access  
- Junior Admins: Read-only access  
- Service Desk: VM Contributor only  

**Screenshot:**  
![rbac_group_roles_overview.png](/assets/images/labs/rbac_group_roles_overview.png)  
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
![rbac_policy_review.png](/assets/images/labs/rbac_policy_review.png)  
*Page 9 – Reviewing RBAC policy compliance*

![rbac_security_center.png](/assets/images/labs/rbac_security_center.png)  
*Page 10 – Azure Security Center highlighting RBAC configuration*

![rbac_audit_log.png](/assets/images/labs/rbac_audit_log.png)  
*Page 11 – Audit log showing role assignment and access activity*

---

## Summary of Pages 12–25

From page 12 onward, the lab dives deeper into:

- **Policy enforcement testing**: Simulated access attempts by unauthorized users  
- **Role reassignment scenarios**: Temporarily elevated privileges and revocation  
- **Security alerts**: Triggered by misconfigured access or failed login attempts  
- **Compliance dashboard**: Reviewed Secure Score and identity recommendations  
- **Documentation and reporting**: Exported audit logs and role assignment history for governance review  
- **Reflection**: Emphasized the importance of RBAC in Zero Trust architecture and operational security

These sections reinforce the hands-on validation of RBAC principles and demonstrate your ability to manage identity governance in a production-grade Azure environment.

---

## Conclusion

This lab showcased the practical implementation of Role-Based Access Control in Azure. By creating structured security groups and assigning scoped roles, we enforced access boundaries that align with Zero Trust principles. The Service Desk group’s ability to manage VMs without elevated privileges demonstrated how RBAC supports operational efficiency while minimizing risk.

Through this hands-on exercise, I reinforced my understanding of identity governance, access management, and secure cloud operations — essential skills for any cloud security professional.

---

## References

- [Azure RBAC Overview](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview)  
- [Assign Azure Roles](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments)  
- [Azure Security Best Practices](https://learn.microsoft.com/en-us/azure/security/fundamentals/best-practices)
