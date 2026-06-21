# Thynk Unlimited: Phishing Detection & Awareness Training Framework
**Reference Document:** SEC-AR-2026-004  
**Presented By Dhanush  

---

## 📌 Project Overview
Human error remains the primary vector for network breaches, accounting for the majority of successful cyberattacks. Threat actors exploit domain spoofing to impersonate trusted senders, leverage psychological manipulation to bypass rational judgment, and deploy obfuscated hyperlinks to conceal malicious destinations. 

This repository functions as a professional project blueprint containing the core threat verification architectures, triage protocols, and authentication analysis workflows designed to strengthen our human defense layer and protect corporate networks.

---

## 🛠️ Repository Blueprint Structure
To ensure this triage architecture remains scannable and maintainable for client review, the repository is organized using the following structural framework:

├── README.md                 <- Main landing page; contains project overview & methodology
├── docs/
│   └── phishing_report.md    <- Core detection & awareness framework report
├── samples/
│   ├── raw_phishing_sample.eml  <- Plaintext/EML file containing the target threat sample
│   └── headers/
│       └── sanitized_header.txt <- Raw email header used for analyzer tool ingestion
└── assets/
    └── framework_diagram.png <- Visual representation of triage or verification architecture

---

## 🛡️ Corporate Threat Classification Framework
Every incoming email undergoes specific analysis parameters to evaluate threat levels and dictate mandatory response actions:

| Risk Tier | Technical Indicators | Mandatory Action |
| :--- | :--- | :--- |
| **Low Risk** | Validated signatures; SPF/DKIM/DMARC all **PASS**. Standard business processing. | Process through standard workflows. |
| **Medium Risk** | External origin mimicking internal senders; Display name mismatches; Unusual requests. | **Do Not Engage:** Do not reply, click links, or open attachments. Report via internal ticketing system. |
| **High Risk** | Spoofed domains; Coercive/urgent tone; Look-alike domains; Double-extension attachments (e.g., `.pdf.exe`). | **Incident Escalation:** Escalate to Incident Response via official security channels. Preserve sample as evidence. |

---

## 🧩 Technical Deep Dive: Email Authentication Protocols
To effectively analyze headers ingested via `samples/headers/`, our verification framework tracks three critical enforcement layers:

* **SPF (Sender Policy Framework):** Acts as a public guest list for our email domain by specifying which IP addresses are authorized to send mail on behalf of the organization.
* **DKIM (DomainKeys Identified Mail):** Provides a digital tamper-proof seal using cryptographic key pairs to embed a unique signature into the email header, validating transit integrity.
* **DMARC Enforcement Protocol:** Uses the comparative results of SPF and DKIM to determine handling alignment via three progressive modes:
  * **Policy: None** -> Monitoring mode only; failures are logged for analysis.
  * **Policy: Quarantine** -> Suspicious emails are routed directly to the recipient's spam/junk folder.
  * **Policy: Reject** -> Unauthorized emails are blocked entirely and never delivered.

---

## 🚦 Decision Flowchart & Triage Protocol
When triage analysts or end-users interact with an email, the following evaluation pipeline must be applied:
1. **Incoming Email:** Open for initial textual and metadata review.
2. **Sender Origin Verification:** Check the actual sender address domain to determine if it is internal or external.
3. **Payload & Vector Assessment:** Assess if the email demands immediate action, leverages coercive language, or contains obfuscated links/attachments.
4. **Execution/Escalation:** Route the message according to standard processing procedures or alert the Security Team.

---

## 🛑 Security Best Practices (Mandatory Protocols)

### The Do's
* **Inspect Real Senders:** Always hover over display names to check the actual sender address domain in the email header.
* **Independent Verification:** Verify urgent internal requests via a separate, trusted channel (e.g., phone call or Slack)—never use provided contact details.
* **URL Inspection:** Hover over hyperlinks to verify the actual destination URL before clicking.
* **Report Active Threats:** Utilize the "Report Phishing" button in Outlook immediately.

### The Don'ts
* **Do Not** rely on brand imagery or logos alone.
* **Do Not** use contact information contained within a suspicious email.
* **Do Not** open double-extension attachments (e.g., `.docx.js`).
* **Do Not** input Multi-Factor Authentication (MFA) codes generated from email links.

---

## 📞 Escalation & Contact
For active threat containment, credential compromise incidents, or system tampering alerts:
* **Security Team Portal:** `security@company.com`  
* **Emergency Escalation:** Official Incident Response Channel
