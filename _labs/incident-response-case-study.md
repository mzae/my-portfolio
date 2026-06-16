---
title: "Incident Response Case Study"
layout: lab
author: Wanjama Daniel
permalink: /labs/incident-response-case-study/
---

This lab simulates a ransomware attack response scenario, including endpoint isolation, forensic analysis, and PowerShell automation for SOC workflows.

## Objectives

- Detect ransomware indicators
- Isolate compromised endpoints
- Perform incident investigation
- Automate response actions
- Document findings

## Prerequisites

- Microsoft Sentinel and Defender setup
- PowerShell knowledge
- Incident response procedures

## Incident Scenario

A ransomware attack compromises a critical server. The lab demonstrates:

1. **Detection**: Identifying suspicious file encryption activity
2. **Isolation**: Blocking network access from the compromised system
3. **Analysis**: Reviewing logs and identifying attack vector
4. **Response**: Automating remediation through PowerShell
5. **Recovery**: Restoring from backups

## Key Automation Scripts

### Isolate VM on Detection

```powershell
$ResourceGroup = "RG-Critical"
$VMName = "CompromisedVM"
$NSGName = "NSG-Isolation"

# Create deny-all rule
New-AzNetworkSecurityRuleConfig -Name "DenyAll" `
  -Protocol "*" -SourcePortRange "*" -DestinationPortRange "*" `
  -SourceAddressPrefix "*" -DestinationAddressPrefix "*" `
  -Access "Deny" -Priority 100 -Direction "Inbound"
```

## References

- [Incident Response Best Practices](https://learn.microsoft.com/en-us/security/incident-response/)
- [Sentinel Automation](https://learn.microsoft.com/en-us/azure/sentinel/automate-responses-with-playbooks)
