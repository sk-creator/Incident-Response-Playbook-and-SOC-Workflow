# SOC Standard Operating Procedure (SOP)

## 1. Alert Validation
- Check severity, source, frequency.
- Confirm whether alert is True Positive or False Positive.
- Cross-reference with historical activity baseline.

## 2. Evidence Collection
- Collect all relevant logs:
  - Windows (Security, PowerShell)
  - Sysmon (1, 3, 7, 11)
  - EDR telemetry
  - DNS and Proxy logs
  - Firewall events
- Take screenshots or export logs for documentation.

## 3. Analysis
- Build process tree.
- Enrich indicators (VirusTotal, OTX, AbuseIPDB).
- Identify persistence or lateral movement.

## 4. Containment Procedure
- Kill malicious processes.
- Isolate host.
- Disable accounts.
- Block IP/domains at firewall.

## 5. Eradication Procedure
- Remove malware.
- Clean autoruns, tasks, registry.
- Patch vulnerabilities.

## 6. Escalation Guidelines
- Escalate P1 and P2 alerts to L2/L3 immediately.
- Provide clear evidence and summary.

## 7. Documentation
- Update ServiceNow/JIRA with:
  - Timeline
  - Logs
  - Actions taken
  - Impact analysis
  - Resolution notes
