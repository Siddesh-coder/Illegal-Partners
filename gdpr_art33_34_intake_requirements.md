# GDPR Articles 33 & 34 — Legal Notification Requirements

## Purpose

This document defines the mandatory information that must be collected
under GDPR Articles 33 and 34 in case of a personal data breach.

This file contains ONLY legally required data elements.

It serves as the legal foundation for:

- Incident intake
- Risk evaluation
- Notification preparation
- Documentation compliance

Based on:

- GDPR Article 33 — Notification to Supervisory Authority
- GDPR Article 34 — Notification to Data Subjects

---

# SECTION 1 — Awareness Timing (Art. 33(1))

## detection_time

Type: datetime  
Required: yes  

Description:

Timestamp when the controller became aware of the personal data breach.

Legal basis:

Art. 33(1) — notification within 72 hours.

---

## delay_justification

Type: text  
Required: conditional  

Description:

Reason for delay if notification occurs later than 72 hours.

Legal basis:

Art. 33(1) — justification required if deadline exceeded.

---

# SECTION 2 — Nature of the Breach (Art. 33(3)(a))

## breach_description

Type: text  
Required: yes  

Description:

Description of the nature of the personal data breach.

Legal basis:

Art. 33(3)(a)

---

## data_categories

Type: multi-select  
Required: yes  

Description:

Categories of personal data affected.

Legal basis:

Art. 33(3)(a)

---

## subject_categories

Type: multi-select  
Required: optional  

Description:

Categories of affected individuals.

Legal basis:

Art. 33(3)(a)

---

## affected_subject_count

Type: number  
Required: yes  

Description:

Approximate number of affected data subjects.

Legal basis:

Art. 33(3)(a)

---

## affected_record_count

Type: number  
Required: optional  

Description:

Approximate number of affected personal data records.

Legal basis:

Art. 33(3)(a)

---

# SECTION 3 — Contact Information (Art. 33(3)(b))

## contact_person_name

Type: text  
Required: yes  

Description:

Name of the Data Protection Officer or other contact point.

Legal basis:

Art. 33(3)(b)

---

## contact_person_email

Type: email  
Required: yes  

Description:

Email address of contact person.

Legal basis:

Art. 33(3)(b)

---

## contact_person_phone

Type: phone  
Required: optional  

Description:

Phone number of contact person.

Legal basis:

Art. 33(3)(b)

---

# SECTION 4 — Likely Consequences (Art. 33(3)(c))

## likely_consequences

Type: text  
Required: yes  

Description:

Description of likely consequences of the breach.

Legal basis:

Art. 33(3)(c)

---

# SECTION 5 — Measures Taken (Art. 33(3)(d))

## measures_taken

Type: text  
Required: yes  

Description:

Measures already taken to address the breach.

Legal basis:

Art. 33(3)(d)

---

## mitigation_measures

Type: text  
Required: optional  

Description:

Measures taken to mitigate possible adverse effects.

Legal basis:

Art. 33(3)(d)

---

# SECTION 6 — Risk Assessment (Art. 33(1), Art. 34)

## risk_level

Type: select  
Required: yes  

Values:

- no_risk
- risk
- high_risk

Description:

Assessment whether the breach poses a risk to the rights and freedoms of natural persons.

Legal basis:

Art. 33(1)  
Art. 34(1)

---

# SECTION 7 — Data Subject Notification (Art. 34)

## subjects_notified

Type: boolean  
Required: conditional  

Description:

Indicates whether affected individuals have been informed.

Required if:

risk_level = high_risk

Legal basis:

Art. 34(1)

---

# SECTION 8 — Breach Documentation (Art. 33(5))

## incident_documentation

Type: text  
Required: yes  

Description:

Documentation of:

- facts relating to the breach
- its effects
- remedial actions taken

Legal basis:

Art. 33(5)

Purpose:

Allows supervisory authority to verify compliance.

---

# LEGAL SUMMARY

Under GDPR:

A personal data breach must be reported to the supervisory authority
within 72 hours unless the breach is unlikely to result in risk.

If a high risk exists, affected individuals must also be notified.

All breaches must be documented regardless of notification obligation.
