# MITRE ATT&CK — T1218 (Signed Binary Proxy Execution)

### Description
Attackers use trusted Windows binaries (LOLBINs) such as mshta, regsvr32, rundll32, wmic, certutil to execute malicious content.

### Examples
- mshta loading remote HTML
- regsvr32 executing COM scriptlets
- certutil downloading malicious payloads

### Common Indicators
- Parent process anomalies (office apps → LOLBIN)
- LOLBIN executing remote paths
- Unsigned DLL execution via rundll32
- HTA files running scripts

### Relevant Logs
- Sysmon 1 (Process Creation)
- Sysmon 7 (Image Loaded)
- Windows Event 4688

### Detection Approach
- Monitor unusual LOLBIN parameters.
- Alert on remote URLs.
- Flag LOLBINs executing from temp directories.

### Response
- Kill LOLBIN process.
- Block URL/IP.
- Check persistence.
- Perform full EDR sweep.

