# SignalCast: Incentive & Mechanism Design

SignalCast is an intelligent distribution layer that bridges the gap between AI content creation (**Subnet 93 / Bitcast**) and real-world industrial impact. The mechanism is designed to transform anonymous social media reach into verified corporate interest and competitive market share by exclusively targeting the customer bases of major competitors.

---

Got it. Let me rewrite the worked example with a Bittensor subnet as advertiser targeting a competitor's users.

---

**Updated Worked Example:**

---

## Worked Example: The Interest Pipeline in Action

### Scenario: Subnet 64 (Chutes) vs. Replicate

**Advertiser:** Chutes.ai (Bittensor SN64 — serverless AI inference)
**Target:** Replicate customers experiencing latency or pricing pain
**Asset:** SN93-generated explainer video: "How Devs Cut Inference Costs 60% by Switching from Replicate to Chutes"

**Stage 1 — Task Ingest:** Validator broadcasts brief with Target Account List (known Replicate customers from BuiltWith/GitHub integrations) and conversion targets (API signups, docs visits, Discord joins).

**Stage 2 — Miner Reconnaissance:** Miner 0x7A3F identifies a YC-backed startup "VoiceFlow AI" as a heavy Replicate user via their public GitHub repo. Detects a frustrated tweet from their CTO: "Replicate cold starts are killing our UX." Locates an active Hacker News thread about inference costs.

**Stage 3 — Precision Placement:** Miner replies in HN thread with tracked link: "Saw a comparison showing Chutes cuts cold starts by 80%. Runs on Bittensor infra. [link]"

**Stage 4 — Conversion:** VoiceFlow CTO clicks from office IP, watches explainer (3:45), visits Chutes docs, signs up for API access with work email (alex@voiceflow.ai), joins Discord.

**Stage 5 — Validation:** Validator confirms:
- Reverse IP → VoiceFlow AI Inc.
- VoiceFlow on Target Account List (Replicate customer) → **10x Conquest Multiplier**
- API signup → **10x Conversion Weight**
- Human behavior verified via Honey-Link
- Reasoning trace quality: strong → **+5% bonus**

**Final Score:** 1.0 × 10 × 10 × 1.05 = **105 points** (vs 0.1 for random residential click)

**Stage 6 — Reward:** Miner receives ~6 TAO. Chutes pays ~2 TAO success fee on verified conversion.

**Outcome:** Replicate loses a customer touchpoint. Chutes gains a qualified developer lead. Bittensor ecosystem grows.

---

## Emission and Reward Logic

The SignalCast emission schedule follows a **Strategic Conquest** model that prioritizes the acquisition of a competitor's market share over raw reach. Emissions are weighted based on the **Authority** of the customer audience and the **Depth** of their conversion.

* **Tier 1: Competitor Customer Conquest (50%):** The highest priority emission tier. A **10x multiplier** is applied to verified engagement originating from the corporate domains of a competitor's known customer base. 
* **Tier 2: High-Fit Industry Targets (30%):** A **3x multiplier** is applied to engagement from companies within the same industrial vertical that fit the Ideal Customer Profile (ICP) but are not yet confirmed as competitor clients.
* **Tier 3: Standard Performance & Discovery (20%):** Base rewards for organic conversion across general niche audiences. Internal traffic from competitor corporate domains is demoted to a **0.1x multiplier** to discourage waste and ensure focus remains on external customer acquisition.
* **Technographic Bounties:** A dynamic pool of emissions is reserved for miners who are the first to detect and act upon "Market Ruptures" within a competitor's customer base, such as detecting a client removing a competitor's script or starting a software migration.

---

## Incentive Alignment for Miners and Validators

The mechanism ensures that all participants profit only when the advertiser—and by extension, the Bitcast ecosystem—sees a measurable ROI from a competitor's market.

* **Miners (Market Snipers):** Miners are incentivized to perform **Adversarial Reconnaissance**. Because rewards are weighted heavily toward a competitor's customers, miners must map the rival's client list and identify "Pulse Zones" (gated forums, industrial Slack groups, X.com threads) where those specific customers' decision-makers gather.
* **Validators (Firmographic Oracles):** Validators act as the arbiters of **Lead Authority**. Their dividends depend on their ability to accurately distinguish between a competitor's customer and residential bot noise. By cross-referencing visitor telemetry with technographic registries and the SN93 conversion loop, they ensure emissions are backed by genuine industrial intent.
* **The Cross-Subnet Synergy:** By utilizing the SN93 (Bitcast) output, SignalCast creates a high-velocity feedback loop where the highest quality AI creative assets are directed at the most valuable potential churn opportunities in the market.

---

## Mechanisms to Discourage Low-Quality or Adversarial Behavior

SignalCast maintains a "Zero-Trust" environment through **Economic Deterrence** and **Firmographic Filtering**.

* **Stake-at-Risk (Slashing):** Miners must stake Alpha/TAO to participate in premium briefs. If a miner's traffic is flagged as fraudulent or fails to meet the "Customer-Only" targeting criteria (verified by Reverse IP), their stake is burned.
* **Honey-Link Telemetry:** Validators "wrap" distributed links in invisible telemetry layers. If a click occurs without human-like behavioral variance (e.g., linear scroll velocity or lack of cursor jitter), it is disqualified from the Tier 1 payout.
* **Saturation Throttling:** To protect an advertiser's brand reputation, validators apply frequency caps. If a miner "spams" a target customer account too frequently, their rewards for that account are zeroed out to prevent brand damage.

---

## Proof of Intelligence Framework

SignalCast qualifies as a **Proof of Intelligence** subnet by requiring complex, non-algorithmic market logic that cannot be solved by brute-force hardware.

### Why This Qualifies as Proof of Intelligence

| Requirement | SignalCast Implementation |
|-------------|---------------------------|
| **Non-trivial task** | Competitive intelligence requires research, reasoning, and judgment |
| **Verifiable output** | Reasoning traces can be checked against evidence |
| **Resistance to gaming** | Fabricated reasoning fails consistency checks; volume without quality is penalized |
| **Economic alignment** | Rewards scale with reasoning quality, not just placement volume |
| **Skill differentiation** | Miners with better intelligence capabilities consistently outperform |

### Strategic Reasoning Submission

Miners must submit a **reasoning trace** alongside each placement proof:

```json
{
  "placement_proof": "https://x.com/thread/...",
  "telemetry_bundle": "hash:0x7a3f...",
  "reasoning": {
    "target_identification": "NovaTech identified as Salesforce customer via BuiltWith + G2 review",
    "pain_point_match": "Asset addresses cost reduction; G2 review mentions pricing frustration",
    "timing_rationale": "Q1 renewal cycle; competitor outage reported 48h ago",
    "channel_selection": "VP RevOps active in CRM discussion thread"
  }
}
```

Validators score reasoning quality across four dimensions (target identification, pain point match, timing rationale, channel selection), with strong reasoning earning up to 20% bonus multiplier.

### The Intelligence Hierarchy

SignalCast rewards intelligence at multiple levels:

1. **Level 1 — Channel Access:** Developing presence in gated professional communities
2. **Level 2 — Strategic Matching:** Connecting assets to verified targets with coherent reasoning
3. **Level 3 — Signal Detection:** Identifying technographic shifts and pain points from noisy data
4. **Level 4 — Market Prediction:** Anticipating decision windows before signals appear (highest reward)

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

SignalCast is **SN93-compatible, not SN93-dependent**. The subnet's core innovation—decentralized precision B2B distribution—is valuable for any content.

---

## High-Level Algorithm: The Interest Pipeline

SignalCast miners bridge the gap between social awareness and industrial intent. Potential customers discover "Lead Magnets" (Whitepapers, Demos, Contact Forms) through the following loop:

1. **Task Ingest & Discovery:** Validators pull active SN93 assets, Target Account Lists (TAL), and Lead Magnets. Miners place these assets in front of "problem-aware" customer audiences on X.com and industry-specific hubs.
2. **Engagement (Social Interest):** High-authority targets from the competitor's customer base interact with the asset (Likes, Follows, Reposts). Validators verify these via social APIs, triggering Tier 2/3 rewards.
3. **Conversion (Industrial Intent):** Customers follow the SignalCast-tracked link to the advertiser's landing page and perform high-value actions:
   * **Resource Ingest:** Downloading technical Whitepapers or Case Studies.
   * **Product Evaluation:** Signing up for live Demos.
   * **Direct Inquiry:** Submitting Contact Forms for procurement.
4. **Validation (The Audit):** Validators cross-reference these off-chain events with the SN93 data loop and Reverse IP lookups to verify the lead's **Customer Status** and issue Tier 1 "Conquest" rewards.
5. **Scoring & Allocation:** Validators calculate the final score based on the **Conquest Multiplier** and **Conversion Depth**. Yuma Consensus processes these weights to allocate block rewards.

---
