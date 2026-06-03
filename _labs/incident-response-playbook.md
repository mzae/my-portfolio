---
layout: lab
title: "Incident Response Playbook"
permalink: /labs/incident-response-playbook/
---

# Incident Response Playbook

This lab demonstrates how a SOC Analyst responds to a phishing incident using Microsoft Sentinel.

## Objectives
- Detect suspicious sign-ins using KQL queries.
- Investigate alerts in Sentinel.
- Contain and remediate the incident.

## Example KQL Query
```kql
SigninLogs
| where ResultType == "50126"
| summarize count() by UserPrincipalName, IPAddress
