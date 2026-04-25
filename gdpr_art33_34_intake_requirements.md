# GDPR Art. 33 & 34 Intake Requirements
# Based on real supervisory authority reporting form (BayLDA)

## Purpose

This document defines the legally required data fields
for reporting personal data breaches under GDPR Articles 33 and 34.

This structure is based on:

- GDPR Article 33 (Authority Notification)
- GDPR Article 34 (Data Subject Notification)
- Real supervisory authority reporting form (Bavaria, Germany)

Used for:

- Incident Intake Form
- Risk Assessment Engine
- Notification Generator
- Audit Trail System

---

# SECTION 1 — Report Type

## report_type

Type: select  
Required: yes  

Values:

- initial_report
- follow_up_report

---

## initial_report_reference_id

Type: text  
Required: conditional  

Required if:

report_type = follow_up_report

---

# SECTION 2 — Responsible Organisation

## organisation_name

Type: text  
Required: yes  

---

## organisation_address

Type: object  
Required: yes  

Includes:

- street
- postal_code
- city

---

## organisation_website

Type: url  
Required: optional  

---

## kritis_operator

Type: boolean  
Required: optional  

Indicates KRITIS status.

---

# SECTION 3 — Reporting Person

## reporter_salutation

Type: select  
Required: yes  

Values:

- mr
- ms
- diverse
- none

---

## reporter_first_name

Type: text  
Required: yes  

---

## reporter_last_name

Type: text  
Required: yes  

---

## reporter_email

Type: email  
Required: yes  

---

## reporter_phone

Type: phone  
Required: yes  

---

## reporter_role

Type: select  
Required: yes  

Examples:

- DPO
- IT Security
- Legal
- Management
- Other

---

# SECTION 4 — Contact Person

## contact_is_reporter

Type: boolean  
Required: yes  

If TRUE:

→ reporter becomes contact

---

## contact_notification_method

Type: select  
Required: yes  

Values:

- email
- secure_email

---

## auto_confirmation_requested

Type: boolean  
Required: optional  

---

# SECTION 5 — Incident Timeline

## incident_time

Type: datetime  
Required: optional  

If known.

---

## detection_time

Type: datetime  
Required: yes  

Used for:

→ 72-hour deadline calculation

---

## delay_justification

Type: text  
Required: conditional  

Required if:

report submitted > 72 hours

---

# SECTION 6 — Incident Description

## breach_description

Type: text  
Required: yes  

Detailed description of incident.

---

## processor_involved

Type: boolean  
Required: yes  

Was a processor involved?

---

# SECTION 7 — Affected Scope

## affected_subject_count

Type: number  
Required: yes  

Approximate number of individuals affected.

---

## affected_record_count

Type: number  
Required: optional  

Approximate number of records.

---

# SECTION 8 — Data Categories

## data_categories

Type: multi-select  
Required: yes  

Values:

- health_data
- financial_data
- economic_data
- religious_data
- union_membership
- ethnic_origin
- sexuality
- political_opinion
- professional_secret
- biometric_data
- location_data
- photos_videos
- email_addresses
- postal_addresses
- passwords
- criminal_data
- birth_date
- id_number
- tax_number
- other_identifiers
- other_documents
- other_personal_data
- unknown

---

# SECTION 9 — Categories of Affected Persons

## subject_categories

Type: multi-select  
Required: yes  

Values:

- employees
- members
- users
- customers
- politicians
- patients
- children
- public_figures
- other

---

# SECTION 10 — Breach Effects (CIA Triad)

## breach_effect_types

Type: multi-select  
Required: yes  

Values:

- confidentiality_loss
- availability_loss
- integrity_loss

---

# SECTION 11 — Likely Consequences

## likely_consequences

Type: multi-select  
Required: yes  

Values:

- discrimination
- identity_theft
- life_threat
- financial_loss
- reputational_damage
- livelihood_loss
- embarrassment
- job_loss
- confidentiality_breach
- de_pseudonymization
- social_disadvantage
- economic_disadvantage
- other

---

# SECTION 12 — Risk Assessment

## risk_level

Type: select  
Required: yes  

Values:

- low
- medium
- high

Rules:

LOW → No notification required  
MEDIUM → Notify authority  
HIGH → Notify authority + subjects

---

## subjects_notified

Type: boolean  
Required: conditional  

Required if:

risk_level = high

---

# SECTION 13 — Mitigation Measures

## measures_taken

Type: text  
Required: yes  

Actions already performed.

Examples:

- system_isolated
- accounts_locked
- passwords_reset
- network_blocked

---

# SECTION 14 — Additional Authority Information

## external_authorities_notified

Type: text  
Required: optional  

Examples:

- police
- cybersecurity_agency
- regulator

---

# SECTION 15 — Attachments

## evidence_files

Type: file_upload  
Required: optional  

Accepted formats:

- PDF
- JPEG
- PNG
- ZIP

Examples:

- logs
- screenshots
- reports

---

# SECTION 16 — Follow-Up Reports

## follow_up_information

Type: text  
Required: conditional  

Required if:

report_type = follow_up_report

---

# SYSTEM OUTPUT REQUIREMENTS

The system must generate:

- authority_notification_required
- subject_notification_required
- reporting_deadline_timer
- risk_summary
- incident_report_document

---

# AUDIT TRAIL REQUIREMENTS

All incidents must be logged.

Required metadata:

- incident_id
- timestamps
- user_actions
- status_changes
- notification_history

---

# LEGAL NOTES

Notifications must be submitted:

→ Within 72 hours after detection  
→ Unless risk is negligible

All processing must be documented.
