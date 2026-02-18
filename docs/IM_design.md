# SignalCast: Incentive & Mechanism Design

---

## 1. Executive Summary

SignalCast is a decentralized Audience Research & Precision Distribution Layer built on Bittensor. It connects AI-generated content (primarily from Subnet 93 / Bitcast) with verified decision-makers who would genuinely benefit from the advertised solution — transforming anonymous reach into verified corporate interest.

The mechanism rewards **precision over volume**, **intelligence over automation**, and **long-term relationship building over single-touch conversions**.

---

## 2. Emission and Reward Logic

Emissions follow a **Precision Targeting** model that prioritizes reaching the right audience over raw reach.

### 2.1 Audience Tier Multipliers

| Tier | Audience | Multiplier |
|------|----------|------------|
| Tier 1 | Verified competitor users (self-reported need or first-party list match) | 10x |
| Tier 2 | High-fit industry targets (technographic match, not confirmed competitor) | 3x |
| Tier 3 | General relevant audience (niche community members) | 1x |
| Tier 4 | Low-confidence / residential / inferred only | 0.1x |

### 2.1.1 Tier Determination and Verification

Each tier is determined by the **verification method** used to confirm the audience. Miners claim a tier when submitting placement; validators verify or downgrade.

#### Tier 1: Verified Competitor Users (10x)

**Verification Methods:**
- **Self-reported need:** User explicitly stated a need or pain point (e.g., "Looking for Replicate alternatives," "Cold starts are killing us")
  - Source: Social media, forums, support tickets, review sites
  - Must include company identification and specific need expressed
- **First-party list match:** Advertiser provided company on their target list
  - Source: Advertiser-uploaded account list
  - Automatic Tier 1 if conversion occurs from listed company

**Required Evidence:**
- URL or transcript of self-reported need
- Company name and verified domain
- Clear link between stated need and advertised solution

#### Tier 2: High-Fit Industry Targets (3x)

**Verification Methods:**
- **Technographic data:** Evidence company uses competitor product
  - Source: BuiltWith, Clearbit, GitHub (imports, dependencies), StackShare, SimilarTech
  - Must show active/in recent usage (not abandoned projects)
- **Job postings:** Company hiring for roles indicating scale (e.g., ML Engineer, DevOps at scale)
  - Source: LinkedIn, job boards
  - Must correlate with advertised product category

**Required Evidence:**
- Data source URL or API response showing product usage
- Timestamp within last 90 days
- Company verification (domain matches)

#### Tier 3: General Relevant Audience (1x)

**Verification Methods:**
- **Contextual match:** Company in same industry/vertical, fits Ideal Customer Profile (ICP)
  - Source: Company website, LinkedIn, Crunchbase
  - ICP criteria: industry, company size, geography, role of decision-maker
- **Community membership:** Active in relevant communities (niche Discord, Slack, forums)
  - Source: Community membership verification, activity logs

**Required Evidence:**
- Company profile showing industry/vertical alignment
- ICP fit justification (size, geography, use case)
- No direct competitor usage confirmed

#### Tier 4: Low-Confidence / Inferred (0.1x)

**Verification Methods:**
- **Reverse-IP only:** IP address mapped to company via WHOIS or IP database
  - Source: IP geolocation, WHOIS lookup
  - No additional confirmation
- **Residential IP flag:** IP resolves to residential ISP (remote worker or false positive)
  - Source: IP reputation database

**Required Evidence:**
- IP-to-company mapping (even if weak)
- Flag for residential/unverified IP

### 2.1.2 Verification Flow

1. **Miner submits placement** with reasoning trace including claimed tier
2. **Validator verifies** the signal source exists:
   - Tier 1: Check self-reported signal or first-party list match
   - Tier 2: Pull technographic data to confirm competitor usage
   - Tier 3: Verify industry/ICP fit
   - Tier 4: Reverse-IP lookup only
3. **Tier confirmed or downgraded** — validator may lower tier if evidence is weak
4. **Dispute possible** — miner can appeal with additional evidence

---

### 2.2 Conversion Depth Multipliers

| Conversion Type | Multiplier |
|----------------|------------|
| API signup / Demo request | 10x |
| Whitepaper download | 5x |
| Social follow | 3x |
| Engagement (like/repost) | 1x |

### 2.3 Final Score Calculation

```
Final Score = Base Score × Audience Tier × Conversion Depth × Reasoning Bonus
```

- **Base Score:** 1.0 per placement submission
- **Reasoning Bonus:** 0-20% based on validator-scored reasoning quality

---

## 3. First-Party Targeting

Advertisers can provide their own target lists, eliminating miner guesswork.

### 3.1 Advertiser Options

| Input Type | Description | Reward Weight |
|------------|-------------|---------------|
| **Exact Account List** | Specific companies to target | Highest (automatic Tier 1 if converted) |
| **ICP Description** | "Companies using X, Y, Z in industry A, size B" | Miner researches and verifies |
| **Discovery-Only** | No list provided — miner finds targets | Standard tiered rewards |
| **Hybrid** | Seed list + miner discovery | Tier 1 for list matches, standard for discovered |

### 3.2 Signal Taxonomy

When miners don't have a first-party list, they earn based on signal quality:

| Signal Type | Example | Weight |
|-------------|---------|--------|
| Explicit need | "Looking for [competitor] alternatives" | 10x |
| Pain expression | "[Competitor] latency is killing us" | 8x |
| Feature request | "Wish [competitor] had..." | 5x |
| Job postings | Hiring ML infra at scale | 3x |
| Technographic data | BuiltWith, Clearbit, GitHub imports | 1x |

Miners must submit the **source** of their targeting signal. Validators verify it exists.

---

## 4. Journey-Weighted Scoring

Multi-touch sequences are rewarded to prevent "swoop and grab" behavior.

### 4.1 Time-Weighted Multipliers

| Journey Length | Multiplier | Rationale |
|----------------|------------|-----------|
| Single touchpoint | 1x | Base conversion value |
| 2-3 touchpoints over 14 days | 1.5x | Demonstrated follow-through |
| 4+ touchpoints over 30 days | 2x | Full nurture sequence |
| Multi-stakeholder engagement | 3x | Account penetration |

### 4.2 Attribution Model (40/40/20)

| Touch | Reward Share |
|-------|---------------|
| First touch (awareness) | 40% |
| Last touch (conversion) | 40% |
| Highest-engagement touch | 20% |

- Touches expire after 30 days if no conversion
- One miner = one touch per account per campaign (no spam)
- Real-time leaderboard shows active touches and attributed value

---

## 5. Validator Incentive Structure

Validators earn dividends by verifying that content reached the intended audience and scoring miner reasoning quality.

- Validators operate under **Yuma Consensus** (Bittensor's standard validator mechanism)
- Rewards scale with verification accuracy and consistency

---

## 6. Miner Cold Start

New miners need pathways to earn before building a conversion track record.

### 6.1 Discovery Bounties

Separate pool for identifying targets (not just converting):

| Activity | Reward |
|----------|--------|
| Identify a new verified competitor user | 0.1 TAO |
| Find a target company's decision-maker contact | 0.2 TAO |
| Discover a new channel where targets gather | 0.5 TAO |
| First to identify emerging competitor (bonus) | 1.0 TAO |

### 6.2 Tiered Brief Access

| Tier | Conversions | Access | Staking Required |
|------|-------------|--------|------------------|
| Bronze | 0-9 | Learning briefs (practice) | 100 TAO |
| Silver | 10-49 | Premium briefs | 500 TAO |
| Gold | 50-199 | VIP campaigns | 2,000 TAO |
| Platinum | 200+ | Private auctions | 10,000 TAO |

### 6.3 Mentorship Program

- Experienced miners can mentor new participants
- Mentor receives 5% of mentee's earnings for 30 days
- Mentee gets accelerated reputation during probation

### 6.4 Sandbox Mode

- New miners practice on test briefs with validator-controlled fake accounts
- "Practice reputation" converts to real stake after 30 days

---

## 7. Proof of Intelligence Framework

SignalCast qualifies as a Proof of Intelligence subnet by requiring complex, non-algorithmic research.

### 7.1 Why This Qualifies

| Requirement | Implementation |
|-------------|----------------|
| Non-trivial task | Audience research requires investigation, reasoning, judgment |
| Verifiable output | Reasoning traces can be checked against evidence |
| Resistance to gaming | Fabricated reasoning fails consistency checks |
| Economic alignment | Rewards scale with targeting accuracy, not volume |
| Skill differentiation | Miners with better research consistently outperform |

### 7.2 Intelligence Hierarchy

| Level | Description | Reward |
|-------|-------------|--------|
| Level 1 | Channel access — presence in professional communities | Base |
| Level 2 | Strategic matching — asset to verified audience with reasoning | +20% |
| Level 3 | Signal detection — identify needs from noisy data | +50% |
| Level 4 | Audience prediction — anticipate readiness before explicit signals | +100% |

### 7.3 Reasoning Trace Format

Miners submit structured reasoning with each placement:

```json
{
  "placement_proof": "https://news.ycombinator.com/item?id=...",
  "telemetry_bundle": "hash:0x7a3f...",
  "reasoning": {
    "signal_source": "explicit_need | pain_expression | technographic",
    "signal_evidence": "URL or data source",
    "audience_identification": "Company identified as [X] user via [source]",
    "relevance_match": "Asset addresses [specific pain point]",
    "timing_rationale": "Active thread on [topic], high visibility",
    "channel_selection": "Technical audience, [platform], [reason]"
  }
}
```

### 7.4 Reasoning Quality Scoring

Validators score each submission on 4 dimensions (0-5 scale each):

| Dimension | What It Measures |
|-----------|------------------|
| Signal Source Quality | How credible is the targeting signal? |
| Audience Identification | Is the company correctly identified as a target? |
| Relevance Match | Does the content actually address the identified need? |
| Channel Selection | Is this the right platform/context for this audience? |

- Each dimension: 0-5 score
- Total: 0-20 points → 0-20% bonus applied to final score

| Total Score | Reasoning Bonus |
|-------------|------------------|
| 0-4 | 0% |
| 5-8 | 5% |
| 9-12 | 10% |
| 13-16 | 15% |
| 17-20 | 20% |

---

## 8. Anti-Gaming Mechanisms

### 8.1 Stake-at-Risk

- Miners stake TAO to participate in premium briefs
- Fraudulent or irrelevant traffic → stake burned

### 8.2 Honey-Link Telemetry

- Validators wrap links in invisible telemetry
- Non-human behavior (linear scroll, no cursor variance) → disqualification

### 8.3 Frequency Caps

- Validators apply saturation limits per account
- Over-exposed accounts → rewards zeroed for that account

### 8.4 Reasoning Consistency Checks

- Fabricated reasoning fails cross-reference validation
- Pattern of low-quality reasoning → reputation penalty

---

## 9. Content Source Flexibility

SignalCast is content-source agnostic.

| Source | Asset Type | Status |
|--------|------------|--------|
| SN93 (Bitcast) | AI-generated video | Primary |
| Advertiser-provided | Whitepapers, landing pages | Supported |
| Other Bittensor subnets | SN17 (3D), SN59 (audio), future | Extensible |

---

## 10. Emission Summary

| Pool | Allocation |
|------|------------|
| Verified conversions (Tier 1) | 50% |
| High-fit targets (Tier 2) | 30% |
| Discovery & general (Tier 3) | 15% |
| Discovery bounties (new targets) | 5% |
