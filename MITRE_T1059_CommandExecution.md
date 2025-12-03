# MITRE ATT&CK — T1059 (Command Execution)

### Description
Adversaries use command-line interfaces like PowerShell, CMD, bash, wscript, cscript to execute malicious commands.

### Common Indicators
- Encoded PowerShell (`-enc`, `-EncodedCommand`)
- unusual parent processes (office apps spawning PowerShell)
- External IP connections from script hosts
- Suspicious file writes or downloads

### Relevant Log Sources
- Sysmon ID 1 (Process Creation)
- Sysmon ID 3 (Network Connection)
- Event ID 4688 (Process Creation)
- PowerShell Operational Logs (4104)

### Detection Ideas
- Detect encoded commands.
- Alert on PowerShell launched by winword.exe, excel.exe.
- Identify remote script execution.
- Correlate child-parent anomalies.

### Response
- Decode base64.
- Kill script host.
- Block associated IOCs.
- Isolate endpoint.
- Check for persistence.

