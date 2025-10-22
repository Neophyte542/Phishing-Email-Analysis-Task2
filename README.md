# Phishing-Email-Analysis-Task2
Phishing Email Analysis – Cyber Security Internship Task 2 This repository contains an analysis of a sample phishing email as part of my cybersecurity internship. The task involves identifying phishing indicators such as sender spoofing, header discrepancies, suspicious URLs, grammar errors, and social engineering techniques. Tools used include online header analyzers and manual inspection.

Outcome: Gained hands-on experience in phishing detection, email header analysis, and threat awareness.

Objective

To analyze a suspicious email sample and identify phishing indicators such as:

1. Sender spoofing

2. Header discrepancies

3. Mismatched URLs

4. Urgent or manipulative language

5. Suspicious attachments

6. Social engineering patterns

Goal:
Develop hands-on skills in phishing detection, header analysis, and threat awareness.

| Tool / Platform                          | Purpose                                                    |
| ---------------------------------------- | ---------------------------------------------------------- |
| **MXToolbox Email Header Analyzer**      | To inspect and interpret email header details.             |
| **Google Admin Toolbox (Messageheader)** | To trace message delivery path and check SPF/DKIM results. |
| **PhishTank / Phishing.org Samples**     | To obtain safe phishing email examples for analysis.       |
| **Text Editor (VS Code / Notepad++)**    | For analyzing raw email headers and writing the report.    |

🔬 Step-by-Step Process
1. Collecting the Sample Email

Downloaded a known phishing email claiming to be from PayPal Support with subject:

“⚠️ Your account has been locked! Verify immediately.”

2. Header Analysis

Extracted raw email header from the email client.

Analyzed using MXToolbox
.

Findings:

Sender domain: support@paypai.com (spoofed)

SPF: Fail

DKIM: None

Return-Path: reply@mail.ru

Received path shows multiple unknown relay IPs.

Email Body Inspection:

| Indicator                  | Observation                                                            | Description                                    |
| -------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------- |
| **Urgency**                | “Verify your account immediately or it will be locked!”                | Classic social engineering to trigger panic.   |
| **Mismatched URL**         | Link text: `paypal.com` → Actual URL: `https://secure-paypal-login.ru` | Redirects to a fake domain.                    |
| **Grammar Errors**         | “Your informations is required.”                                       | Poor grammar, typical in phishing emails.      |
| **Generic Greeting**       | “Dear Customer”                                                        | No personalization — typical of bulk phishing. |
| **Suspicious Attachments** | “Invoice.docm” (macro-enabled)                                         | Potential malware carrier.                     |

4. Link Analysis (Safe Hovering)

Hovered over links instead of clicking.

Observed that the displayed text and destination URL didn’t match.

URL uses .ru TLD, not related to legitimate PayPal servers.

5. Social Engineering Techniques

Fear / Urgency: Forces the user to act fast (“verify now”).

Trust Exploitation: Uses PayPal’s brand and logo.

Authority: Pretends to be from customer service.

📊 Summary of Findings
| Category             | Indicator Found                  | Status |
| -------------------- | -------------------------------- | ------ |
| Sender Spoofing      | Fake domain (`paypai.com`)       | ✅      |
| Header Tampering     | SPF fail, DKIM missing           | ✅      |
| Suspicious Link      | Redirect to fake login           | ✅      |
| Urgent Language      | “Your account will be suspended” | ✅      |
| Grammar / Formatting | Errors, fake branding            | ✅      |
| Attachment Threat    | `.docm` file                     | ⚠️     |
| Social Engineering   | Fear + Authority techniques      | ✅      |

Key Learning Outcomes

1. Understanding of SPF/DKIM/DMARC roles in verifying email authenticity.

2. Ability to identify phishing characteristics through header and body analysis.

3. Awareness of how social engineering manipulates user behavior.

   
