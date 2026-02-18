# SignalCast: Advertiser Integration Guide

SignalCast delivers verified B2B leads through precision audience targeting. This document describes how advertisers receive and act on that value.

---

## How It Works

### 1. Create a Brief

Advertisers create a campaign brief defining:

| Field | Description |
|-------|-------------|
| Target Audience | Tier definition (competitor users, industry, ICP) |
| Content Asset | SN93 video, whitepaper, landing page, etc. |
| Conversion Goals | What counts as conversion (API signup, demo, download) |
| Success Fee | TAO paid per verified conversion |

### 2. Targeting Options

| Input Type | Description |
|------------|-------------|
| **Exact Account List** | Specific companies to target (automatic Tier 1 if converted) |
| **ICP Description** | "Companies using X, Y, Z in industry A, size B" |
| **Discovery-Only** | No list provided — miners find targets |
| **Hybrid** | Seed list + miner discovery |

### 3. Receive Verified Conversions

- Miners research and place content with verified audiences
- Validators confirm audience relevance
- Advertisers only pay for verified conversions

---

## Dashboard

Every advertiser receives access to a real-time dashboard showing:

- **Target Account Engagement:** Which companies have interacted with content
- **Funnel Progression:** Awareness → Consideration → Conversion breakdown
- **Miner Attribution:** Which miners drove which engagements
- **Spend & ROI:** TAO spent vs. verified conversions

---

## CRM Integration

SignalCast pushes intent signals directly into your sales workflow.

### Supported Platforms

- Salesforce
- HubSpot
- Pipedrive
- Custom webhook

### Data Pushed

- Company name (from firmographic verification)
- Contact email (if provided at conversion)
- Engagement history (touchpoints, content consumed, timestamps)
- Confidence score (Tier 1/2/3)
- Conversion type (API signup, demo, whitepaper, follow, engagement)

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

- New accounts engaged this week
- Accounts progressing through funnel
- Conversions pending sales follow-up
- Suggested optimizations (content performing well, underperforming segments)

---

## Pricing

Advertisers pay a success fee per verified conversion. No spend required unless results are delivered.

| Conversion Type | Success Fee (TAO) |
|----------------|---------------------|
| API Signup | 2-5 |
| Demo Request | 1-3 |
| Whitepaper Download | 0.5-1 |
| Social Follow | 0.2-0.5 |
| Engagement | 0.1 |

**Pricing Factors:**

- Advertiser sets budget caps and conversion targets
- Higher Tier targeting (verified competitor users) commands higher fees
- Spend only occurs on verified outcomes
- Dashboard access and CRM integration are free

---

## Getting Started

1. **Connect wallet** — TAO for success fees
2. **Create brief** — Define target audience and goals
3. **Upload content** — Provide assets or use SN93 content
4. **Set budget** — Cap maximum spend
5. **Receive leads** — Verified conversions via dashboard or CRM
