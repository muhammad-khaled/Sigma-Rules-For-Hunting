# Sigma-Rules-For-Hunting
A curated collection of Sigma rules tailored for threat hunting activities. This repository provides ready-to-use detection logic, with mappings to KQL for Microsoft Defender and other SIEM/XDR platforms. Ideal for security teams looking to accelerate hunting and detection engineering.

If you’re a SOC Analyst, Threat Detection, or Threat Hunter, Sigma rules are one of the most practical ways to make your hunting proactive, scalable, and consistent across tools.  

 
1 — From data to hypothesis to action  
• Collect: CTI, dark web monitoring, reports, proactive thinking  
• Form: Build a clear hypothesis (what activity, where, and why)  
• Act: Turn that hypothesis into documented, reusable detections  
 

2 — What is Sigma?  
• A universal detection rule format written in YAML  
• Write once, convert to many detection languages and platforms
• Standardized structure for clear, maintainable hunting content  


3 — Basic Structure of a Sigma Rule  
title: Suspicious PowerShell  
id: uuid  
status: stable  
description: Detects encoded PowerShell  
logsource:  
  product: Windows  
  category: process_creation  
Detection:  
  Selection:  
    CommandLine|contains: 'malicious.exe'  
condition: selection  
falsepositives:  
  - Legitimate admin tool  
level: high  
tags:  
  - attack.execution  
  - attack.t1059.001  


4 — Key Parts Explained Simply  
• title → Rule name (“Suspicious PowerShell”)  
• id → Unique ID (uuid format)  
• status → Rule maturity (test, stable, etc.)  
• description → What it detects (“Detects encoded PowerShell”)  
• logsource → Where to look (Windows, Linux, etc.)  
• detection → What to match (EventID, CommandLine, etc.)  
• condition → How to match (selection/selection and not filter)  
• falsepositives → Known noise (Legit WMI use)  
• level → Severity (medium, high, etc.)  
• tags → MITRE ATT&CK mapping (attack.persistence)  


5 — Benefits of adopting Sigma  
• Consistency: Shared language across teams and tools  
• Scalability: One rule, many backends  
• Documentation: Clear evidence of intent and outcomes  
• Velocity: Faster hypothesis testing and repeatable hunts  