# Phishing-Email-Forensics
Investigated a legitimate RedCloud recruitment email and a phishing email impersonating Amazon using email header analysis, IP address investigation, SPF/DKIM/DMARC checks, sender infrastructure analysis, and embedded link inspection to identify phishing indicators and verify email authenticity.

# Phishing Email Forensics
### A Comparative Forensic Analysis of a Legitimate Email and a Phishing Email

## Project Overview
This project investigates two real emails received in a live inbox: a legitimate recruitment notification from RedCloud and a phishing email impersonating Amazon. The investigation uses email header analysis, authentication checks, IP address investigation, domain analysis, and URL redirect tracing to identify indicators of legitimacy and phishing.

## Objectives
- Analyze raw email headers to investigate sender identity and message origin.
- Verify SPF, DKIM, and DMARC authentication results.
- Investigate sending IP addresses, ownership, and reputation.
- Examine email domains and embedded links.
- Trace URL redirect chains to identify suspicious destinations.
- Compare legitimate email characteristics with phishing indicators.

## Tools Used
- **Gmail – Show Original:** Extracted raw email headers and source information.
- **Notepad:** Inspected raw `.eml` files.
- **MXToolbox:** Checked domain and mail server health.
- **AbuseIPDB:** Investigated IP reputation and abuse history.
- **VirusTotal:** Analyzed URLs, redirect chains, and destination reputation.
- **RIPE / WHOIS:** Verified IP ownership and allocation.

## Methodology
1. Preserved and inspected the raw email source.
2. Examined sender details, Message-ID, Return-Path, and Received headers.
3. Evaluated SPF, DKIM, and DMARC authentication results.
4. Investigated sending IP addresses and ownership.
5. Checked domain and mail server information.
6. Extracted embedded URLs and traced their redirect chains.
7. Compared technical evidence and email content to reach a conclusion.

## Case Studies

### Case Study 1: Legitimate RedCloud Recruitment Email
- SPF, DKIM, and DMARC authentication passed.
- Sending IP: `76.223.149.245`
- IP reputation showed a 0% abuse-confidence score on AbuseIPDB.
- Sender domains and embedded links were consistent with the recruitment notification.
- The profile link received 0/92 detections on VirusTotal.

**Conclusion:** The email was assessed as a legitimate recruitment notification sent through Teamtailor on behalf of RedCloud Technology.

### Case Study 2: Phishing Email Impersonating Amazon
- SPF failed, DKIM was unknown, and DMARC failed.
- The claimed Amazon sender identity was inconsistent with the Message-ID domain.
- Sending IP: `46.23.51.233`, associated with a residential ISP in Czechia.
- The URL redirect chain passed through `google.com.pe` and `lihi2.me` before reaching `login.servicenotificationes.com`.
- The final landing page was flagged as phishing by Fortinet through VirusTotal.
- The message used a generic greeting and urgent account-verification language.

**Conclusion:** The email was identified as a phishing attempt designed to impersonate Amazon and harvest account credentials.

## Key Findings
| Indicator | Legitimate Email | Phishing Email |
|---|---|---|
| SPF | Pass | Fail |
| DKIM | Pass | Unknown |
| DMARC | Pass | Fail |
| Sending IP | Reputable email infrastructure | Unrelated residential ISP |
| Sender consistency | Consistent domains | Domain mismatch |
| URL analysis | Expected destination | Suspicious redirect chain |
| Final assessment | Legitimate | Confirmed phishing |

## Key Takeaways
- Email authentication results provide valuable evidence but should be assessed alongside other indicators.
- IP ownership and reputation checks can help expose sender impersonation.
- A clean scan of an initial URL does not guarantee that its final destination is safe.
- Mismatches between From, Return-Path, and Message-ID domains can indicate suspicious activity.
- Urgency, generic greetings, and account-suspension threats can support a phishing assessment.

## Recommendations
- Enforce appropriate DMARC policies to reduce email spoofing.
- Verify unexpected account notifications through official websites or applications.
- Inspect complete URL redirect chains rather than trusting visible links.
- Investigate inconsistencies in email headers.
- Report confirmed malicious infrastructure to relevant abuse-reporting services.

## Skills Demonstrated
Email Forensics | Phishing Analysis | Email Header Analysis | SPF/DKIM/DMARC | IP Address Investigation | WHOIS Lookup | IP Reputation Analysis | URL Analysis | Redirect Chain Investigation | Threat Detection

## Project Conclusion
This investigation demonstrated how combining email authentication, header analysis, IP address investigation, domain checks, and URL tracing can distinguish legitimate communications from phishing attempts. The comparison highlighted the importance of evidence-based analysis when investigating suspicious emails.  
**Focus Area:** Email Security and Digital Forensics
