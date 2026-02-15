# SignalCast: Advertiser Integration Guide

SignalCast delivers verified B2B leads. This document describes how advertisers receive and act on that value.

---

## Dashboard

Every advertiser receives access to a real-time dashboard showing:

* **Target Account Engagement:** Which companies from your TAL have interacted with content
* **Funnel Progression:** Awareness → Consideration → Conversion breakdown
* **Miner Attribution:** Which miners drove which engagements
* **Spend & ROI:** TAO spent vs. verified conversions

---

## CRM Integration

SignalCast pushes intent signals directly into your sales workflow.

### Supported Platforms
* Salesforce
* HubSpot
* Pipedrive
* Custom webhook

### Data Pushed
* Company name (from firmographic verification)
* Contact email (if provided at conversion)
* Engagement history (touchpoints, content consumed, timestamps)
* Confidence score (FCS tier)
* Conversion type (whitepaper, demo, signup)

### Setup
1. Provide OAuth credentials or webhook URL during onboarding
2. Map SignalCast fields to your CRM schema
3. Define lead routing rules (e.g., Tier 1 → SDR immediate follow-up)

---

## Intent API

For custom integrations, SignalCast exposes a REST API:

```
GET /v1/accounts/{advertiser_id}/engagements
GET /v1/accounts/{advertiser_id}/conversions
POST /v1/accounts/{advertiser_id}/conversion_feedback
```

The feedback endpoint allows advertisers to confirm or reject conversions, feeding into post-conversion validation scoring.

---

## Outcome Reporting

Weekly digest delivered via email or Slack:

* New accounts engaged this week
* Accounts progressing through funnel
* Conversions pending sales follow-up
* Suggested optimizations (content performing well, underperforming segments)

---

## Pricing

| Event | Cost |
|-------|------|
| Tier 1 verified conversion (target account) | 2-5 TAO |
| Tier 2 high-confidence conversion | 0.5-1 TAO |
| Tier 3 moderate conversion | 0.1-0.3 TAO |
| Dashboard access | Free |
| CRM integration | Free |

Advertisers set budget caps and conversion targets. Spend only occurs on verified outcomes.
```
