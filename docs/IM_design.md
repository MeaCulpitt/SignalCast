# SignalCast: Incentive & Mechanism Design

SignalCast is an intelligent distribution layer that bridges the gap between AI content creation (**Subnet 93 / Bitcast**) and real-world industrial impact. The mechanism is designed to transform anonymous social media reach into verified corporate interest by placing content in front of the **right eyeballs** — decision-makers who already use competitor products and are most likely to benefit from alternatives.

---

## Worked Example: The Interest Pipeline in Action

### Scenario: Subnet 64 (Chutes) vs. Replicate

**Advertiser:** Chutes.ai (Bittensor SN64 — serverless AI inference)
**Target Audience:** Developers currently using Replicate who may benefit from lower latency and pricing
**Asset:** SN93-generated explainer video: "How Devs Cut Inference Costs 60% with Chutes"

**Stage 1 — Task Ingest:** Validator broadcasts brief with Target Account List (known Replicate users from BuiltWith/GitHub integrations) and conversion targets (API signups, docs visits, Discord joins).

**Stage 2 — Miner Research:** Miner 0x7A3F identifies a YC-backed startup "VoiceFlow AI" as a Replicate user via their public GitHub repo. Notices a tweet from their CTO discussing cold start latency challenges. Locates an active Hacker News thread about inference costs.

**Stage 3 — Precision Placement:** Miner replies in HN thread with tracked link: "Saw a comparison showing Chutes handles cold starts differently. Runs on Bittensor infra. [link]"

**Stage 4 — Conversion:** VoiceFlow CTO clicks from office IP, watches explainer (3:45), visits Chutes docs, signs up for API access with work email (alex@voiceflow.ai), joins Discord.

**Stage 5 — Validation:** Validator confirms:
- Reverse IP → VoiceFlow AI Inc.
- VoiceFlow on Target Account List (Replicate user) → **10x Precision Multiplier**
- API signup → **10x Conversion Weight**
- Human behavior verified via Honey-Link
- Reasoning trace quality: strong → **+5% bonus**

**Final Score:** 1.0 × 10 × 10 × 1.05 = **105 points** (vs 0.1 for random residential click)

**Stage 6 — Reward:** Miner receives ~6 TAO. Chutes pays ~2 TAO success fee on verified conversion.

**Outcome:** Content reached someone who actually needed it. Developer discovered a solution to their problem. Bittensor ecosystem grows.

---

## Emission and Reward Logic

The SignalCast emission schedule follows a **Precision Targeting** model that prioritizes reaching the right audience over raw reach. Emissions are weighted based on the **Relevance** of the audience and the **Depth** of their conversion.

* **Tier 1: Verified Relevant Audience (50%):** The highest priority emission tier. A **10x multiplier** is applied to verified engagement from users of competing products — people most likely to benefit from the advertised solution.
* **Tier 2: High-Fit Industry Targets (30%):** A **3x multiplier** is applied to engagement from companies within the same vertical that fit the Ideal Customer Profile (ICP) but are not yet confirmed as competitor users.
* **Tier 3: Standard Performance & Discovery (20%):** Base rewards for organic conversion across general niche audiences.
* **Discovery Bounties:** A dynamic pool of emissions is reserved for miners who identify new pockets of relevant audiences — mapping which companies use which tools enables better content targeting.

------

## Journey-Weighted Scoring

Single conversions are valuable, but sustained engagement over time is more valuable. SignalCast rewards miners who nurture accounts through the full buyer journey.

### Time-Weighted Multipliers

| Journey Length | Multiplier | Rationale |
|----------------|------------|-----------|
| Single touchpoint | 1x | Base conversion value |
| 2-3 touchpoints over 14 days | 1.5x | Demonstrated follow-through |
| 4+ touchpoints over 30 days | 2x | Full nurture sequence |
| Multi-stakeholder engagement (same company) | 3x | Account penetration |

### Journey Attribution

When multiple miners touch the same account, rewards are distributed based on contribution:

* **First touch (awareness):** 20% of final conversion value
* **Middle touches (consideration):** 10% each, capped at 30% total
* **Last touch (conversion):** 50% of final conversion value

This prevents "swoop and grab" tactics where miners wait for accounts already in-market and claim full credit for a single touchpoint.

### Example

1. Miner A places content in HN thread. VoiceFlow CTO clicks, reads, leaves.
2. Two weeks later, Miner B places related content in industry newsletter. Same CTO clicks, downloads whitepaper.
3. One week later, Miner A places demo video in LinkedIn. CTO books demo.

**Attribution:** Miner A: 20% + 50% = 70%. Miner B: 30%. Both rewarded proportionally.

---

## Incentive Alignment for Miners and Validators

The mechanism ensures that all participants profit only when content reaches people who genuinely benefit from seeing it.

* **Miners (Audience Researchers):** Miners are incentivized to perform **Audience Discovery**. Because rewards are weighted heavily toward reaching verified competitor users, miners must research which companies use which tools and identify channels where those decision-makers gather.
* **Validators (Verification Oracles):** Validators act as the arbiters of **Audience Accuracy**. Their dividends depend on their ability to accurately verify that content reached the intended audience. By cross-referencing visitor telemetry with technographic registries and the SN93 conversion loop, they ensure emissions are backed by genuine relevance.
* **The Cross-Subnet Synergy:** By utilizing the SN93 (Bitcast) output, SignalCast creates a feedback loop where high-quality AI creative assets are directed at the audiences most likely to benefit from them.

---

## Mechanisms to Discourage Low-Quality or Adversarial Behavior

SignalCast maintains a "Zero-Trust" environment through **Economic Deterrence** and **Audience Filtering**.

* **Stake-at-Risk (Slashing):** Miners must stake Alpha/TAO to participate in premium briefs. If a miner's traffic is flagged as fraudulent or irrelevant to the target audience, their stake is burned.
* **Honey-Link Telemetry:** Validators "wrap" distributed links in invisible telemetry layers. If a click occurs without human-like behavioral variance (e.g., linear scroll velocity or lack of cursor jitter), it is disqualified from the Tier 1 payout.
* **Saturation Throttling:** To protect an advertiser's brand reputation, validators apply frequency caps. If a miner over-exposes a target account, their rewards for that account are zeroed out.

---

## Proof of Intelligence Framework

SignalCast qualifies as a **Proof of Intelligence** subnet by requiring complex, non-algorithmic audience research that cannot be solved by brute-force hardware.

### Why This Qualifies as Proof of Intelligence

| Requirement | SignalCast Implementation |
|-------------|---------------------------|
| **Non-trivial task** | Audience research requires investigation, reasoning, and judgment |
| **Verifiable output** | Reasoning traces can be checked against evidence |
| **Resistance to gaming** | Fabricated reasoning fails consistency checks; volume without quality is penalized |
| **Economic alignment** | Rewards scale with targeting accuracy, not just placement volume |
| **Skill differentiation** | Miners with better research capabilities consistently outperform |

### Strategic Reasoning Submission

Miners must submit a **reasoning trace** alongside each placement proof:

```json
{
  "placement_proof": "https://news.ycombinator.com/item?id=...",
  "telemetry_bundle": "hash:0x7a3f...",
  "reasoning": {
    "audience_identification": "VoiceFlow identified as Replicate user via GitHub repo imports",
    "relevance_match": "Asset addresses cold start latency; CTO tweet mentions this exact challenge",
    "timing_rationale": "Active HN thread on inference costs; high visibility window",
    "channel_selection": "Technical audience, high-authority context, CTO known to be active"
  }
}
```

Validators score reasoning quality across four dimensions (audience identification, relevance match, timing rationale, channel selection), with strong reasoning earning up to 20% bonus multiplier.

### The Intelligence Hierarchy

SignalCast rewards intelligence at multiple levels:

1. **Level 1 — Channel Access:** Developing presence in professional communities where target audiences gather
2. **Level 2 — Strategic Matching:** Connecting assets to verified audiences with coherent reasoning
3. **Level 3 — Signal Detection:** Identifying audience needs and pain points from noisy data
4. **Level 4 — Audience Prediction:** Anticipating which users are ready for alternatives before explicit signals appear (highest reward)

---

## Content Source Flexibility

While Subnet 93 (Bitcast) is SignalCast's primary integration partner, the architecture is **content-source agnostic**.

### Supported Asset Types

| Source | Asset Type | Integration Status |
|--------|------------|-------------------|
| **SN93 (Bitcast)** | AI-generated video | Primary (native) |
| **Advertiser-provided** | Whitepapers, case studies, landing pages | Supported |
| **Other Bittensor subnets** | SN17 (3D), SN59 (audio), future content subnets | Planned |
| **External CDNs** | Any URL-addressable content | Supported |

SignalCast is **SN93-compatible, not SN93-dependent**. The subnet's core innovation—precision B2B distribution to the right audience—is valuable for any content.

---

## High-Level Algorithm: The Interest Pipeline

SignalCast miners bridge the gap between content and the right audience. Potential customers discover "Lead Magnets" (Whitepapers, Demos, APIs) through the following loop:

1. **Task Ingest & Discovery:** Validators pull active SN93 assets, Target Account Lists (TAL), and Lead Magnets. Miners place these assets in front of relevant audiences on X.com and industry-specific hubs.
2. **Engagement (Interest Signal):** Relevant targets interact with the asset (Likes, Follows, Reposts). Validators verify these via social APIs, triggering Tier 2/3 rewards.
3. **Conversion (Action):** Users follow the SignalCast-tracked link to the advertiser's landing page and perform high-value actions:
   * **Resource Ingest:** Downloading technical Whitepapers or Case Studies.
   * **Product Evaluation:** Signing up for Demos or API access.
   * **Direct Inquiry:** Submitting Contact Forms.
4. **Validation (The Audit):** Validators cross-reference these events with technographic data to verify the lead's **Audience Relevance** and issue Tier 1 rewards.
5. **Scoring & Allocation:** Validators calculate the final score based on the **Precision Multiplier** and **Conversion Depth**. Yuma Consensus processes these weights to allocate block rewards.

---
