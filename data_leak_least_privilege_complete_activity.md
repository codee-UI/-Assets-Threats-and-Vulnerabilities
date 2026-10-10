# Data Leak Worksheet — Least Privilege Analysis

## Activity Overview

This activity analyzes a data leak at an educational technology company and evaluates how the **principle of least privilege** could have reduced the risk.

The analysis is based on:

- The incident summary
- The company's security plan snapshot
- NIST SP 800-53: AC-6 (Least Privilege)
- Recommended control enhancements

The goal is to identify what caused the leak, determine how least privilege applies, recommend improvements, and explain why those improvements reduce future risk.

---

# Scenario

An educational technology company developed an application that helps teachers automatically grade assignments.

The application handles data collected from:

- Academic institutions
- Instructors
- Parents
- Students

The company experienced a leak of confidential internal business information after an employee accidentally shared a folder of internal documents with an external business partner.

The incident exposed weaknesses in how the organization applied the **principle of least privilege**.

---

# Incident Summary

A manager shared access to a folder containing internal-only documents with members of the sales team.

The folder included:

- Information about an unreleased product
- Customer analytics
- Promotional materials

After the meeting, the manager did not revoke access to the folder.

Later, a sales representative intended to share only the promotional materials with a business partner but accidentally shared the entire internal folder.

The business partner then posted the link to social media, exposing confidential company information.

---

# Control Being Evaluated

```text
Least Privilege
```

The **principle of least privilege** means that users should receive only the minimum access and authorization needed to perform their job duties.

---

# Issue(s)

Access to the internal folder remained broader than necessary after the sales meeting, and the manager did not revoke permissions when the temporary need for access ended. The sales representative was also able to share the entire internal folder externally, which allowed confidential information to reach a business partner and later social media.

---

# Security Plan Snapshot

The company's security plan connects the data-leak issue to the NIST Cybersecurity Framework.

The relevant path is:

```text
Function:
Protect

Category:
PR.DS — Data Security

Subcategory:
PR.DS-5 — Protections against data leaks

Reference:
NIST SP 800-53: AC-6
```

This means the company uses **NIST SP 800-53 AC-6** as guidance for implementing controls that help prevent unauthorized disclosure of information.

---

# Review — NIST SP 800-53: AC-6

NIST SP 800-53: AC-6 addresses the **principle of least privilege** by requiring users, processes, and roles to receive only the minimum access and authorization necessary to perform required business functions. It also provides control enhancements that organizations can use to strengthen least privilege and reduce unnecessary exposure of sensitive information.

---

# AC-6 Control

The core idea of AC-6 is:

```text
Only the minimum access and authorization required
to complete a task or function should be provided.
```

The goal is to prevent users from operating with privileges beyond what is necessary for business objectives.

---

# AC-6 Control Enhancements

The worksheet identifies the following potential improvements:

- Restrict access to sensitive resources based on user role
- Automatically revoke access after a defined period
- Keep activity logs for provisioned accounts
- Regularly audit user privileges

---

# Recommendation(s)

## 1. Restrict Access Based on User Role

Access to confidential folders should be limited according to job responsibilities and business need. External business partners should not receive access to internal folders, and sales representatives should only be able to access or share the specific materials required for their role.

## 2. Regularly Audit User Privileges

Managers and security teams should regularly review access permissions to internal folders and remove unnecessary privileges. Regular audits would help identify access that is no longer required and reduce the risk of sensitive information being shared accidentally.

---

# Justification

Role-based restrictions would reduce the chance that employees could expose confidential information beyond what their job requires. Regular privilege audits would also help detect and remove unnecessary access before it can be misused, limiting the likelihood of another accidental data leak.

---

# Alternative Strong Control Enhancement

Another effective control would be:

```text
Automatically revoke access to information after a period of time.
```

This would directly address the manager's failure to remove access after the sales meeting.

For example:

```text
Temporary folder access granted for meeting
        ↓
Access expires automatically after meeting
        ↓
Employee cannot later share the entire internal folder
```

This reduces reliance on human memory and manual permission cleanup.

---

# Root Cause Analysis

The incident resulted from multiple control failures.

| Factor | Security Problem |
|---|---|
| Manager did not revoke access | Excess privileges remained active |
| Sales representative retained unnecessary access | Least privilege was not enforced |
| Entire folder could be externally shared | Sensitive resources lacked sufficient sharing restrictions |
| No timely access review | Excess permissions were not detected |
| Business partner posted the link publicly | Confidential information escaped organizational control |

---

# Data Leak Sequence

```text
Manager shares internal folder
        ↓
Sales team receives broad access
        ↓
Access is not revoked
        ↓
Sales representative shares wrong link
        ↓
Business partner receives internal folder
        ↓
Partner posts link on social media
        ↓
Confidential data leak
```

---

# How Least Privilege Could Have Prevented the Incident

A stronger least-privilege implementation could have limited the incident at several stages.

## Before the Meeting

Only employees who required access should have been granted permissions.

## After the Meeting

Temporary access should have been removed or automatically expired.

## During External Sharing

The sales representative should only have been able to share approved promotional materials, not the complete internal folder.

## Through Ongoing Monitoring

Privilege audits and activity logs could have revealed that unnecessary access remained active.

---

# Recommended Control Improvements Summary

| Recommendation | Risk Reduction |
|---|---|
| Restrict access by user role | Limits exposure of sensitive resources |
| Regularly audit privileges | Detects unnecessary or excessive access |
| Automatically revoke temporary access | Prevents stale permissions |
| Maintain account activity logs | Supports monitoring and investigation |

---

# CIA Triad Impact

The incident primarily affected **confidentiality**, because internal-only information was disclosed to unauthorized parties.

It could also affect:

- **Integrity** if exposed documents were modified or misrepresented
- **Availability** if the leak disrupted business operations or forced systems or materials to be withdrawn

---

# Privacy and Security Relevance

This activity demonstrates how access control directly supports information privacy.

A practical principle is:

```text
Access should be:
Necessary
Limited
Temporary when appropriate
Monitored
Reviewed regularly
```

When access is broader or longer-lasting than required, the risk of accidental or unauthorized disclosure increases.

---

# NIST CSF Relationship

The activity connects to the **Protect** function of the NIST Cybersecurity Framework.

```text
Protect
   ↓
Data Security
   ↓
Protection Against Data Leaks
   ↓
Least Privilege
   ↓
NIST SP 800-53 AC-6
```

---

# Final Worksheet Answers

## Issue(s)

Access to the internal folder remained broader than necessary after the sales meeting, and the manager did not revoke permissions when the temporary need for access ended. The sales representative was also able to share the entire internal folder externally, which allowed confidential information to reach a business partner and later social media.

## Review

NIST SP 800-53: AC-6 addresses the principle of least privilege by requiring users, processes, and roles to receive only the minimum access and authorization necessary to perform required business functions. It also provides control enhancements that organizations can use to strengthen least privilege and reduce unnecessary exposure of sensitive information.

## Recommendation(s)

- Restrict access to sensitive resources based on user role.
- Regularly audit user privileges.

## Justification

Role-based restrictions would reduce the chance that employees could expose confidential information beyond what their job requires. Regular privilege audits would also help detect and remove unnecessary access before it can be misused, limiting the likelihood of another accidental data leak.

---

# Activity Completion Checklist

- [x] 2–3 sentences analyzing factors that caused the incident
- [x] 2–3 sentences summarizing NIST SP 800-53: AC-6
- [x] Two least-privilege control enhancements
- [x] 2–3 sentences justifying the recommendations
- [x] Root-cause analysis
- [x] NIST CSF mapping
- [x] CIA-triad relevance

---

# Core Takeaway

The main lesson from this incident is:

```text
Too much access
      +
Access retained too long
      +
Weak sharing restrictions
      =
Higher risk of data leakage
```

A stronger approach is:

```text
Restrict Access
      ↓
Time-Limit Access
      ↓
Audit Privileges
      ↓
Monitor Activity
      ↓
Reduce Data Exposure
```

The principle of least privilege is most effective when access is continuously limited, reviewed, and revoked when it is no longer required.
