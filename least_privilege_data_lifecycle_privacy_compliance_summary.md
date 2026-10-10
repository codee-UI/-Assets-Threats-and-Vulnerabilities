# Least Privilege, Data Lifecycle, Privacy, and Compliance — Concise Summary

## Objective

Understand four related security topics:

1. Principle of least privilege
2. Data lifecycle and governance
3. Information privacy vs. information security
4. Privacy regulations, audits, and assessments

---

# 1. Principle of Least Privilege

The **principle of least privilege (PoLP)** means granting only the minimum access and authorization required to complete a task.

It supports the CIA triad:

- Confidentiality
- Integrity
- Availability

## Why it matters

Least privilege reduces risk by:

- Limiting access to sensitive data
- Reducing accidental modification or loss
- Preventing misuse
- Supporting monitoring and administration

A useful rule is:

```text
Give only the access required,
for only as long as it is required.
```

## Separation of Duties

Least privilege is closely related to **separation of duties**, which divides critical responsibilities among multiple users so one person does not control an entire sensitive process.

## Common Account Types

| Account Type | Purpose |
|---|---|
| Guest account | Temporary/external access |
| User account | Standard staff access based on job duties |
| Service account | Used by applications or software |
| Privileged account | Elevated or administrative access |

## Privilege Creep

**Privilege creep** occurs when users accumulate permissions they no longer need.

Examples:

- Promotion
- Department transfer
- Temporary access not revoked

---

# Auditing Account Privileges

## Usage Audit

Reviews:

- Which resources accounts access
- What users do with those resources

Purpose:

- Confirm policy compliance
- Identify unused permissions

## Privilege Audit

Compares:

```text
User role
vs.
Current permissions
```

Purpose:

- Detect privilege creep
- Ensure access still matches job duties

## Account Change Audit

Reviews account changes such as:

- Password changes
- Permission changes
- Account creation or deletion

Purpose:

- Detect unauthorized changes
- Identify suspicious activity

---

# 2. Data Lifecycle

The **data lifecycle** describes how information moves through an organization.

The five stages are:

```text
Collect
  ↓
Store
  ↓
Use
  ↓
Archive
  ↓
Destroy
```

Data should be protected whether it is:

- At rest
- In use
- In transit

---

# Data Governance

**Data governance** is a set of processes defining how an organization manages information.

Governance policies typically address:

- Privacy
- Accuracy
- Availability
- Security

## Data Governance Roles

### Data Owner

Decides:

- Who can access data
- Who can edit it
- How it may be used
- When it may be destroyed

### Data Custodian

Responsible for safe:

- Handling
- Transport
- Storage

Security professionals often act as custodians.

### Data Steward

Maintains and implements data governance policies.

| Role | Main Responsibility |
|---|---|
| Data owner | Decides access and use |
| Data custodian | Safely handles, stores, and transports data |
| Data steward | Maintains governance policies |

---

# Legally Protected Information

## PII

**Personally Identifiable Information (PII)** can be used to identify, contact, or locate a person.

## PHI

**Protected Health Information (PHI)** relates to a person's health information.

In the U.S., PHI is regulated by HIPAA.

## SPII

**Sensitive Personally Identifiable Information (SPII)** is highly sensitive PII that requires stricter handling.

Examples:

- Bank account numbers
- Login credentials

---

# 3. Information Privacy vs. Information Security

## Information Privacy

Information privacy concerns protection from unauthorized access and distribution of personal data.

It focuses on:

- Who may collect data
- How data may be used
- Who may receive it
- Whether users have control

## Information Security

**Information security (InfoSec)** protects data in all states from unauthorized users.

### Key Difference

```text
Privacy = control over personal information
Security = protection of that information
```

Both support:

- Customer trust
- Brand reputation
- Legal compliance

---

# 4. Major Privacy Regulations and Standards

## GDPR

The **General Data Protection Regulation (GDPR)** protects personal information of EU citizens and residents.

It can apply to organizations outside the EU if they process EU personal data.

## PCI DSS

The **Payment Card Industry Data Security Standard (PCI DSS)** protects payment card data and transactions.

## HIPAA

The **Health Insurance Portability and Accountability Act (HIPAA)** protects sensitive health information in the United States.

| Regulation / Standard | Main Focus |
|---|---|
| GDPR | Personal data and privacy rights |
| PCI DSS | Payment card security |
| HIPAA | Health information |

---

# 5. Security Audits and Assessments

## Security Audit

A **security audit** reviews controls, policies, and procedures against expected requirements.

Examples:

- Checking whether MFA is enabled where required
- Reviewing compliance with regulations
- Verifying that controls are implemented

Audits may be internal or external and are generally performed less frequently.

## Security Assessment

A **security assessment** evaluates how resilient current controls are against threats.

Examples:

- Testing password strength
- Identifying security gaps
- Reviewing control effectiveness

Assessments are typically performed more frequently.

## Audit vs. Assessment

| Security Audit | Security Assessment |
|---|---|
| Compares against requirements | Evaluates resilience and effectiveness |
| Can validate compliance | Identifies weaknesses |
| Often annual | Often every 3–6 months |
| May be internal or external | Usually internal |

---

# Security Relevance

These concepts help security professionals:

- Restrict unnecessary access
- Prevent privilege creep
- Protect sensitive information
- Manage data through its lifecycle
- Protect PII, PHI, and SPII
- Support regulatory compliance
- Prepare for audits
- Perform security assessments
- Maintain the CIA triad

---

# Core Takeaways

## Least Privilege

```text
Minimum access
Minimum authorization
Only when needed
```

## Account Audits

```text
Usage audit
Privilege audit
Account change audit
```

## Data Lifecycle

```text
Collect
Store
Use
Archive
Destroy
```

## Governance Roles

```text
Owner
Custodian
Steward
```

## Protected Data

```text
PII
PHI
SPII
```

## Privacy vs. Security

```text
Privacy  → control over personal data
Security → protection of that data
```

## Major Regulations / Standards

```text
GDPR
PCI DSS
HIPAA
```

## Security Evaluation

```text
Security audit      → check against requirements
Security assessment → evaluate resilience
```

Overall:

```text
Identify Data
     ↓
Classify Sensitivity
     ↓
Limit Access
     ↓
Apply Least Privilege
     ↓
Protect Throughout Lifecycle
     ↓
Follow Privacy Requirements
     ↓
Audit and Assess
     ↓
Improve Controls
```
