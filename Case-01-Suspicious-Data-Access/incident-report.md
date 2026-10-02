# Incident Report: Suspicious Data Access

## 1. Incident Overview

A security alert was generated for suspicious activity involving the user account `j.smith`. The activity includes authentication from an unfamiliar external IP address followed by access to multiple sensitive files.

## 2. Initial Triage

### User

j.smith

### Suspicious IP Address

185.71.44.19

### Initial Indicators

- Two failed login attempts occurred from `185.71.44.19` at 14:02 and 14:03.
- A successful login occurred from the same IP at 14:04.
- Sensitive files were accessed shortly after the successful login.
- `Customer_Records.csv` was accessed multiple times.
- `HR_Salaries.xlsx`, `Finance_Q3.xlsx`, and `Employee_Benefits.xlsx` were also accessed.
- The user's normal activity in the logs originated from `10.24.15.22`.

### Initial Assessment

The activity is considered suspicious because the successful authentication from an unfamiliar external IP was followed by access to multiple sensitive files.

### Initial Priority

High

## 3. Investigation Status

Initial triage completed. Further investigation is required to determine whether the activity represents legitimate user activity, account compromise, or unauthorized access to sensitive data.

## 4. Evidence Analysis

### Evidence 1: Unfamiliar Source IP

The account `j.smith` normally authenticated from the internal IP address `10.24.15.22`. The suspicious activity originated from `185.71.44.19`, which does not appear in the user's normal activity within the available logs.

### Evidence 2: Authentication Activity

The account successfully authenticated from `185.71.44.19` at 13:18:44. Later, two failed authentication attempts occurred from the same IP at 14:02:18 and 14:03:02, followed by another successful authentication at 14:04:11.

This sequence warrants investigation because repeated failed authentication attempts were followed by successful access.

### Evidence 3: Sensitive File Access

Following authentication from `185.71.44.19`, the account accessed multiple sensitive files, including:

- `Customer_Records.csv`
- `HR_Salaries.xlsx`
- `Finance_Q3.xlsx`
- `Employee_Benefits.xlsx`

`Customer_Records.csv` was accessed repeatedly during both suspicious sessions.

### Evidence 4: Change in Access Pattern

The user's normal activity occurred from `10.24.15.22`. The activity from `185.71.44.19` involved access to several sensitive files in a relatively short period.

The change in source IP and access pattern increases the likelihood that the activity requires further investigation.

## 5. Evidence Summary

The available evidence indicates suspicious activity involving the `j.smith` account. The primary indicators are:

1. Authentication from an unfamiliar external IP address.
2. Multiple failed authentication attempts followed by successful authentication.
3. Access to multiple sensitive files.
4. Repeated access to `Customer_Records.csv`.
5. A significant change from the user's observed normal access pattern.

The evidence is consistent with potential unauthorized account activity. However, the available logs alone do not establish whether the account was compromised or whether the activity was authorized.

## 6. MITRE ATT&CK Mapping

The observed activity was mapped to the following MITRE ATT&CK techniques based on the available evidence.

| Technique | ID | Relevance to Investigation |
|---|---|---|
| Valid Accounts | T1078 | The `j.smith` account successfully authenticated from an unfamiliar external IP address, indicating potential unauthorized use of a legitimate account. |
| Data from Local System | T1005 | The account accessed multiple sensitive files, including customer records, employee salary information, financial information, and employee benefits information. |

### Mapping Assessment

The available evidence supports potential use of a legitimate account to access sensitive information. However, the logs do not establish whether the account was compromised or whether the accessed information was copied or exfiltrated.

Additional endpoint, authentication, VPN, and network evidence would be required to identify further ATT&CK techniques with confidence.

## 7. Impact and Severity Assessment

### Potential Impact

The suspicious activity involved an employee account accessing multiple sensitive business files from an unfamiliar external IP address.

The potentially affected information includes:

- Customer records
- Employee salary information
- Financial forecasting information
- Employee benefits information

If the activity was unauthorized, the exposure of this information could create privacy, financial, operational, and regulatory risks for the organization.

### Severity

**Severity: High**

### Severity Rationale

The incident is assessed as High based on the combination of:

- Successful authentication from an unfamiliar external IP.
- Multiple failed authentication attempts followed by successful authentication.
- Access to multiple sensitive files.
- Repeated access to customer records.
- A significant change from the user's normal access pattern.

The available evidence does not confirm that data was downloaded, copied, or exfiltrated. Therefore, the assessment is based on the potential impact of the observed access rather than confirmed data loss.

### Affected Assets

- User account: `j.smith`
- Internal file resources containing customer, employee, and financial information
- Authentication infrastructure
- Corporate data environment

### Current Impact Assessment

**Potential unauthorized access to sensitive data**

Further investigation is required to determine whether the activity was legitimate and whether any data was actually removed from the environment.

## 8. Containment and Remediation Recommendations

### Immediate Containment

1. Temporarily disable the `j.smith` account or require an immediate password reset.
2. Revoke active sessions and authentication tokens associated with the account.
3. Investigate and restrict access from `185.71.44.19` while the investigation is ongoing.
4. Review the account's permissions and temporarily restrict access to sensitive data if necessary.

### Investigation and Validation

5. Confirm with the user whether the activity from `185.71.44.19` was legitimate.
6. Review additional authentication, VPN, endpoint, and network logs to determine the origin of the activity.
7. Determine whether any files were downloaded, copied, modified, or transferred outside the organization.
8. Review access logs for additional suspicious activity involving the account.

### Remediation

9. Reset credentials and enforce multi-factor authentication if not already enabled.
10. Review and reduce unnecessary access privileges for the affected account.
11. Monitor the account for additional suspicious activity following restoration.
12. Document the investigation, findings, actions taken, and final outcome.

### Recommended Priority

**Immediate**

The account and associated access should be investigated and contained promptly due to the potential unauthorized access to sensitive customer, employee, and financial information.

## 9. Final Investigation Conclusion

### Investigation Summary

The investigation examined suspicious activity involving the `j.smith` account. The account normally authenticated from the internal IP address `10.24.15.22`. Activity was also observed from the unfamiliar external IP address `185.71.44.19`.

The account successfully authenticated from the external IP and subsequently accessed multiple sensitive files, including customer records, employee salary information, financial forecasting information, and employee benefits information.

Two additional authentication failures were observed from the same external IP before another successful authentication. Following this authentication, the account repeatedly accessed `Customer_Records.csv`.

### Findings

The investigation identified the following indicators:

- Authentication from an unfamiliar external IP.
- Multiple failed authentication attempts followed by successful authentication.
- Access to multiple sensitive files.
- Repeated access to customer records.
- A significant change from the user's observed normal access pattern.

### Conclusion

The activity is considered **suspicious and requires security investigation and containment**.

The available evidence is consistent with potential unauthorized use of the `j.smith` account. However, the available logs do not provide sufficient evidence to confirm that the account was compromised or that data was successfully exfiltrated.

Additional authentication, endpoint, VPN, and network logs should be reviewed to determine the source of the activity and whether sensitive information was transferred outside the organization.

### Recommended Actions

- Validate the activity with the account owner.
- Reset credentials and revoke active sessions if unauthorized activity is confirmed or cannot be validated.
- Investigate the external IP address and related authentication activity.
- Review endpoint, VPN, and network logs for additional evidence.
- Determine whether sensitive files were downloaded or transferred.
- Review account permissions and apply least-privilege access.
- Continue monitoring the account for additional suspicious activity.
- Document the final investigation outcome and remediation actions.

### Final Severity

**High**

### Investigation Status

**Pending further investigation**
