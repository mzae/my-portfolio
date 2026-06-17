---
title: SOC Analyst Case Study – Security Operations Simulation
layout: lab
category: Security Operations
level: Advanced
tags: [SOC, SIEM, Incident Response, Threat Hunting]
---


# 🛡️ SOC Analyst Case Study (Capstone)

## 🧠 Overview
This page brings together all hands-on security engineering labs into a unified SOC (Security Operations Center) simulation workflow.

---

## 🔗 SOC Security Labs Dashboard

### 🔥 Core Security Operations Labs

- [Incident Response Case Study](https://github.com/mzae/my-portfolio/blob/master/_labs/incident-response-case-study.md)
- [Incident Response Playbook](../incident-response-playbook.md)
- [Threat Hunting Lab](../threat-hunting.md)
- [Sentinel Integration](../sentinel-integration.md)






# 🛡️ SOC Analyst Case Study – Security Operations Simulation

## 📌 Objective
This lab simulates a real-world Security Operations Center (SOC) investigation using Microsoft Sentinel and Azure security tools.

---

## 🧠 Scenario Overview

A suspicious activity alert was triggered in a simulated enterprise environment. The investigation involved:

- Log analysis in Microsoft Sentinel
- Identity verification using Entra ID logs
- Network traffic inspection
- Threat classification and response

---

## 🔍 Investigation Steps

### 1. Alert Detection (Sentinel)
Security alerts were generated based on anomalous login patterns and network behavior.

### 2. Log Analysis
Investigated:
- Authentication logs
- VM activity logs
- Firewall logs

### 3. Threat Validation
Confirmed whether activity was:
- False positive
- Insider threat
- External attack attempt

---

## 🧱 Tools Used

- Microsoft Sentinel (SIEM)
- Microsoft Defender for Cloud
- Azure Firewall
- Entra ID (Azure AD)
- Log Analytics Workspace

---

## ⚠️ Findings

- Suspicious login attempts detected
- IP anomaly flagged by Sentinel analytics rules
- Network segmentation prevented lateral movement

---

## 🛡️ Response Actions

- Account access reviewed and restricted
- Alert escalated to incident severity level
- Firewall rules validated and adjusted
- Logging rules improved for future detection

---

## 📊 Outcome

✔ Threat contained successfully  
✔ No data exfiltration occurred  
✔ Detection rules improved  
✔ Incident documented for SOC playbook

---

## 📸 Evidence

(Attach screenshots from Sentinel, logs, and firewall rules from your assets/labs folder)
