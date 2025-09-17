---
title: "Full Lab: Configuring and Securing Azure Container Registry (ACR) and Azure Kubernetes Service (AKS)"
layout: lab
permalink: /labs/full-acr-aks-walkthrough/
author: Daniel Wanjama
date: 2025-09-17
---

## Introduction

This lab was completed as part of the Microsoft ADC Cybersecurity Skilling Program. It focuses on configuring and securing Azure Container Registry (ACR) and Azure Kubernetes Service (AKS). The goal was to gain hands-on experience deploying containerized applications in Azure, managing access controls, and applying cloud-native security practices.

---

## Objectives

- Create and configure Azure Container Registry  
- Build and push Docker image to ACR  
- Deploy AKS cluster and configure secure image pull  
- Assign roles and permissions for AKS-ACR integration  
- Deploy external and internal Kubernetes services  
- Validate access, networking, and dashboard visibility  
- Apply YAML configurations and verify updates  
- Perform resource cleanup and reflect on key learnings  

---

## Walkthrough

### Task 1: Create Azure Container Registry

- Created private ACR instance named `acrsecuritylab`  
- Selected Basic SKU and East Africa region  
📸 *Screenshot: `acr-creation.png`*  
![ACR Creation](../../assets/images/labs/acr-creation.png)

---

### Task 2: Build and Push Docker Image to ACR

- Built Nginx image using Dockerfile  
- Tagged image with ACR login server  
- Pushed image to ACR using Docker CLI  
📸 *Screenshot: `docker-push-acr.png`*  
![Docker Push](../../assets/images/labs/docker-push-acr.png)

---

### Task 3: Deploy AKS Cluster

- Created AKS cluster with default node pool  
- Verified resource group and cluster name  
📸 *Screenshot: `aks-cluster-created.png`*  
![AKS Cluster](../../assets/images/labs/aks-cluster-created.png)

---

### Task 4: Assign Role for AKS to Pull from ACR

- Assigned `AcrPull` role to AKS managed identity  
- Verified role assignment using Azure CLI  
📸 *Screenshot: `aks-acr-role-assignment.png`*  
![Role Assignment](../../assets/images/labs/aks-acr-role-assignment.png)

---

### Task 5: Deploy External Service in AKS

- Created Kubernetes deployment and LoadBalancer service  
- Verified public access to Nginx container  
📸 *Screenshot: `external-nginx-access.png`*  
![External Access](../../assets/images/labs/external-nginx-access.png)

---

### Task 6: Deploy Internal Service in AKS

- Created ClusterIP service for internal access  
- Verified pod-to-pod communication  
📸 *Screenshot: `internal-service-test.png`*  
![Internal Service](../../assets/images/labs/internal-service-test.png)

---

### Task 7: Review AKS Networking Configuration

- Inspected subnet and NSG rules  
- Verified AKS node pool isolation  
📸 *Screenshot: `aks-networking.png`*  
![AKS Networking](../../assets/images/labs/aks-networking.png)

---

### Task 8: Explore Kubernetes Dashboard

- Accessed dashboard to inspect pods, services, and deployments  
- Verified image source and resource health  
📸 *Screenshot: `k8s-dashboard.png`*  
![Dashboard Overview](../../assets/images/labs/k8s-dashboard.png)

---

### Task 9: Edit and Apply YAML Configurations

- Modified deployment YAML to increase replicas  
- Applied changes using `kubectl apply`  
📸 *Screenshot: `yaml-edit-apply.png`*  
![YAML Edit](../../assets/images/labs/yaml-edit-apply.png)

---

### Task 10: Final Validation of AKS-ACR Integration

- Verified AKS pulling image securely from ACR  
📸 *Screenshot: `final-validation.png`*  
![Final Validation](../../assets/images/labs/final-validation.png)

---

### Task 11: Deployment Rollout and Replica Scaling

- Used `kubectl rollout status` to confirm successful update  
- Verified replica count with `kubectl get deployment`  
📸 *Screenshot: `deployment-rollout-status.png`*  
![Rollout Status](../../assets/images/labs/deployment-rollout-status.png)  
📸 *Screenshot: `replica-count-confirmation.png`*  
![Replica Count](../../assets/images/labs/replica-count-confirmation.png)

---

### Task 12: Network Security and NSG Review

- Inspected NSG rules for AKS subnet  
- Verified port restrictions and subnet isolation  
📸 *Screenshot: `nsg-rules-review.png`*  
![NSG Rules](../../assets/images/labs/nsg-rules-review.png)  
📸 *Screenshot: `subnet-isolation-check.png`*  
![Subnet Isolation](../../assets/images/labs/subnet-isolation-check.png)

---

### Task 13: Internal Pod Access and DNS Resolution

- Used `kubectl exec` and `curl` to test pod connectivity  
- Verified DNS resolution between services  
📸 *Screenshot: `kubectl-exec-curl-test.png`*  
![Pod Access Test](../../assets/images/labs/kubectl-exec-curl-test.png)  
📸 *Screenshot: `dns-resolution-test.png`*  
![DNS Test](../../assets/images/labs/dns-resolution-test.png)

---

### Task 14: Resource Cleanup

- Deleted AKS cluster, ACR, and resource group using Azure CLI  
📸 *Screenshot: `resource-deletion-cli.png`*  
![Resource Deletion](../../assets/images/labs/resource-deletion-cli.png)  
📸 *Screenshot: `resource-group-status.png`*  
![Resource Group Status](../../assets/images/labs/resource-group-status.png)

---

### Task 15: Final Dashboard Review

- Revisited Kubernetes dashboard to confirm pod health  
📸 *Screenshot: `dashboard-final-check.png`*  
![Final Dashboard](../../assets/images/labs/dashboard-final-check.png)

---

## Conclusion

This lab provided hands-on experience with deploying and securing containerized applications in Azure. I learned how to:

- Build and store Docker images in ACR  
- Deploy AKS clusters and configure secure image pulls  
- Assign roles and manage access controls  
- Deploy and test both external and internal services  
- Scale deployments using YAML and verify rollout  
- Review network security and isolate workloads  
- Clean up resources responsibly to manage costs  

These skills are foundational for cloud security and DevOps workflows. I now feel confident applying these practices in real-world environments and freelance projects.

---
