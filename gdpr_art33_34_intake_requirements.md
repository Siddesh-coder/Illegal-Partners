# GDPR Art. 33 & 34 Breach Notification Requirements

## Purpose

This file defines the mandatory legal requirements for GDPR breach notifications.

It serves as the legal foundation for:

- Incident Intake Form
- Risk Assessment Engine
- Notification Generation
- Audit Trail Documentation

Based on:

- GDPR Article 33 (Notification to Supervisory Authority)
- GDPR Article 34 (Notification to Data Subjects)

---

# Article 33 — Supervisory Authority Notification

## Mandatory Information (Legal Requirement)

The following information MUST be collected.

These fields are required by law.

### Breach Description

Field ID: breach_description  
Type: text  
Required: yes  

Description of the nature of the personal data breach.

---

### Data Categories

Field ID: data_categories  
Type: multi-select  
Required: yes  

Examples:

- Names
- Email addresses
- Financial data
- Health data
- Login credentials
- Other personal data

---

### Number of Affected Data Subjects

Field ID: affected_subject_count  
Type: number or range  
Required: yes  

Approximate number of individuals affected.

---

### Number of Affected Data Records

Field ID: affected_record_count  
Type: number or range  
Required: yes  

Approximate number of records affected.

---

### Contact Details

Field ID: contact_point  
Type: object  
Required: yes  

Includes:

- Name of Data Protection Officer (DPO)
- Email
- Phone number

---

### Likely Consequences

Field ID: likely_consequences  
Type: text  
Required: yes  

Examples:

- Identity theft risk
- Financial loss
- Reputational damage

---

### Measures Taken

Field ID: measures_taken  
Type: text  
Required: yes  

Actions already performed.

Examples:

- System isolated
- Password reset
- Access revoked

---

### Planned Measures

Field ID: measures_planned  
Type: text  
Required: yes  

Future actions to mitigate risks.

Examples:

- Forensic investigation
- Security patching
- User notification

---

# Additional Legal Constraints

## 72-Hour Deadline

Field ID: breach_detection_time  
Type: datetime  
Required: yes  

Used to calculate:

- Reporting deadline

If notification is late:

Field ID: delay_justification  
Required: conditional

---

## Audit Trail Requirement

All incidents MUST be documented.

Required metadata:

- Incident ID
- Timestamp history
- User actions
- Status changes

---

# Article 34 — Notification to Data Subjects

## High Risk Decision

This determines whether affected individuals must be notified.

Field ID: high_risk_flag  
Type: boolean  
Required: yes  

Trigger condition:

If HIGH RISK = TRUE  
→ Notify data subjects

---

## Required Content for Data Subject Notification

If high risk exists:

The following information must be included:

- Breach description
- Contact point
- Likely consequences
- Remedial measures

Language requirement:

Must be:

- clear
- simple
- understandable

---

# Risk Assessment Inputs (Decision Engine)

These fields support the high-risk evaluation.

Not directly required by law, but required for automation.

Field IDs:

- data_sensitivity_level
- encryption_status
- unauthorized_access_confirmed
- potential_identity_theft
- financial_damage_possible

---

# Output Decisions

The system must support the following outputs:

- NO_NOTIFICATION_REQUIRED
- NOTIFY_AUTHORITY
- NOTIFY_AUTHORITY_AND_SUBJECTS

---

# Notes for Developers

This file defines:

- Required intake fields
- Legal logic dependencies
- Notification triggers

Do NOT remove mandatory fields.

These fields are legally required under GDPR Articles 33 and 34.
