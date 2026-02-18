# Splunk Detection Queries

## Certutil Suspicious Download Detection

This rule detects potential malicious usage of the LOLBin `certutil.exe`, commonly abused by attackers to download payloads.

### Detection Logic
- Looks for process creation events (Sysmon Event ID 1)
- Filters for certutil execution
- Flags suspicious command-line patterns such as:
  - urlcache
  - verifyctl
  - HTTP-based downloads

### MITRE ATT&CK Mapping
- Technique: T1105 – Ingress Tool Transfer
- Technique: T1218 – Signed Binary Proxy Execution
