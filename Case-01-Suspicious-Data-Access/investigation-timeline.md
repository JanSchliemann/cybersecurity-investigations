# Investigation Timeline: Suspicious Data Access

| Time | User | Source IP | Event | Details |
|---|---|---|---|---|
| 08:42:11 | j.smith | 10.24.15.22 | Login | Successful login from normal internal IP |
| 09:03:27 | j.smith | 10.24.15.22 | File Access | Employee_Benefits.xlsx |
| 09:15:43 | j.smith | 10.24.15.22 | File Access | Customer_Records.csv |
| 09:47:19 | j.smith | 10.24.15.22 | File Access | Finance_Q3.xlsx |
| 10:12:04 | j.smith | 10.24.15.22 | File Access | HR_Salaries.xlsx |
| 10:34:51 | j.smith | 10.24.15.22 | File Access | Customer_Records.csv |
| 11:02:33 | j.smith | 10.24.15.22 | Logout | Normal session ended |
| 13:18:44 | j.smith | 185.71.44.19 | Login | Successful login from unfamiliar external IP |
| 13:21:07 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 13:22:18 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 13:24:52 | j.smith | 185.71.44.19 | File Access | HR_Salaries.xlsx |
| 13:27:41 | j.smith | 185.71.44.19 | File Access | Finance_Q3.xlsx |
| 13:29:03 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 13:31:26 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 13:34:17 | j.smith | 185.71.44.19 | File Access | Employee_Benefits.xlsx |
| 13:36:45 | j.smith | 185.71.44.19 | Logout | Session ended |
| 14:02:18 | j.smith | 185.71.44.19 | Login | Failed authentication |
| 14:03:02 | j.smith | 185.71.44.19 | Login | Failed authentication |
| 14:04:11 | j.smith | 185.71.44.19 | Login | Successful authentication |
| 14:05:33 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 14:07:49 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 14:10:15 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 14:13:27 | j.smith | 185.71.44.19 | File Access | Customer_Records.csv |
| 14:16:54 | j.smith | 185.71.44.19 | Logout | Session ended |
| 15:22:31 | j.smith | 10.24.15.22 | Login | Successful login from normal internal IP |
| 15:30:42 | j.smith | 10.24.15.22 | File Access | Employee_Benefits.xlsx |
| 16:01:18 | j.smith | 10.24.15.22 | Logout | Normal session ended |

## Investigation Highlights

### Normal Activity

The account's observed normal activity originated from `10.24.15.22`.

### Suspicious Activity

At 13:18:44, the account authenticated from the unfamiliar external IP `185.71.44.19` and subsequently accessed multiple sensitive files.

### Authentication Anomaly

At 14:02:18 and 14:03:02, authentication attempts from `185.71.44.19` failed. A successful authentication occurred at 14:04:11, followed by repeated access to `Customer_Records.csv`.

### Return to Normal Activity

At 15:22:31, the account authenticated again from the observed normal IP `10.24.15.22`.

### Investigation Significance

The timeline demonstrates a clear change in authentication source and access behavior, supporting the decision to investigate the activity as potentially unauthorized.
