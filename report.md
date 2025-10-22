Phishing Email Analysis Report

Cyber Security Internship – Task 2
Topic: Phishing Email Investigation and Header Analysis
Author: [Your Name]
Date: [Insert Date]

📌 1. Objective

To analyze a suspicious email and identify phishing indicators such as:

Sender domain spoofing

Header manipulation (SPF/DKIM/DMARC fails)

Mismatched URLs

Urgent or manipulative language

Suspicious attachments

Social engineering indicators

Goal:
Gain practical understanding of email threat analysis and phishing detection using real-world samples.

🧰 2. Tools & Resources Used

| Tool                      | Purpose                                         |
| ------------------------- | ----------------------------------------------- |
| MXToolbox Header Analyzer | For decoding and interpreting email header data |
| Google Admin Toolbox      | To trace sender path and authentication checks  |
| Phishing.org / PhishTank  | Safe sources for phishing email samples         |
| Browser Hover Inspection  | To reveal hidden or spoofed URLs                |
| VS Code / Text Editor     | To format and inspect raw header text           |

🔍 3. Sample Phishing Email Overview

Subject: Urgent: Verify your PayPal Account Immediately!
Sender (spoofed): support@paypai.com

Return-Path: support@paypai.com

Reply-To: security@paypal-login-alert.ru

Date: 21 Oct 2025, 08:34 AM
Email Type: Credential-stealing attempt (spoofed PayPal login link)

🖼️ Screenshot 1 – Phishing Email Body

(Attach image here — e.g., Screenshot of the email body showing the fake PayPal message)
📸 File: screenshots/email_body.png
Observation:
The email uses PayPal’s logo and colors to appear legitimate but contains grammar errors and urgency (“verify immediately”).

🧩 4. Header Analysis

Return-Path: <support@paypai.com>
Received: from unknown (HELO mail.fakehost.ru) (185.244.29.66)
  by mail.yourdomain.com with ESMTP; Mon, 21 Oct 2025 08:34:27 +0530
Received-SPF: Fail (domain of paypai.com does not designate 185.244.29.66)
Authentication-Results: spf=fail; dkim=none; dmarc=fail
Message-ID: <8FBA27C223D@mail.fakehost.ru>
From: "PayPal Support" <support@paypai.com>
Reply-To: <security@paypal-login-alert.ru>
X-Originating-IP: [185.244.29.66]
X-Spam-Status: Yes, score=9.8

🧾 Header Findings

| Parameter         | Observation                  | Meaning                                       |
| ----------------- | ---------------------------- | --------------------------------------------- |
| **SPF**           | Fail                         | Sender not authorized for paypai.com domain   |
| **DKIM**          | None                         | No digital signature (likely spoofed sender)  |
| **DMARC**         | Fail                         | Authentication mismatch – message quarantined |
| **Return-Path**   | Different from actual sender | Sign of email forwarding or spoofing          |
| **Reply-To**      | Mismatched domain (.ru)      | Redirects victims to phishing domain          |
| **X-Spam-Status** | Yes (score=9.8)              | Detected as high-risk phishing                |

🖼️ Screenshot 2 – Header Analyzer Result

(Attach screenshot of MXToolbox/Google MessageHeader output)
📸 File: screenshots/header_analysis.png
Observation:
SPF and DMARC both failed, indicating unauthenticated and spoofed sender domain.

🧠 5. Email Body Analysis

| Phishing Indicator    | Example from Email                              | Why It’s Suspicious            |
| --------------------- | ----------------------------------------------- | ------------------------------ |
| Urgent Language       | “Verify your account immediately!”              | Social engineering pressure    |
| Mismatched URL        | Text: paypal.com → Real: secure-paypal-login.ru | Redirects to attacker’s domain |
| Grammar Errors        | “You must verify you’re informations now.”      | Common in phishing scams       |
| Generic Greeting      | “Dear Customer”                                 | No personalization             |
| Suspicious Attachment | invoice.docm                                    | Potential malware dropper      |
| Visual Spoofing       | Uses PayPal logo                                | Imitation of trusted brand     |

🖼️ Screenshot 3 – Hovered URL Example

(Attach screenshot showing the real link vs displayed text)
📸 File: screenshots/url_hover.png
Observation:
Displayed URL: https://paypal.com/login
Actual URL: https://secure-paypal-login.ru/verify
→ Confirms URL mismatch/redirection.

⚙️ 6. Social Engineering Techniques Identified

| Technique              | Description                    | Example                               |
| ---------------------- | ------------------------------ | ------------------------------------- |
| **Urgency & Fear**     | Forces quick reaction          | “Account will be locked in 12 hours!” |
| **Authority**          | Pretends to be a trusted brand | “PayPal Security Team”                |
| **Scarcity**           | Limited time warning           | “Verify before midnight”              |
| **Trust Exploitation** | Uses real logos/colors         | Mimics legitimate PayPal design       |

📊 7. Summary Table

| Category          | Phishing Indicator         | Detected | Risk Level |
| ----------------- | -------------------------- | -------- | ---------- |
| Header Forgery    | SPF/DKIM Fail              | ✅        | High       |
| Domain Spoofing   | paypai.com ≠ paypal.com    | ✅        | High       |
| Fake Link         | Redirect to phishing page  | ✅        | High       |
| Urgent Tone       | Psychological manipulation | ✅        | Medium     |
| Grammar Errors    | Unprofessional writing     | ✅        | Low        |
| Attachment Threat | Suspicious .docm file      | ⚠️       | High       |

✅ 8. Conclusion

This email is a phishing attempt designed to:

Steal login credentials via a fake PayPal login page.

Possibly deliver malware through malicious attachments.

The analysis confirmed:

SPF/DKIM/DMARC failures

Spoofed sender domain

Fake URLs and manipulated header fields

Final Verdict:

🚨 Confirmed Phishing Email – Do not interact, click, or reply. Report to security team or email provider.

🧠 9. Learning Outcome

Understood how email headers authenticate senders (SPF/DKIM/DMARC).

Learned how to use tools for header tracing and link inspection.

Gained practical experience in identifying social engineering and spoofing tactics.
