# Investigation Timeline

| Time | Event | Analysis |
|---|---|---|
| 09:17:42 | Phishing email received | Employee received a phishing email impersonating a banking security team and directing them to a suspicious verification URL. |
| 09:21:14 | Windows login | Normal workstation login from internal IP `10.24.15.22`. |
| 09:23:41 | Business Banking login | Normal Business Banking authentication from `10.24.15.22`. |
| 09:31:08 | Business Banking logout | User ended the normal Business Banking session. |
| 09:42:17 | Failed login attempt | Business Banking login attempt from unfamiliar external IP `185.71.44.19` failed. |
| 09:42:31 | Failed login attempt | Second failed Business Banking login attempt from `185.71.44.19`. |
| 09:43:02 | Successful authentication | Business Banking authentication succeeded from `185.71.44.19`. |
| 09:43:19 | Account accessed | The authenticated session accessed the Business Banking account. |
| 09:44:07 | Customer information accessed | Customer profile information was accessed from the suspicious session. |
| 09:45:22 | Multiple account pages accessed | The session accessed multiple account pages. |
| 09:47:51 | Business Banking logout | The suspicious Business Banking session ended. |
| 10:02:16 | Windows login | Normal Windows login from internal IP `10.24.15.22`. |

## Investigation Sequence

**Phishing Email → Failed Authentication Attempts → Successful Authentication → Account Access → Customer Information Access → Multiple Account Pages Access**

The timeline shows a suspicious authentication sequence occurring approximately 24 minutes after the phishing email was received. The successful authentication from the unfamiliar external IP followed two failed attempts and was followed by access to account and customer information.

This activity is consistent with potential credential compromise and unauthorized account access. The available evidence does not confirm credential theft, financial loss, or data exfiltration.
