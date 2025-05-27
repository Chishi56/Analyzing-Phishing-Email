 
# Phishing Email Analysis – Binance Spoof Investigation

This project is part of a **Cybersecurity Internship Task** focused on identifying and analyzing phishing emails. The suspicious email reviewed here falsely claimed to be from **Binance**, a well-known cryptocurrency platform.

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
-  [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)
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

## Project Files Included


