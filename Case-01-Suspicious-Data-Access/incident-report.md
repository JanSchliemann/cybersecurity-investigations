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

## 6. Impact and Severity Assessment

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
