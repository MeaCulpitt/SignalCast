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
│                   via multi-modal firmographic checks           │
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
6. Miner earns ~6 TAO. Chutes pays ~2 TAO success fee.

Content reached someone who genuinely needed it.

---

## Key Features

### Precision Targeting
Reach users of specific competitor products, not random audiences. Miners research which companies use which tools and find where those decision-makers gather.

### Multi-Modal Verification
Reverse IP alone misses 40% of remote workers. SignalCast uses a 5-layer verification stack: technographic context, reverse IP, behavioral signals, referral context, and conversion verification.

### Proof of Intelligence
Miners submit reasoning traces documenting their audience research. Validators score reasoning quality. Gaming is detected and penalized.

### Privacy by Design
No PII storage. IPs hashed immediately. No cookies or cross-site tracking. GDPR-compatible under legitimate interest for B2B professional context.

### Content Source Flexibility
Primary integration with SN93 (Bitcast), but supports any content source. SignalCast is SN93-compatible, not SN93-dependent.

---

## Documentation

| Document | Description |
|----------|-------------|
| [Incentive & Mechanism Design](./docs/IM_design.md) | Emission logic, reward tiers, proof of intelligence framework |
| [Miner Architecture](./docs/Miner.md) | Audience research, placement, telemetry, reasoning requirements |
| [Validator Architecture](./docs/Validator.md) | Multi-modal verification stack, scoring, fraud detection |
| [Business Logic](./docs/Business_Logic.md) | Problem statement, competitive landscape, privacy compliance |
| [Go-To-Market Strategy](./docs/GTM_strategy.md) | Target users, growth channels, early incentives |

---

## Reward Tiers

| Tier | Audience | Multiplier |
|------|----------|------------|
| **Tier 1** | Verified competitor users | 10x |
| **Tier 2** | High-fit industry targets | 3x |
| **Tier 3** | General relevant audience | 1x |
| **Tier 4** | Low confidence / residential | 0.1x |

Conversion depth adds another multiplier:
- API signup / Demo request: 10x
- Whitepaper download: 5x
- Social follow: 3x
- Engagement (like/repost): 1x

---

## For Miners

Earn TAO by:
1. Researching which companies use which competitor products
2. Finding channels where those users gather
3. Placing relevant content with tracked links
4. Submitting reasoning traces documenting your research

Higher rewards for better audience research and deeper conversions.

---

## For Validators

Earn dividends by:
1. Verifying that content reached intended audiences
2. Running multi-modal firmographic checks
3. Scoring miner reasoning quality
4. Detecting and flagging fraudulent placements

---

## For Advertisers

Pay only for results:
1. Define your target audience (users of specific competitor products)
2. Provide content or use SN93 assets
3. Set conversion targets (signups, demos, downloads)
4. Pay TAO success fee only on verified conversions

---

## Getting Started

*Coming soon: Miner setup guide, Validator requirements, Advertiser onboarding*

---

## Links

- **Bittensor:** https://bittensor.com
- **Subnet 93 (Bitcast):** Content creation partner

---

## License

MIT

---
