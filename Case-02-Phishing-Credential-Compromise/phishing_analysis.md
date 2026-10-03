# Phishing Email Analysis

## Suspicious Indicators

### 1. Urgent Subject
**Indicator:** Urgent: Your RBC Business Banking Access Requires Verification

**Analysis:** The urgent language attempts to pressure the recipient into taking immediate action without carefully evaluating the message.

### 2. Suspicious Link
**Indicator:** https://rbcdigital-secure.com/verify

**Analysis:** The link uses a domain that does not match the legitimate banking organization's domain and may be designed to capture user information.

### 3. Suspicious Sender
**Indicator:** security-alert@rbcdigital-secure.com

**Analysis:** The sender domain does not appear to be an official banking domain despite the message claiming to represent RBC.

### 4. Credential and Account Information Request
**Indicator:** The email asks the recipient to verify their identity and account information.

**Analysis:** This could be an attempt to obtain credentials or other information that could enable account compromise.

### 5. Email Authentication Failures
**Indicator:** SPF, DKIM, and DMARC all failed.

**Analysis:** The authentication failures provide technical evidence that the email did not pass expected email authentication controls.

## Indicators of Compromise

- **Sender:** security-alert@rbcdigital-secure.com
- **Domain:** rbcdigital-secure.com
- **URL:** https://rbcdigital-secure.com/verify
- **IP Address:** 185.71.44.19
