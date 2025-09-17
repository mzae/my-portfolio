---
title: "Configuring and Securing Azure Container Registry (ACR) and Azure Kubernetes Service (AKS)"
layout: lab
permalink: /labs/configuring-securing-acr-aks/
author: Daniel Wanjama
date: 2025-09-17
---

## Introduction

This lab provides a complete walkthrough of deploying and securing containerized workloads using **Azure Container Registry (ACR)** and **Azure Kubernetes Service (AKS)**. It covers image creation, secure registry access, AKS deployment, role assignments, service exposure, and validation steps. Screenshots are included to document the full lifecycle of the solution.

---

## Objectives

- Create and configure Azure Container Registry  
- Build and push Docker image to ACR  
- Deploy AKS cluster and configure secure image pull  
- Assign roles and permissions for AKS-ACR integration  
- Deploy external and internal Kubernetes services  
- Validate access, networking, and dashboard visibility  
- Apply YAML configurations and verify updates  
- Perform final validation and cleanup  

---

## Prerequisites

- Azure subscription with admin access  
- Docker installed locally or in lab environment  
- Familiarity with Azure CLI, Kubernetes, and YAML  

---

## Walkthrough

### Task 1: Create Azure Container Registry

- Created private ACR instance named `acrsecuritylab`  
- Selected Basic SKU and East Africa region  
📸 *Screenshot: `acr-creation.png` – ACR instance created*  
![ACR Creation](../../assets/images/labs/acr-creation.png)

---

### Task 2: Build and Push Docker Image to ACR

- Built Nginx image using Dockerfile  
- Tagged image with ACR login server  
- Pushed image to ACR using Docker CLI  
📸 *Screenshot: `docker-push-acr.png` – Docker image pushed to ACR*  
![Docker Push](../../assets/images/labs/docker-push-acr.png)

---

### Task 3: Deploy AKS Cluster

- Created AKS cluster with default node pool  
- Verified resource group and cluster name  
📸 *Screenshot: `aks-cluster-created.png` – AKS cluster deployed*  
![AKS Cluster](../../assets/images/labs/aks-cluster-created.png)

---

### Task 4: Assign Role for AKS to Pull from ACR

- Assigned `AcrPull` role to AKS managed identity  
- Verified role assignment using Azure CLI  
📸 *Screenshot: `aks-acr-role-assignment.png` – Role assignment for secure image pull*  
![Role Assignment](../../assets/images/labs/aks-acr-role-assignment.png)

---

### Task 5: Deploy External Service in AKS

- Created Kubernetes deployment and LoadBalancer service  
- Verified public access to Nginx container  
📸 *Screenshot: `external-nginx-access.png` – External service exposed*  
![External Access](../../assets/images/labs/external-nginx-access.png)

---

### Task 6: Deploy Internal Service in AKS

- Created ClusterIP service for internal access  
- Verified pod-to-pod communication  
📸 *Screenshot: `internal-service-test.png` – Internal service connectivity test*  
![Internal Service](../../assets/images/labs/internal-service-test.png)

---

### Task 7: Review AKS Networking Configuration

- Inspected subnet and NSG rules  
- Verified AKS node pool isolation  
📸 *Screenshot: `aks-networking.png` – AKS network configuration*  
![AKS Networking](../../assets/images/labs/aks-networking.png)

---

### Task 8: Explore Kubernetes Dashboard

- Accessed dashboard to inspect pods, services, and deployments  
- Verified image source and resource health  
📸 *Screenshot: `k8s-dashboard.png` – Kubernetes dashboard overview*  
![Dashboard Overview](../../assets/images/labs/k8s-dashboard.png)

---

### Task 9: Edit and Apply YAML Configurations

- Modified deployment YAML to increase replicas  
- Applied changes using `kubectl apply`  
📸 *Screenshot: `yaml-edit-apply.png` – YAML configuration update*  
![YAML Edit](../../assets/images/labs/yaml-edit-apply.png)

---

### Task 10: Final Validation and Cleanup

- Verified AKS pulling image securely from ACR  
- Deleted resources to avoid billing charges  
📸 *Screenshot: `final-validation.png` – Final validation of AKS-ACR integration*  
![Final Validation](../../assets/images/labs/final-validation.png)

---

## Key Learnings

- ACR provides secure, private storage for container images  
- AKS requires explicit role assignment to pull images from ACR  
- Kubernetes services can be exposed externally or kept internal  
- YAML configuration drives deployment and scaling  
- Role-based access and network isolation are essential for cloud-native security  
- Azure CLI and dashboard tools provide full visibility into cluster health  

---
