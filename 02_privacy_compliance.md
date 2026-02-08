# SignalCast: Privacy & Compliance Framework

## Overview

SignalCast operates in the B2B marketing intelligence space, which involves processing firmographic data to identify and reach corporate decision-makers. This document outlines the privacy-by-design principles and compliance measures built into the protocol.

---

## Regulatory Landscape

SignalCast acknowledges the following regulatory frameworks:

| Regulation | Jurisdiction | Key Requirements |
|------------|--------------|------------------|
| **GDPR** | EU/EEA | Lawful basis, data minimization, right to erasure |
| **CCPA/CPRA** | California | Opt-out rights, disclosure requirements |
| **ePrivacy Directive** | EU | Cookie consent, electronic communications |
| **CAN-SPAM** | United States | Commercial email requirements |

---

## Data Categories & Handling

### What SignalCast Processes

| Data Type | Example | Storage | Purpose |
|-----------|---------|---------|---------|
| **IP Address** | 198.51.100.47 | Hashed only | Firmographic attribution |
| **ASN/Org Name** | "NovaTech Inc." | Aggregated | Target verification |
| **Behavioral Signals** | Scroll patterns, click timing | Ephemeral | Bot detection |
| **Conversion Data** | Email domain submitted | Hashed | Lead qualification |

### What SignalCast Does NOT Process

- **Personal names** (unless voluntarily submitted via form)
- **Personal email addresses** (only domain extracted and hashed)
- **Browsing history** beyond the single session
- **Cross-site tracking** or persistent identifiers
- **Sensitive categories** (health, political views, etc.)

---

## Privacy-by-Design Principles

### 1. Data Minimization

Miners and validators process only the minimum data required for firmographic verification:

```
Raw IP → Reverse Lookup → Org Name + ASN → Hash → Discard Raw IP
```

No raw IP addresses are stored beyond the validation window (~1 hour).

### 2. Aggregation Over Identification

SignalCast targets **organizations**, not individuals. The goal is to verify "this click came from a Salesforce customer" — not to identify the specific person.

Scoring is based on:
- Organization membership (firmographic)
- Conversion actions (behavioral)
- NOT personal identity

### 3. First-Party Consent at Conversion

When a user downloads a whitepaper or submits a demo request, they provide:
- Work email address (voluntary)
- Consent to advertiser contact (via form)

This is standard B2B lead generation practice, governed by the advertiser's privacy policy.

### 4. No Persistent Tracking

SignalCast does not:
- Set cookies
- Use browser fingerprinting for cross-session identification
- Build persistent user profiles

Each session is evaluated independently. Behavioral signals (cursor movement, scroll patterns) are used solely for real-time bot detection and discarded immediately.

---

## Lawful Basis (GDPR)

For EU-originated traffic, SignalCast operates under:

### Legitimate Interest (Article 6(1)(f))

B2B marketing to corporate decision-makers in their professional capacity is recognized as a legitimate interest under GDPR, provided:

1. **Necessity:** Firmographic verification is necessary to prevent fraud and ensure advertiser ROI.
2. **Balancing:** Processing is limited to professional context; no sensitive data is involved.
3. **Safeguards:** Data minimization, hashing, and short retention periods protect individual rights.

### Right to Object

Users may object to processing by:
- Contacting the advertiser directly
- Using browser-level tracking prevention (respected by SignalCast)
- Submitting erasure requests to validators (processed within 72 hours)

---

## Compliance Measures for Miners

Miners operating SignalCast nodes must:

1. **Not store raw telemetry** beyond the submission window
2. **Not attempt to de-anonymize** hashed data
3. **Not sell or transfer** telemetry to third parties
4. **Operate redirect proxies** in privacy-respecting jurisdictions

Violations result in stake slashing and network exclusion.

---

## Compliance Measures for Validators

Validators must:

1. **Verify firmographic data** only against authorized registries
2. **Discard raw data** after epoch validation
3. **Maintain audit logs** of data handling (hashed, not raw)
4. **Report compliance metrics** in validator transparency reports

---

## Advertiser Responsibilities

Advertisers using SignalCast are responsible for:

1. Maintaining compliant landing pages with clear privacy policies
2. Obtaining proper consent for lead follow-up
3. Honoring opt-out and erasure requests
4. Not using SignalCast for prohibited categories (e.g., political targeting)

SignalCast is a **distribution layer**, not a data controller for end-user PII. Advertisers remain the data controllers for any leads generated.

---

## Summary

SignalCast is designed to operate within the boundaries of modern privacy regulation by:

- Processing organizational data, not personal data
- Minimizing and hashing all telemetry
- Avoiding persistent tracking or cross-site identification
- Relying on legitimate interest for B2B professional context
- Placing compliance obligations on all network participants

This framework ensures SignalCast can deliver precision B2B targeting while respecting user privacy and regulatory requirements.

---

Say "next" for file 3.
