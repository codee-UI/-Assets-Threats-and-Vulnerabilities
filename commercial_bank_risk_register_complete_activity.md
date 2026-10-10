# Risk Register — Commercial Bank Risk Assessment

## Activity Overview

This activity demonstrates how to perform a basic cybersecurity risk assessment for a commercial bank by evaluating common risks to one of its key assets: **funds**.

A **risk register** is a central record used to document potential risks to an organization's assets, systems, and data. It helps security teams compare risks and prioritize limited resources.

The risk calculation used in this activity is:

```text
Likelihood × Severity = Priority
```

Likelihood and severity are each scored from **1 to 3**, producing an overall priority score from **1 to 9**.

---

# Scenario

A commercial bank is conducting a risk assessment of its operational environment.

Important characteristics include:

- The bank is located in a **coastal area**.
- The surrounding area has **low crime rates**.
- The bank has **100 on-premise employees**.
- The bank has **20 remote employees**.
- It serves approximately **2,000 individual accounts**.
- It serves approximately **200 commercial accounts**.
- Its services are marketed by a **professional sports team** and **ten local businesses**.
- The bank operates under **strict financial regulations**.
- The bank must maintain enough funds each day to meet regulatory requirements.

The asset being evaluated is:

```text
Funds
```

---

# Risk Scoring Scale

## Likelihood

| Score | Meaning |
|---:|---|
| **1** | Low likelihood / rare |
| **2** | Moderate likelihood / likely |
| **3** | High likelihood / certain |

## Severity

| Score | Meaning |
|---:|---|
| **1** | Low impact |
| **2** | Moderate impact |
| **3** | High / catastrophic impact |

## Priority

Priority is calculated as:

```text
Likelihood × Severity
```

Example:

```text
2 × 3 = 6
```

---

# Risk Register

| Asset | Risk | Description | Likelihood | Severity | Priority |
|---|---|---|---:|---:|---:|
| Funds | Business email compromise | An employee is tricked into sharing confidential information. | **2** | **2** | **4** |
| Funds | Compromised user database | Customer data is poorly encrypted. | **2** | **3** | **6** |
| Funds | Financial records leak | A database server containing backed-up data is publicly accessible. | **3** | **3** | **9** |
| Funds | Theft | The bank's safe is left unlocked. | **1** | **3** | **3** |
| Funds | Supply chain disruption | Delivery delays occur because of natural disasters. | **1** | **2** | **2** |

---

# Notes on the Operating Environment

The bank's relationships with employees, remote workers, customers, and external business partners create several opportunities for sensitive information or funds to be exposed. Although physical theft could have a serious impact, its likelihood is lower because the bank operates in an area with low crime rates; however, digital risks and third-party exposure require stronger attention.

---

# Risk-by-Risk Evaluation

## 1. Business Email Compromise

### Description

```text
An employee is tricked into sharing confidential information.
```

### Likelihood: 2 — Moderate

The bank has many employees, including remote staff, which increases exposure to phishing and social-engineering attempts. Because business email compromise is a common attack method, a moderate likelihood is reasonable.

### Severity: 2 — Moderate

Successful compromise could expose confidential information, cause fraudulent transactions, or create operational disruption. The impact could be significant, but it may be limited compared with a large-scale customer database or financial-records breach.

### Priority

```text
2 × 2 = 4
```

**Priority score: 4**

---

## 2. Compromised User Database

### Description

```text
Customer data is poorly encrypted.
```

### Likelihood: 2 — Moderate

Weak encryption increases the chance that customer information could be exposed if an attacker gains access to the database. The bank's large customer base makes this an important concern.

### Severity: 3 — High

A compromised database could expose information associated with thousands of customer and commercial accounts. This could lead to regulatory penalties, financial loss, identity-related harm, and serious reputational damage.

### Priority

```text
2 × 3 = 6
```

**Priority score: 6**

---

## 3. Financial Records Leak

### Description

```text
A database server containing backed-up financial data is publicly accessible.
```

### Likelihood: 3 — High

A publicly accessible database server creates direct exposure. Because access is already overly permissive, exploitation is highly plausible.

### Severity: 3 — High

Financial records are highly sensitive. A leak could cause regulatory violations, financial losses, customer distrust, and major reputational damage.

### Priority

```text
3 × 3 = 9
```

**Priority score: 9**

This is the **highest-priority risk** in the register.

---

## 4. Theft

### Description

```text
The bank's safe is left unlocked.
```

### Likelihood: 1 — Low

The vulnerability is serious, but the bank is located in an area with low crime rates. Based on the operating environment, physical theft is less likely than the digital risks.

### Severity: 3 — High

If theft occurs, funds could be directly lost and the bank may fail to meet operational or regulatory requirements.

### Priority

```text
1 × 3 = 3
```

**Priority score: 3**

---

## 5. Supply Chain Disruption

### Description

```text
Delivery delays caused by natural disasters.
```

### Likelihood: 1 — Low

The bank is located in a coastal area, so natural disasters may disrupt deliveries. However, such events are expected to occur less frequently than everyday cyber threats.

### Severity: 2 — Moderate

A disruption could affect cash availability or other operational requirements. The impact may be meaningful but is less severe than a major financial-records or customer-data breach.

### Priority

```text
1 × 2 = 2
```

**Priority score: 2**

---

# Priority Ranking

| Rank | Risk | Priority Score | Priority Level |
|---:|---|---:|---|
| **1** | Financial records leak | **9** | Critical |
| **2** | Compromised user database | **6** | High |
| **3** | Business email compromise | **4** | Moderate |
| **4** | Theft | **3** | Moderate-Low |
| **5** | Supply chain disruption | **2** | Low |

---

# Recommended Security Priorities

Based on the calculated scores, the bank should focus first on the highest-risk issues.

## Priority 1 — Secure Financial Records

Recommended actions:

- Remove public database access.
- Restrict access using least privilege.
- Review firewall and network access controls.
- Enable strong authentication.
- Monitor database access.
- Encrypt sensitive data.
- Audit backup configurations.

## Priority 2 — Protect the User Database

Recommended actions:

- Strengthen encryption.
- Review key-management practices.
- Restrict database permissions.
- Patch and harden database systems.
- Monitor for unauthorized access.
- Conduct periodic access reviews.

## Priority 3 — Reduce Business Email Compromise

Recommended actions:

- Provide phishing-awareness training.
- Use multi-factor authentication.
- Configure email security controls.
- Monitor suspicious sign-in behavior.
- Establish procedures for verifying sensitive requests.

## Priority 4 — Improve Physical Security

Recommended actions:

- Keep the safe locked.
- Limit access to authorized employees.
- Maintain physical access logs.
- Use cameras and alarms where appropriate.

## Priority 5 — Prepare for Supply Chain Disruption

Recommended actions:

- Maintain contingency plans.
- Establish alternate suppliers.
- Define emergency cash and service procedures.
- Review business continuity plans.

---

# Risk Matrix

| Likelihood \ Severity | Low (1) | Moderate (2) | High (3) |
|---|---:|---:|---:|
| **High / Certain (3)** | 3 | 6 | **9** |
| **Moderate / Likely (2)** | 2 | **4** | **6** |
| **Low / Rare (1)** | 1 | **2** | **3** |

---

# NIST CSF Relevance

This activity supports the **Identify** function of the NIST Cybersecurity Framework because the organization is:

- identifying important assets,
- identifying risks,
- evaluating vulnerabilities,
- estimating likelihood and impact, and
- prioritizing remediation activities.

The results can then guide the **Protect**, **Detect**, **Respond**, and **Recover** functions.

---

# Final Deliverable Checklist

- [x] 2–3 sentences describing operating-environment risk factors
- [x] 5 likelihood scores
- [x] 5 severity scores
- [x] 5 overall priority scores
- [x] Risk calculations
- [x] Priority ranking
- [x] Security recommendations

---

# Core Takeaway

Risk assessment helps an organization decide where security resources should be focused.

The basic process is:

```text
Identify Asset
     ↓
Identify Risk
     ↓
Estimate Likelihood
     ↓
Estimate Severity
     ↓
Calculate Priority
     ↓
Rank Risks
     ↓
Apply Security Controls
```

For this assessment, the highest-priority issue is the **financial records leak**, with a score of:

```text
3 × 3 = 9
```

It should therefore receive the most urgent attention.
