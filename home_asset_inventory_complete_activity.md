# Home Asset Inventory — Complete Activity

## Activity Overview

In this activity, a home-office network is reviewed from an asset-management perspective.

**Asset management** is the process of tracking assets and the risks that affect them. A key part of asset management is creating an **asset inventory**, which is a catalog of assets that should be protected.

After identifying assets, they are classified according to their importance and sensitivity so that appropriate security controls can be applied.

---

## Scenario

A small business is operated from a home office. Several devices connect to the home network, and each connected device can potentially become an entry point to other systems or information.

The goal is to:

1. Identify devices connected to the home network.
2. Record important characteristics of each device.
3. Review how each device accesses the network.
4. Consider the type of information stored or processed.
5. Assign an appropriate sensitivity classification.

---

## Activity Objective

Create a home-network asset inventory that includes:

- At least three additional network-connected devices
- Network access information
- Asset owner
- Physical location
- Security-relevant notes
- Sensitivity classification

---

# Asset Classification Levels

The activity uses four common sensitivity levels.

| Classification | Meaning |
|---|---|
| **Restricted** | Highest sensitivity; access should be limited to those with a strict need to know |
| **Confidential** | Disclosure could cause significant negative impact |
| **Internal-only** | Intended for authorized internal users, employees, or approved partners |
| **Public** | Disclosure would cause little or no negative impact |

---

# Existing Example Assets

The template already contained example assets such as:

- Network router
- Desktop computer
- Guest smartphone

These examples help demonstrate how assets can be documented according to access, ownership, location, notes, and sensitivity.

---

# Additional Assets Identified

Three additional devices were added to the inventory:

1. Laptop computer
2. Wireless printer
3. Smart TV

---

# Completed Asset Inventory

| Asset | Network Access | Owner | Location | Notes | Sensitivity |
|---|---|---|---|---|---|
| **Laptop computer** | Frequently connected to the home Wi-Fi network | Business owner | Home office, near the router | Stores business documents, account information, and other sensitive files. Used regularly for business activity and should be strongly protected. | **Restricted** |
| **Wireless printer** | Connected to the home network when powered on | Business owner | Home office | Receives business documents over the network and may temporarily store print jobs or scanned information. Unauthorized access could expose confidential material. | **Confidential** |
| **Smart TV** | Frequently connected to Wi-Fi for streaming and software updates | Household / business owner | Living area, farther from the router | Primarily used for media services. It has network access but normally does not store highly sensitive business information. | **Internal-only** |

---

# Step 1 — Access the Asset Inventory Template

The provided home asset inventory spreadsheet was used as the working template.

The template provides columns for:

- Asset
- Network access
- Owner
- Location
- Notes
- Sensitivity

A blank copy of the template can be retained for future exercises or professional use.

---

# Step 2 — Identify Assets

Three devices not already included in the template were selected.

### Selected devices

```text
Laptop computer
Wireless printer
Smart TV
```

The devices were chosen because each can connect to the home network and therefore represents a potential point of exposure.

---

# Step 3 — Record Asset Characteristics

For each device, the following characteristics were considered:

## Network Access

Describes how often and how the device connects to the network.

Examples:

```text
Frequently connected
Connected when powered on
Always connected
Occasionally connected
```

## Owner

Identifies the person or entity responsible for the asset.

Examples:

```text
Business owner
Household member
Guest
Organization
```

## Location

Describes the physical location of the asset relative to the network and router.

Examples:

```text
Home office
Living room
Near router
Farther from router
```

---

# Step 4 — Evaluate Network Access and Security Characteristics

Each device was reviewed by asking:

- What information is stored on the device?
- How does it connect to the network?
- Does it process or transmit sensitive information?
- Could unauthorized access affect the business?
- Is the device regularly maintained or updated?
- Could the device provide a pathway to other network assets?

---

## Laptop Computer Assessment

The laptop is one of the most important assets because it is used for business activity.

Possible information stored includes:

- Business documents
- Account information
- Customer information
- Email
- Authentication data
- Financial records

Because compromise could expose or alter sensitive business information, it requires a high level of protection.

### Classification

```text
Restricted
```

---

## Wireless Printer Assessment

The printer is connected to the network and may process:

- Business documents
- Scanned records
- Confidential print jobs
- Temporary print data

Although it may not permanently store large amounts of data, unauthorized access could still disclose business information.

### Classification

```text
Confidential
```

---

## Smart TV Assessment

The smart TV connects to the home Wi-Fi network for:

- Streaming
- Software updates
- Online services

It normally does not store highly sensitive business information, but because it is connected to the same network, it should still be managed and secured.

### Classification

```text
Internal-only
```

---

# Step 5 — Classify Asset Sensitivity

The final classifications were assigned according to the potential impact if each asset were compromised.

| Asset | Main Security Concern | Classification |
|---|---|---|
| Laptop computer | Exposure, modification, or loss of sensitive business data | **Restricted** |
| Wireless printer | Disclosure of confidential printed or scanned information | **Confidential** |
| Smart TV | Network exposure with limited business information | **Internal-only** |

---

# Confidentiality, Integrity, and Availability Considerations

The sensitivity of each asset can also be evaluated using the CIA triad.

## Confidentiality

Could unauthorized users access sensitive information?

Examples:

- Laptop business files
- Printer documents
- Stored credentials

## Integrity

Could an attacker modify information or device settings?

Examples:

- Alter business documents
- Change printer configuration
- Modify device settings

## Availability

Could compromise prevent the business from using the asset?

Examples:

- Laptop malware or ransomware
- Printer unavailable during business operations
- Network-connected devices affecting network performance

---

# Risk Perspective

A useful relationship is:

```text
Threat + Vulnerability → Increased likelihood of harm → Risk
```

For example:

```text
Asset: Laptop
Threat: Unauthorized attacker
Vulnerability: Weak password or unpatched software
Impact: Business data stolen or modified
Risk: Loss of confidentiality and integrity
```

---

# Security Recommendations

Based on the inventory, practical controls include:

### Laptop Computer

- Use strong passwords
- Enable multi-factor authentication where possible
- Use full-disk encryption
- Keep the operating system and applications updated
- Maintain regular backups
- Use antivirus/endpoint protection
- Lock the device when unattended

### Wireless Printer

- Change default administrator credentials
- Keep firmware updated
- Disable unnecessary services
- Restrict management access
- Use secure Wi-Fi
- Clear stored jobs if supported

### Smart TV

- Keep firmware updated
- Use strong Wi-Fi security
- Disable unused features
- Avoid installing unnecessary applications
- Consider placing IoT devices on a separate network or guest VLAN where possible

---

# Why Asset Inventory Matters

Maintaining an asset inventory helps a business:

- Know which devices require protection
- Identify sensitive assets
- Prioritize security controls
- Track ownership
- Identify unmanaged or unknown devices
- Improve incident response
- Support risk assessment
- Reduce unnecessary exposure

A useful principle is:

```text
You cannot protect what you do not know you have.
```

---

# Final Deliverable

The completed inventory includes:

- [x] Three additional home-network devices
- [x] Network access information
- [x] Owner information
- [x] Location information
- [x] Security-relevant notes
- [x] Sensitivity classification
- [x] Risk-based reasoning

---

# Key Takeaways

Asset inventory is the foundation of effective asset management.

The process can be summarized as:

```text
Identify Assets
      ↓
Record Characteristics
      ↓
Evaluate Network Access
      ↓
Assess Security Impact
      ↓
Classify Sensitivity
      ↓
Apply Appropriate Controls
```

For this activity:

```text
Laptop computer  → Restricted
Wireless printer → Confidential
Smart TV         → Internal-only
```

The classification reflects the potential impact to confidentiality, integrity, and availability if each asset were compromised.
