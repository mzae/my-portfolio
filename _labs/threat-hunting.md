---
title: "Threat Hunting with KQL"
layout: lab
author: Wanjama Daniel
permalink: /labs/threat-hunting/
---

This lab demonstrates how to detect anomalies in sign-in logs and network traffic using KQL queries for brute force and suspicious activity detection within Microsoft Sentinel.

## Objectives

- Write effective KQL queries for threat detection
- Analyze sign-in logs for suspicious patterns
- Detect brute force attacks
- Monitor network anomalies
- Create custom detection rules

## Prerequisites

- Microsoft Sentinel environment
- Access to Log Analytics workspace
- Familiarity with KQL (Kusto Query Language)

## Key Queries

### Detecting Brute Force Attacks

```kusto
SigninLogs
| where TimeGenerated > ago(1d)
| where ResultDescription contains "Invalid password"
| summarize FailureCount = count() by UserPrincipalName, IPAddress
| where FailureCount > 10
```

### Anomalous Sign-in Detection

```kusto
SigninLogs
| where TimeGenerated > ago(7d)
| where RiskState == "atRisk"
| project TimeGenerated, UserPrincipalName, IPAddress, Location, RiskState
```

## References

- [KQL Query Language](https://learn.microsoft.com/en-us/kusto/query/)
- [Sentinel Threat Detection](https://learn.microsoft.com/en-us/azure/sentinel/detect-threats-custom)
