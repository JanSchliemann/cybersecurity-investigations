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
