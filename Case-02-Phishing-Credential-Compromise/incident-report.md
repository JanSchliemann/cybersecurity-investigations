# Incident Report: Phishing and Potential Credential Compromise

## Incident Summary

A simulated phishing email was sent to an employee of Northstar Bank impersonating RBC Digital Banking Security. The email used an urgent account verification request and directed the recipient to a suspicious external domain.

Approximately 24 minutes after the email was received, the employee's Business Banking account experienced multiple failed login attempts followed by a successful authentication from an unfamiliar external IP address.

Following the successful authentication, the account was used to access customer profile information and multiple account pages.

The activity is consistent with a potential credential compromise resulting from the phishing attempt. However, the available evidence does not confirm that credentials were successfully captured or that financial information was exfiltrated.

## Severity

**High**

The incident was assessed as High severity due to successful authentication from an unfamiliar external IP address followed by access to customer information.

## Timeline

| Time | Event |
|---|---|
| 09:17:42 | Phishing email received |
| 09:21:14 | Normal Windows login from internal IP `10.24.15.22` |
| 09:23:41 | Normal Business Banking login from `10.24.15.22` |
| 09:31:08 | Normal Business Banking logout |
| 09:42:17 | Failed Business Banking login from `185.71.44.19` |
| 09:42:31 | Second failed Business Banking login from `185.71.44.19` |
| 09:43:02 | Successful Business Banking authentication from `185.71.44.19` |
| 09:43:19 | Account accessed |
| 09:44:07 | Customer profile information accessed |
| 09:45:22 | Multiple account pages accessed |
| 09:47:51 | Business Banking session ended |
| 10:02:16 | Normal Windows login from `10.24.15.22` |

## Key Findings

### Phishing Email

The email contained several suspicious indicators:

- Impersonation of a banking security team
- Urgent language intended to pressure the recipient
- Suspicious sender domain
- Suspicious external verification URL
- Request to verify identity and account information
- SPF, DKIM, and DMARC authentication failures

### Authentication Activity

The authentication logs showed a significant change from the user's earlier activity.

Normal activity originated from internal IP address `10.24.15.22`.

Later activity originated from external IP address `185.71.44.19` and included:

- Two failed authentication attempts
- Successful authentication
- Account access
- Customer profile information access
- Multiple account page accesses

The sequence of events is consistent with potential unauthorized use of the employee's credentials.

## Indicators of Compromise

- **Email:** `security-alert@rbcdigital-secure.com`
- **Domain:** `rbcdigital-secure.com`
- **URL:** `https://rbcdigital-secure.com/verify`
- **IP Address:** `185.71.44.19`

Reputation checks did not identify confirmed malicious activity associated with the domain, URL, or IP address. The indicators remain suspicious based on their relationship to the phishing email and subsequent authentication activity.

## MITRE ATT&CK Mapping

### T1566.002 – Phishing: Spearphishing Link

The phishing email directed the recipient to an external verification URL designed to obtain account information.

### T1056.002 – Input Capture: GUI Input Capture

The phishing website could potentially capture credentials entered by the victim.

### T1078 – Valid Accounts

A successful Business Banking authentication occurred using the employee's account following the phishing attempt, which is consistent with potential use of compromised legitimate credentials.

## Impact Assessment

### Potential User Impact

- Unauthorized access to the employee's Business Banking account
- Potential financial loss or unauthorized transactions
- Potential exposure of personal or customer information
- Potential account takeover

### Potential Business Impact

- Financial losses or reimbursement costs
- Exposure of sensitive customer information
- Privacy, regulatory, or legal consequences
- Reputational damage and loss of customer trust
- Incident investigation and response costs

The available evidence does not confirm financial loss, unauthorized transactions, or data exfiltration.

## Recommended Containment

- Temporarily disable the affected user account
- Force a password reset
- Revoke active Business Banking sessions
- Require MFA reauthentication
- Block or flag the suspicious IP address
- Preserve relevant authentication and security logs
- Escalate the incident to the cybersecurity or incident response team

## Recommended Remediation

- Review all account and customer information accessed during the suspicious session
- Determine whether unauthorized transactions occurred
- Investigate whether the employee's credentials were compromised
- Search for additional activity involving the suspicious IP and other indicators
- Determine whether other employees received the same phishing campaign
- Block the phishing domain and URL through appropriate security controls
- Provide security awareness guidance to the affected employee
- Continue monitoring the affected account for additional suspicious activity

## Investigation Conclusion

The investigation identified a phishing email followed by suspicious authentication activity from an unfamiliar external IP address.

The combination of the phishing attempt, authentication failures, successful authentication, and subsequent access to customer information indicates a potential credential compromise and unauthorized account access.

The incident should be treated as a High-severity security event until additional evidence confirms the full scope and impact.

Further investigation of authentication, endpoint, network, transaction, and security monitoring data is recommended to determine whether additional unauthorized activity occurred.

## Evidence

- [Phishing Email](./evidence/phishing_email.txt)
- [Authentication Logs](./evidence/authentication_logs.csv)
- [Phishing Analysis](./phishing-analysis.md)
- [Investigation Timeline](./investigation-timeline.md)

## Disclaimer

All scenarios and data in this repository are simulated and created for educational and portfolio purposes. No real organizational, customer, employee, or security data is used.
