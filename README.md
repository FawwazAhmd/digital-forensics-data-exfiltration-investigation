# Digital Forensics & Data Exfiltration Investigation

A practical **digital forensics investigation** conducted using **Autopsy 4.20** to determine how sensitive employee information was created, transmitted outside an organisation, and subsequently exposed.

The investigation involved forensic analysis of a disk image from an employee workstation, including **filesystem metadata, Outlook PST archives, email communications, email attachments, and incident timelines**.

---

## Investigation Overview

The investigation focused on a suspected data breach within the fictional organisation **M57.biz**.

The primary objectives were to determine:

1. When the confidential employee data was created.
2. How the data was exfiltrated from the employee's computer.
3. How the information was transmitted outside the organisation.
4. Whether other individuals within the organisation were involved.
5. How the exposed information was subsequently identified online.

The investigation ultimately established a chain of evidence linking the creation of a confidential spreadsheet, an urgent email request, transmission of the spreadsheet to an external email address, and subsequent public exposure of employee information.

---

## Tools & Technologies

- **Autopsy 4.20**
- Windows Digital Forensics
- Filesystem Metadata Analysis
- Outlook PST Analysis
- Email Forensics
- Email Attachment Analysis
- Keyword Searching
- Timeline Reconstruction
- Evidence Correlation

---

## Evidence Examined

The investigation was conducted using a forensic disk image from the employee workstation.

### Primary Evidence Sources

- Windows filesystem artifacts
- File metadata
- Microsoft Outlook PST archive
- Email communications
- Email attachments
- Spreadsheet files
- Email headers
- User activity artifacts

The forensic image was analyzed within a restricted virtual environment to maintain evidence integrity.

---

## Autopsy Analysis

Several Autopsy ingest modules were used during the investigation:

| Module | Purpose |
|---|---|
| Recent Activity | Identified recently accessed files and user activity |
| File Type Identification | Located relevant document and spreadsheet files |
| Email Parser | Extracted Outlook emails and attachments |
| Embedded File Extractor | Recovered files embedded within attachments |
| Keyword Search | Performed targeted searches across evidence |
| Interesting Files Identifier | Flagged potentially significant artifacts |
| Extension Mismatch Detector | Identified files with inconsistent extensions |

---

## Key Findings

### 1. Creation of Confidential Spreadsheet

Filesystem metadata identified a spreadsheet named:

`m57biz.xls`

The file contained sensitive employee information, including:

- Employee names
- Salaries
- Social Security Numbers

Metadata analysis established that the spreadsheet was created on **20 July 2008 at 01:28:03 UTC** on the investigated workstation.

This indicated that the confidential information was created on the workstation rather than simply downloaded from an external source.

---

### 2. Suspicious Email Request

Analysis of the Outlook PST archive identified an urgent email requesting confidential employee information.

The request included sensitive information such as:

- Employee names
- Salaries
- Social Security Numbers

The urgency of the request played an important role in the subsequent data disclosure.

---

### 3. Transmission of Confidential Data

Further email analysis identified a response from the employee confirming that the requested information had been attached.

The attachment corresponded to the previously identified:

`m57biz.xls`

This provided evidence connecting the confidential spreadsheet to the email transmission.

---

### 4. External Data Transmission

Email header analysis established that the information was transmitted to a **non-corporate email address**.

This demonstrated that confidential organisational information had been transferred outside the organisation's normal communication environment.

---

### 5. Public Exposure

Subsequent internal communications reported that employees had discovered their personal information online.

Further correspondence confirmed that the leaked information, including Social Security Numbers and salary information, was accurate.

This provided evidence that the transmitted data had subsequently been publicly exposed.

---

## Incident Timeline

The evidence was correlated to reconstruct the sequence of events.

| Time | Event |
|---|---|
| 20 July 2008 – 01:28 | Confidential spreadsheet identified as being created on the workstation |
| 20 July 2008 – 02:23 | Urgent request for employee information received |
| 20 July 2008 – 23:57 | Internal communication reported suspicious activity |
| 20 July 2008 – 23:58 | Employee data reported as appearing online |
| 21 July 2008 – 00:40 | Employee responded regarding knowledge of the leak |
| 21 July 2008 – 00:45 | Employee contacted the webmaster regarding the incident |
| 21 July 2008 – 00:46 | Follow-up communication regarding sensitive data |
| 21 July 2008 – 01:17 | Outlook PST activity observed during the investigation |

---

## Investigation Conclusion

The evidence indicated that the incident was primarily associated with a **social engineering attack exploiting urgency and trust**.

The investigation established the following chain:

```text
Urgent Information Request
          ↓
Sensitive Employee Data Requested
          ↓
Confidential Spreadsheet Identified
          ↓
Spreadsheet Attached to Email
          ↓
Data Sent to External Email Address
          ↓
Employee Information Appeared Online
          ↓
Data Breach Confirmed
````

Evidence suggested that the internal email account involved in the request may have been **compromised or impersonated**. The investigation did not identify evidence of intentional malicious activity by the internal employees involved.

---

## Evidence Correlation

The investigation relied on correlating multiple artifacts rather than relying on a single source of evidence.

    Filesystem Metadata
            │
            ├── File creation time
            ├── File location
            └── File metadata
                    │
                    ↓
            Confidential Spreadsheet
                    │
                    ↓
            Outlook PST Archive
                    │
            ├── Request Email
            ├── Response Email
            ├── Attachment
            └── Email Headers
                    │
                    ↓
            External Transmission
                    │
                    ↓
            Public Data Exposure

This correlation helped establish the relationship between the original file, the email communication, external transmission, and subsequent data exposure.

---

## Digital Forensics Skills Demonstrated

This investigation provided practical experience with:

- Digital evidence examination
- Filesystem artifact analysis
- File metadata analysis
- Email forensics
- Outlook PST investigation
- Email header analysis
- Attachment analysis
- Evidence correlation
- Incident timeline reconstruction
- Data exfiltration investigation
- Social engineering analysis
- Incident reporting
- Evidence-based reasoning

---

## Recommendations

Based on the investigation, the following security controls were identified as important:

- Implement strict policies for handling and transferring sensitive information.
- Restrict transmission of confidential data to approved communication channels.
- Provide employees with regular **social engineering and phishing awareness training**.
- Require verification of urgent or unusual requests for sensitive information.
- Implement **Data Loss Prevention (DLP)** controls to monitor and prevent unauthorized data transfers.
- Use appropriate access controls and authentication protections for organisational email accounts.

---

## Investigation Limitations

The investigation was limited to the available evidence from a single workstation.

The following limitations applied:

- No server-side logs were available for correlation.
- No network captures were available.
- External systems could not be directly examined.
- The identity of the external recipient could not be conclusively validated.
- Deleted or encrypted data outside the recovered artifacts could not be examined.

These limitations were considered when evaluating the certainty of the findings.

---

## Disclaimer

This repository contains a **sanitized technical summary** of an academic digital forensics investigation.

The original forensic disk image, raw Outlook PST data, extracted personal information, and other sensitive forensic artifacts are **not included** in this repository.

No real-world personal data or confidential evidence should be published as part of this project.

---

## Project Context

**Module:** Digital Forensics  
**Assessment:** Continuous Assessment 1 (CA1)  
**Forensic Tool:** Autopsy 4.20

This project was completed as part of postgraduate cybersecurity coursework and demonstrates the application of digital forensic techniques to a simulated organisational data-breach investigation.
