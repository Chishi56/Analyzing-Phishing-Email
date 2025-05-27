 
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
- **SPF:**  Pass (sender allowed). SPF only confirms that the email came from a valid server for that domain — not that the domain itself is trustworthy. In this case, the domain is not Binance’s, so SPF alone doesn’t prove legitimacy.
- **DKIM:**  Not signed. DKIM ensures the content was not tampered with in transit. Reputable companies like Binance always use DKIM to protect their brand. The absence of DKIM is a red flag.
- **DMARC:**  Weak (`bestguesspass`). DMARC tells receiving servers how to handle failed SPF/DKIM checks. No policy means anyone can spoof that domain more easily.
- Relayed via suspicious server: `serlogal.arnoia.com`

### 3️. Suspicious URL and message routing
- Text suggests Binance link, but actual URL:  
  `https://axobox.com/vt/wp-track.php`  
  ➤ Malicious link likely used for credential phishing or malware.
- From the Received lines in the header:<br>
  The email originated from IP 43.230.161.16, using:<br>
   `smtp.gmail.com` as the HELO name, then passed through serlogal.arnoia.com before reaching Outlook servers. This Indicates that `smtp.gmail.com` is being impersonated — the IP doesn’t belong to Gmail.
`serlogal.arnoia.com` is not associated with Binance or Google.

### 4. Spam Confidence Level (SCL) = 9
Microsoft Exchange added this header:
`X-MS-Exchange-Organization-SCL: 9`
- SCL (Spam Confidence Level) ranges from 0 (safe) to 9 (dangerous).

- A value of 9 means Microsoft flagged it as spam or phishing.



### 5. Mismatched URL (Hover Mismatch)
- Displayed button implied a **Binance** site. The button or link appeared to lead to Binance ("Open the official website"), but actually directed to this unrelated and suspicious domain.
- Hovering revealed **axobox.com**, unrelated and dangerous.
- This is a mismatched link — the display text doesn’t match the real destination.
- The domain is not owned by Binance.
- Could be used to steal credentials, drop malware, or redirect to fake login pages.

### 6. Urgency and Manipulation
- Claims of “data leak” and “compensation in Bitcoin”
- Urges recipient to act immediately — classic **social engineering** tactic.
- The email message used fear-based tactics, such as:

  “More than 120 data leaks have been recorded...”

  “Get compensated in Bitcoin...”

  “Open the official website”
  
These are social engineering techniques to create panic or urgency so that victims act without thinking — a common phishing hallmark.


---

##  Conclusion

This email is a **confirmed phishing attempt**. It impersonates a trusted brand, uses suspicious domains, bypasses authentication mechanisms, and contains a phishing link disguised under misleading text. It also uses classic manipulation tactics to deceive the recipient:
- Brand impersonation
- Suspicious sending domains
- Lack of DKIM/DMARC
- Dangerous redirect links
- Urgent and manipulative language

---

##  Actions Taken

- The link was **not clicked**.
- Full header analysis and link inspection were documented here.

---

##  Screenshots (Attached Separately)

- Phishing email screenshot using Sublime Security
- Header analysis using Google Admin Toolbox Messageheader, Sublime Security and Herokuapp EML Analyzer


