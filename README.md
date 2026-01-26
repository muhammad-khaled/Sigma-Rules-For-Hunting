# Sigma Detection Pack – Behavioral & Threat-Centric Rules

## Author
**Mohamed Khaled Ibrahim**  
Senior Cyber Security Analyst | Threat Hunter & Detection Engineering  
Date: 2025-08-28

## Overview
This Sigma rule pack focuses on high-fidelity detections across execution, persistence, network anomalies, and abuse of trusted binaries. It is designed to support SOC operations, threat hunting, and proactive defense against adversary behaviors mapped to MITRE ATT&CK.

## Rule Categories
- **Execution & Scripting Abuse**: Detects obfuscated PowerShell, suspicious rundll32/wscript usage, and non-baselined child processes.
- **Persistence & Evasion**: Flags startup folder abuse, scheduled tasks, firewall changes, and signed binary proxy execution.
- **Network & C2 Detection**: Identifies outbound connections to public IPs, remote WMIC execution, and IP scanning behavior.
- **Authentication & Access**: Detects logon attempts from public IPs and shared folder access.
- **System Masquerading**: Captures explorer.exe and conhost.exe launched from unusual paths or parents.
- **Defender & Exploit Guard Events**: Monitors blocked outbound traffic via Defender Exploit Guard.

## MITRE ATT&CK Coverage
This pack maps to the following techniques:
- `T1059` – Command and Scripting Interpreter  
- `T1071` – Application Layer Protocol  
- `T1053.005` – Scheduled Task  
- `T1547.001` – Startup Folder  
- `T1021.001/002` – Remote Services  
- `T1562.004` – Disable or Modify System Firewall  
- `T1218` – Signed Binary Proxy Execution  
- `T1036` – Masquerading  
- `T1046` – Network Service Scanning  
- `T1486` – Data Encrypted for Impact

## Deployment Notes
- Rules are tagged `experimental` and should be tested in detection-only mode before enforcement.
- Use Sigma converters (`sigmac`) to deploy across Splunk, Sentinel, Elastic, etc.
- Tune false positives based on environment-specific baselines and automation scripts.

## Attribution
All rules authored and validated by **Mohamed Khaled Ibrahim**, with modular design and operational metadata for SOC enablement and public sharing.

## License

This pack is intended for internal SOC use and community collaboration. Attribution required if redistributed.


