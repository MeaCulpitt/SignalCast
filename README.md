# SignalCast: Precision Distribution for Bittensor

SignalCast is a decentralized **Audience Research & Precision Distribution Layer** built on Bittensor. It places AI-generated content from **Subnet 93 (Bitcast)** in front of the **right audiences** — decision-makers who currently use competitor products and would genuinely benefit from alternatives.

Unlike traditional advertising networks that optimize for impressions, SignalCast optimizes for **Audience Relevance and Verified Conversions**.

---

## The Problem

Most B2B advertising is wasted. Content reaches random audiences, CAC keeps rising, and decision-makers suffer from ad blindness.

**SignalCast fixes this** by ensuring content reaches people who actually need to see it — users of competing products who have the exact problem your product solves.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────┐
│                     THE INTEREST PIPELINE                        │
├─────────────────────────────────────────────────────────────────┤
│  1. RESEARCH      Miners identify who uses competitor products  │
│                   and where those users gather online            │
├─────────────────────────────────────────────────────────────────┤
│  2. PLACEMENT     Content placed in relevant communities        │
│                   (HN, Discord, Slack, X.com threads)           │
├─────────────────────────────────────────────────────────────────┤
│  3. CONVERSION    Users discover content, take action           │
│                   (API signup, demo request, whitepaper DL)     │
├─────────────────────────────────────────────────────────────────┤
│  4. VERIFICATION  Validators confirm audience relevance         │
│                   via multi-modal checks                        │
└─────────────────────────────────────────────────────────────────┘
```

**Miners** earn TAO by placing content in front of verified competitor users.

**Validators** verify that content reached the intended audience.

**Advertisers** pay only for verified conversions from relevant audiences.

---

## Example: Chutes vs. Replicate

1. **Chutes.ai** (SN64) wants to reach developers using Replicate
2. Miner identifies VoiceFlow AI as a Replicate user via GitHub
3. Miner places Chutes explainer video in Hacker News thread on inference costs
4. VoiceFlow CTO clicks, watches, signs up with work email
5. Validator confirms VoiceFlow is on Target Account List → **10x reward**
6. Miner earns TAO. Chutes pays success fee.

Content reached someone who genuinely needed it.

---

## Scoring System

### Score Calculation

```
Score = Base (1.0) × Tier Multiplier × Conversion Multiplier
```

### Tier Multipliers

| Tier | Audience | Multiplier |
|------|----------|------------|
| Tier 1 | Verified competitor users | 10x |
| Tier 2 | High-fit industry targets | 3x |
| Tier 3 | General relevant audience | 1x |

### Conversion Multipliers

| Conversion Type | Multiplier |
|----------------|------------|
| API Signup | 10x |
| Demo Request | 5x |
| Whitepaper Download | 2x |
| Social Follow | 1x |
| Engagement | 0.5x |

### Emission Distribution

- **80%** to miners (proportional to scores)
- **20%** to validators

---

## Key Features

### Precision Targeting
Reach users of specific competitor products, not random audiences. Miners research which companies use which tools and find where those decision-makers gather.

### Multi-Modal Verification
Reverse IP alone misses 40% of remote workers. SignalCast uses verification: technographic context, reverse IP, behavioral signals, referral context, and conversion verification.

### Proof of Intelligence
Audience research requires genuine investigation and judgment — not compute. Miners must document evidence for verification.

### Privacy by Design
No PII storage. IPs hashed immediately. No cookies or cross-site tracking. GDPR-compatible under legitimate interest for B2B professional context.

---

## Documentation

| Document | Description |
|----------|-------------|
| [Incentive & Mechanism Design](./docs/IM_design.md) | Emission logic, reward tiers, proof of intelligence framework |
| [Miner Architecture](./docs/Miner.md) | Audience research, placement, telemetry |
| [Validator Architecture](./docs/Validator.md) | Verification stack, scoring, fraud detection |
| [Advertiser Integration](./docs/Advertiser_Integration.md) | How advertisers receive and act on verified leads |
| [Business Logic](./docs/Business_Logic.md) | Problem statement, competitive landscape, privacy compliance |
| [Go-To-Market Strategy](./docs/GTM_strategy.md) | Target users, growth channels, early incentives |

---

## For Miners

Earn TAO by:
1. Researching which companies use which competitor products
2. Finding channels where those users gather
3. Placing relevant content with tracked links
4. Submitting evidence for verification

**Entry:** 0.2 TAO stake required. No conversion threshold — anyone can participate.

---

## For Validators

Earn dividends by:
1. Verifying that content reached intended audiences
2. Validating tier claims (Tier 1/2/3)
3. Confirming conversion depth

Validators receive **20%** of the emission pool. Validators operate under **Yuma Consensus** (Bittensor's standard validator mechanism).

---

## For Advertisers

Pay only for results:
1. Define your target audience (competitor users, industry, ICP)
2. Provide content or use SN93 assets
3. Set conversion targets (signups, demos, downloads)
4. Pay success fee only on verified conversions

Payments accepted in TAO, stablecoins, or fiat — all converted to TAO via oracle for distribution to miners and validators.

---

## Getting Started

### Pilot Program

SignalCast launches with a curated pilot to solve the cold-start problem:

**Phase 0: Closed Beta (Weeks 1-4)**
- 5-10 B2B tech companies provide Target Account Lists and conversion tracking
- Miners compete on known-good accounts with clear success criteria
- Validators calibrate scoring against real conversion data

**Phase 1: Case Study Publication (Week 5-6)**
- Publish verified ROI metrics from pilot participants
- Document cost-per-qualified-lead vs. traditional channels
- Release miner earnings data to attract competitive talent

**Phase 2: Open Registration (Week 7+)**
- Open advertiser onboarding
- Miner registration (0.2 TAO stake)
- Full emission schedule activated

---

## License

MIT
```
