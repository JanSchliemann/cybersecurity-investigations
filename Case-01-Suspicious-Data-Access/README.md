# Case 01: Suspicious Data Access Investigation

Hands-on cybersecurity investigation focused on suspicious authentication activity and potential unauthorized access to sensitive data.

## Case Overview

A simulated security alert identified suspicious activity involving an employee account. The account authenticated from an unfamiliar external IP address and subsequently accessed multiple sensitive files.

The investigation examined authentication activity, source IPs, file access patterns, potential impact, and appropriate containment and remediation actions.

## Investigation Process

1. Detect
2. Triage
3. Analyze Evidence
4. Establish Timeline
5. Assess Impact
6. Map Findings to MITRE ATT&CK
7. Recommend Containment and Remediation
8. Document Findings

## Skills Demonstrated

- Security incident investigation
- Log analysis
- Authentication analysis
- IP and access pattern analysis
- Data access monitoring
- MITRE ATT&CK mapping
- Incident triage
- Evidence analysis
- Risk and impact assessment
- Containment and remediation planning
- Incident documentation
- Security communication

## Key Findings

- Successful authentication from an unfamiliar external IP address
- Multiple failed authentication attempts followed by successful authentication
- Access to multiple sensitive files
- Repeated access to customer records
- Significant change from the user's observed normal access pattern

## MITRE ATT&CK Techniques

- **T1078: Valid Accounts**
- **T1005: Data from Local System**

## Investigation Result

The activity was assessed as suspicious and assigned a **High priority** due to potential unauthorized access to sensitive customer, employee, and financial information.

The available evidence did not confirm account compromise or data exfiltration. Additional authentication, endpoint, VPN, and network evidence would be required to determine the full scope of the activity.

## Recommended Response

- Validate the activity with the account owner
- Review authentication, endpoint, VPN, and network evidence
- Reset credentials and revoke active sessions if unauthorized activity is confirmed
- Review account permissions and apply least-privilege access
- Continue monitoring for additional suspicious activity

## Files

- [Incident Report](./incident-report.md)
- [Investigation Timeline](./investigation-timeline.md)
- [Security Logs](./evidence/case1_security_logs.csv)

## Disclaimer

All scenarios and data in this repository are simulated and created for educational and portfolio purposes. No real organizational, customer, employee, or security data is used.
