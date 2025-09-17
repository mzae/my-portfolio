---
title: "Lab Walkthrough: Configuring and Securing ACR and AKS"
layout: lab
permalink: /labs/configuring-securing-acr-aks/
author: Daniel Wanjama
date: 2025-09-17
---

## Introduction

This lab was completed as part of the Microsoft ADC Cybersecurity Skilling Program. It focuses on configuring and securing Azure Container Registry (ACR) and Azure Kubernetes Service (AKS). The walkthrough progresses from setup to validation, following a 1–100% completion path with embedded screenshots at key milestones.

---

## Progress: 1% – Create Azure Container Registry

- Created private ACR instance named `acrsecuritylab`  
- Selected Basic SKU and East Africa region  
📸 *Screenshot: `acr-creation.png`*  
![ACR Creation](../../assets/images/labs/acr-creation.png)

---

## Progress: 10% – Build and Push Docker Image to ACR

- Built Nginx image using Dockerfile  
- Tagged image with ACR login server  
- Pushed image to ACR using Docker CLI  
📸 *Screenshot: `docker-push-acr.png`*  
![Docker Push](../../assets/images/labs/docker-push-acr.png)

---

## Progress: 20% – Deploy AKS Cluster

- Created AKS cluster with default node pool  
- Verified resource group and cluster name  
📸 *Screenshot: `aks-cluster-created.png`*  
![AKS Cluster](../../assets/images/labs/aks-cluster-created.png)

---

## Progress: 30% – Assign Role for AKS to Pull from ACR

- Assigned `AcrPull` role to AKS managed identity  
- Verified role assignment using Azure CLI  
📸 *Screenshot: `aks-acr-role-assignment.png`*  
![Role Assignment](../../assets/images/labs/aks-acr-role-assignment.png)

---

## Progress: 40% – Deploy External Service in AKS

- Created Kubernetes deployment and LoadBalancer service  
- Verified public access to Nginx container  
📸 *Screenshot: `external-nginx-access.png`*  
![External Access](../../assets/images/labs/external-nginx-access.png)

---

## Progress: 50% – Deploy Internal Service in AKS

- Created ClusterIP service for internal access  
- Verified pod-to-pod communication  
📸 *Screenshot: `internal-service-test.png`*  
![Internal Service](../../assets/images/labs/internal-service-test.png)

---

## Progress: 60% – Review AKS Networking Configuration

- Inspected subnet and NSG rules  
- Verified AKS node pool isolation  
📸 *Screenshot: `aks-networking.png`*  
![AKS Networking](../../assets/images/labs/aks-networking.png)

---

## Progress: 70% – Explore Kubernetes Dashboard

- Accessed dashboard to inspect pods, services, and deployments  
- Verified image source and resource health  
📸 *Screenshot: `k8s-dashboard.png`*  
![Dashboard Overview](../../assets/images/labs/k8s-dashboard.png)

---

## Progress: 80% – Edit and Apply YAML Configurations

- Modified deployment YAML to increase replicas  
- Applied changes using `kubectl apply`  
📸 *Screenshot: `yaml-edit-apply.png`*  
![YAML Edit](../../assets/images/labs/yaml-edit-apply.png)

---

## Progress: 90% – Final Validation of AKS-ACR Integration

- Verified AKS pulling image securely from ACR  
📸 *Screenshot: `final-validation.png`*  
![Final Validation](../../assets/images/labs/final-validation.png)

---

## Progress: 95% – Resource Cleanup

- Deleted AKS cluster, ACR, and resource group using Azure CLI  
📸 *Screenshot: `resource-deletion-cli.png`*  
![Resource Deletion](../../assets/images/labs/resource-deletion-cli.png)

---

## Progress: 98% – Confirm Resource Group Status

- Verified that no lingering resources remained  
📸 *Screenshot: `resource-group-status.png`*  
![Resource Group Status](../../assets/images/labs/resource-group-status.png)

---

## Progress: 100% – Final Dashboard Review

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
