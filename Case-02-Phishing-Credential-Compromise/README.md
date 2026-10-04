# Case 02: Phishing and Credential Compromise Investigation

Hands-on cybersecurity investigation focused on phishing analysis, indicator investigation, authentication analysis, and potential credential compromise.

## Case Overview

A simulated bank employee received a phishing email impersonating a banking security team. The email directed the employee to a suspicious account verification page and requested account information.

Approximately 24 minutes later, the employee's Business Banking account experienced multiple failed login attempts followed by a successful authentication from an unfamiliar external IP address.

The account was subsequently used to access customer profile information and multiple account pages.

## Investigation Process

1. Analyze the phishing email
2. Extract indicators of compromise
3. Investigate domain, URL, and IP reputation
4. Analyze authentication logs
5. Establish an investigation timeline
6. Assess potential user and business impact
7. Map activity to MITRE ATT&CK
8. Recommend containment and remediation
9. Document investigation findings

## Tools Used

- VirusTotal
- URLQuery
- CSV log analysis
- MITRE ATT&CK

## Key Findings

- Phishing email impersonated a banking security team
- Suspicious external domain and URL were identified
- SPF, DKIM, and DMARC authentication checks failed
- Two failed login attempts originated from an unfamiliar external IP
- Successful authentication followed the failed attempts
- Customer profile information was accessed
- Multiple account pages were accessed
- Activity was consistent with potential credential compromise and unauthorized account access

## MITRE ATT&CK Techniques

- **T1566.002 – Phishing: Spearphishing Link**
- **T1056.002 – Input Capture: GUI Input Capture**
- **T1078 – Valid Accounts**

## Skills Demonstrated

- Phishing investigation
- Email header analysis
- IOC extraction
- Threat intelligence research
- Authentication log analysis
- Incident timeline development
- User and business impact assessment
- MITRE ATT&CK mapping
- Incident triage
- Containment and remediation planning
- Security documentation

## Investigation Files

- [Incident Report](./incident-report.md)
- [Investigation Timeline](./investigation-timeline.md)
- [Phishing Analysis](./phishing-analysis.md)
- [Phishing Email](./evidence/phishing_email.txt)
- [Authentication Logs](./evidence/authentication_logs.csv)

## Disclaimer

All scenarios and data in this repository are simulated and created for educational and portfolio purposes. No real organizational, customer, employee, or security data is used.
