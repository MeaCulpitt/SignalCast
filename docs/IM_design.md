# SignalCast: Incentive & Mechanism Design

---

## 1. Executive Summary

SignalCast is a decentralized Audience Research & Precision Distribution Layer built on Bittensor. It connects AI-generated content (primarily from Subnet 93 / Bitcast) with verified decision-makers who would genuinely benefit from the advertised solution — transforming anonymous reach into verified corporate interest.

The mechanism rewards **precision over volume**, **intelligence over automation**, and **long-term relationship building over single-touch conversions**.

---

## 2. Emission and Reward Logic

Emissions follow a **Proportional Scoring** model — rewards distribute based on the quality of targeting and conversion depth.

### 2.1 Big Fish Multiplier

| Tier | Audience | Multiplier |
|------|----------|------------|
| Tier 1 | Verified competitor users (self-reported need or first-party list match) | 10x |
| Tier 2 | High-fit industry targets (technographic match, confirmed competitor usage) | 3x |
| Tier 3 | General relevant audience (same industry/ICP, unconfirmed) | 1x |

### 2.1.1 Tier Determination

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
  - ICP criteria: industry, company size, role of decision-maker
- **Community membership:** Active in relevant communities (niche Discord, Slack, forums)
  - Source: Community membership verification, activity logs

**Required Evidence:**
- Company profile showing industry/vertical alignment
- ICP fit justification (size, role)
- No direct competitor usage confirmed

### 2.1.2 Verification Flow

1. **Miner submits placement** with reasoning trace including claimed tier
2. **Validator verifies** the signal source exists:
   - Tier 1: Check self-reported signal or first-party list match
   - Tier 2: Pull technographic data to confirm competitor usage
   - Tier 3: Verify industry/ICP fit
3. **Tier confirmed or downgraded** — validator may lower tier if evidence is weak
4. **Dispute possible** — miner can appeal with additional evidence

---

### 2.2 Conversion Depth Multipliers

| Conversion Type | Description | Multiplier |
|----------------|-------------|------------|
| API Signup | User registers for API access with work email | 10x |
| Demo Request | User requests a product demo | 5x |
| Whitepaper Download | User downloads gated content (case study, research, etc.) | 2x |
| Social Follow | User follows advertiser's Twitter/X, LinkedIn, Discord | 2x |
| Engagement | User likes, reposts, or comments on content | 1x |

---

### 2.3 Final Score Calculation

```
Score = Base (1.0) × Big Fish Multiplier × Conversion Multiplier × Reasoning Bonus
```

- **Base:** 1.0 per placement submission
- **Big Fish Multiplier:** Tier-based (10x, 3x, or 1x)
- **Conversion Multiplier:** Based on conversion depth (1x-10x)
- **Reasoning Bonus:** 0-20% based on validator-scored reasoning quality

---

### 2.4 Proportional Distribution

Emission pool distributes proportionally based on score weights each cycle.

**Example:**

| Miner | Tier | Conversion | Reasoning | Score |
|-------|------|------------|-----------|-------|
| A | Tier 1 | API Signup | 10% | 110 |
| B | Tier 2 | Demo Request | 0% | 15 |
| C | Tier 3 | Engagement | 0% | 1 |
| D | Tier 1 | Social Follow | 5% | 21 |
| E | Tier 1 | API Signup | 15% | 115 |

**Total:** 262 | **Miner A:** 42% of pool | **Miner E:** 44% of pool

The big fish multiplier (10x/3x/1x) already creates natural proportional distribution. No fixed percentages needed.

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

### 3.2 Brief Structure

Each campaign brief contains:

| Field | Description |
|-------|-------------|
| **Advertiser** | Project/subnet seeking distribution |
| **Target Audience** | Tier definition (competitor users, industry, ICP) |
| **Content Asset** | SN93 video, whitepaper, landing page, etc. |
| **Conversion Goals** | What counts as conversion (signups, demos, downloads) |
| **Success Fee** | TAO paid by advertiser per verified conversion |
| **Emitter Reward** | TAO distributed to miner from protocol emissions |

### 3.3 Miner Brief Selection

Miners browse available briefs and choose which to pursue based on:

- **Difficulty:** Higher tiers require more research
- **Competition:** Fewer miners = higher chance of success
- **Reward potential:** Tier 1 + deep conversion = maximum payout

### 3.4 Signal Taxonomy

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
| Multi-stakeholder engagement (same company) | 3x | Account penetration |

### 4.2 Attribution Model (40/40/20)

When multiple miners touch the same account, rewards are distributed:

| Touch | Reward Share | Description |
|-------|---------------|-------------|
| First touch (awareness) | 40% | Initial placement that introduced the solution |
| Last touch (conversion) | 40% | Placement that directly led to conversion |
| Highest-engagement touch | 20% | Placement with deepest engagement (time on page, pages visited) |

**Rules:**
- Touches expire after 30 days if no conversion occurs
- One miner = one touch per account per campaign (no spam)
- Real-time leaderboard shows active touches and attributed value
- If only one touch exists, it receives 80%

### 4.3 Attribution Conflicts

| Scenario | Resolution |
|----------|------------|
| Two miners claim first touch | Earliest timestamp wins |
| Two miners claim last touch | Most recent conversion event wins |
| Touches < 24 hours apart | Split 50/50, flag for review |
| Miner appeals attribution | Validator reviews timestamp evidence |

---

## 5. Validator Incentive Structure

Validators earn dividends by verifying that content reached the intended audience and scoring miner reasoning quality.

- Validators operate under **Yuma Consensus** (Bittensor's standard validator mechanism)
- Rewards scale with verification accuracy and consistency

---

## 6. Miner Entry

### 6.1 Stake Requirement

- **0.2 TAO** stake required for all miners
- No conversion threshold — anyone can participate

### 6.2 Discovery Bounties

Separate pool for identifying targets (not just converting):

| Activity | Reward | Requirements |
|----------|--------|-------------|
| Identify a new verified competitor user | 0.1 TAO | Company name, domain, competitor used, source URL |
| Find a target company's decision-maker contact | 0.2 TAO | Name, role, LinkedIn/email, company verification |
| Discover a new channel where targets gather | 0.5 TAO | Platform, community URL, member count estimate, relevance justification |
| First to identify emerging competitor (bonus) | 1.0 TAO | New competitor not yet in system, evidence of product/market fit |

**Note:** If discovery bounties are unclaimed in a cycle, they roll back into the main emission pool proportionally.

### 6.3 Sandbox Mode

- New miners practice on test briefs with validator-controlled scenarios
- No stake required in sandbox

---

## 7. Proof of Intelligence Framework

SignalCast qualifies as a Proof of Intelligence subnet by requiring complex, non-algorithmic research.

### 7.1 Why This Qualifies as Proof of Intelligence

| Requirement | SignalCast Implementation |
|-------------|--------------------------|
| **Non-trivial task** | Audience research requires investigation, reasoning, and judgment — cannot be computed from data alone |
| **Verifiable output** | Reasoning traces can be checked against evidence; signal sources must be cited and verified |
| **Resistance to gaming** | Fabricated reasoning fails consistency checks; volume without quality is penalized |
| **Economic alignment** | Rewards scale with targeting accuracy, not placement volume |
| **Skill differentiation** | Miners with better research capabilities consistently outperform |

### 7.2 Intelligence Hierarchy

| Level | Description | Reward |
|-------|-------------|--------|
| Level 1 | Channel access — developing presence in professional communities where target audiences gather | Base reward |
| Level 2 | Strategic matching — connecting assets to verified audiences with coherent reasoning | +20% |
| Level 3 | Signal detection — identifying audience needs and pain points from noisy data | +50% |
| Level 4 | Audience prediction — anticipating which users are ready for alternatives before explicit signals appear | +100% |

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
    "timing_rationale": "Active thread on [topic], high visibility window",
    "channel_selection": "Technical audience, [platform], [reason for fit]"
  }
}
```

### 7.4 Reasoning Quality Scoring

Validators score each submission on 4 dimensions (0-5 scale each):

| Dimension | What It Measures | Scoring Criteria |
|-----------|------------------|------------------|
| **Signal Source Quality** | How credible is the targeting signal? | 0 = no source, 5 = verified first-party data |
| **Audience Identification** | Is the company correctly identified as a target? | 0 = wrong company, 5 = verified domain + role |
| **Relevance Match** | Does the content actually address the identified need? | 0 = irrelevant, 5 = perfect alignment |
| **Channel Selection** | Is this the right platform/context for this audience? | 0 = wrong platform, 5 = optimal fit |

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

- All miners stake 0.2 TAO to participate
- Fraudulent or irrelevant traffic → stake burned
- Reasoning fraud → stake burned + reputation damage

### 8.2 Honey-Link Telemetry

- Validators wrap distributed links in invisible telemetry layers
- Non-human behavior detected → placement disqualified from Tier 1 payout
- Detection triggers:
  - Linear scroll velocity
  - No cursor movement
  - Instant form submission
  - Repeated bot-like patterns

### 8.3 Frequency Caps

- Validators apply saturation limits per account
- If a miner over-exposes a target account, rewards for that account are zeroed

### 8.4 Reasoning Consistency Checks

- Fabricated reasoning fails cross-reference validation
- Validator flags submissions where reasoning doesn't match evidence
- Pattern of low-quality reasoning → reputation penalty

---

## 9. Emission Summary

- **Proportional distribution** based on score weights each cycle
- **Discovery bounties:** 10% of pool (if unclaimed, rolls back into main pool proportionally)
- The big fish multiplier (10x/3x/1x) and conversion multipliers already create natural proportional distribution
