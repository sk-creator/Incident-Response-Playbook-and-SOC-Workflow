# Incident Response Playbook (Generic SOC Playbook)

## 1. Incident Summary
Document a short description of the incident type, detection source, and initial context.

## 2. Identification
- Validate alert severity and context.
- Pull raw logs from SIEM (Splunk/Sentinel/QRadar).
- Identify user, source IP, process, timestamp.
- Correlate logs across:
  - Windows Event Logs (4624, 4625, 4688)
  - Sysmon (1, 3, 7, 11)
  - EDR detections
  - DNS/Proxy/Firewall logs

## 3. Containment
- Disable compromised user accounts.
- Kill malicious processes.
- Block indicators (IP, domain, hash).
- Isolate host from network.
- Prevent lateral movement.

## 4. Eradication
- Remove malware or artifacts.
- Clean persistence (registry, scheduled task, WMI).
- Patch vulnerabilities.
- Reset credentials.

## 5. Recovery
- Re-enable accounts.
- Restore normal operations.
- Validate endpoint health.
- Monitor for re-infection for 24–48 hours.

## 6. Lessons Learned
- Document root cause & timeline.
- Tune detections to reduce false positives.
- Update SOPs/Playbooks.
- Add new indicators to threat intel feeds.

