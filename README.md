 
# Phishing Email Analysis – Binance Spoof Investigation

This project involves the analysis of a phishing email that impersonates Binance, a popular cryptocurrency platform. The goal is to identify indicators of phishing and validate the email’s authenticity through header inspection and link analysis.

---

##  Overview

- **Email Subject:** Binance Cybersecurity
- **Sender Address:** info@libreriacies.es
- **Claimed Brand:** Binance
- **Actual Link:** https://axobox.com/vt/wp-track.php (not related to Binance)
- **Spoof Type:** Brand Impersonation + Link Mismatch

---

## Objective

- Examine sender details for spoofing
- Analyze email headers for security discrepancies
- Identify suspicious links and mismatched URLs
- Look for signs of social engineering or urgency in the message

---

##  Tools Used

-  [Email Sample](email/sample-1000.eml)
-  [Google Admin Message Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/)
-  [EML Analyzer - Sublime Security](https://analyzer.sublime.security/)  
-  [EML Analyzer - Herokuapp](https://eml-analyzer.herokuapp.com/#/)


----

##  Phishing Indicators Found

### 1️. Sender Address Mismatch
- Claimed to be Binance, but sent from `libreriacies.es`, a **non-Binance domain**.

### 2️. Email Header Discrepancies
- **SPF:**  Pass (sender allowed)
- **DKIM:**  Not signed
- **DMARC:**  Weak (`bestguesspass`)
- Relayed via suspicious server: `serlogal.arnoia.com`

### 3️. Suspicious URL
- Text suggests Binance link, but actual URL:  
  `https://axobox.com/vt/wp-track.php`  
  ➤ Malicious link likely used for credential phishing or malware.

### 4️. Mismatched URL (Hover Mismatch)
- Displayed button implied a **Binance** site.
- Hovering revealed **axobox.com**, unrelated and dangerous.

### 5️. Urgency and Manipulation
- Claims of “data leak” and “compensation in Bitcoin”
- Urges recipient to act immediately — classic **social engineering** tactic.

---

##  Conclusion

This email is a **confirmed phishing attempt**. It uses:
- Brand impersonation
- Suspicious sending domains
- Lack of DKIM/DMARC
- Dangerous redirect links
- Urgent and manipulative language

---

##  Actions Taken

- The email was **reported as phishing** using built-in email security tools.
- The link was **not clicked**.
- Full header analysis and link inspection were documented here.

---

##  Screenshots (Attached Separately)

- Phishing email screenshot using Sublime Security
- Header analysis using Google Admin Toolbox Messageheader and Herokuapp EML Analyzer


