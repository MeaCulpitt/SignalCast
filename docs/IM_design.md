# SignalCast: Incentive & Mechanism Design

---

## 1. Emission and Reward Logic

### 1.1 Score Calculation

```
Score = Base (1.0) × Big Fish Multiplier × Conversion Multiplier × Reasoning Bonus
```

- **Base:** 1.0 per placement submission
- **Big Fish Multiplier:** Tier-based (10x, 3x, 1x)
- **Conversion Multiplier:** Based on conversion depth (1x-10x)
- **Reasoning Bonus:** 0-20% based on validator-scored reasoning quality

### 1.2 Big Fish Multiplier (Audience Relevance)

| Tier | Audience | Multiplier |
|------|----------|------------|
| Tier 1 | Verified competitor users (self-reported need or first-party list match) | 10x |
| Tier 2 | High-fit industry targets (technographic match, confirmed competitor usage) | 3x |
| Tier 3 | General relevant audience (same industry/ICP, unconfirmed) | 1x |

### 1.3 Conversion Multipliers

| Conversion Type | Multiplier |
|----------------|------------|
| API Signup | 10x |
| Demo Request | 5x |
| Whitepaper Download | 2x |
| Social Follow | 2x |
| Engagement | 1x |

### 1.4 Tier Determination

#### Tier 1: Verified Competitor Users (10x)

**Verification Methods:**
- **Self-reported need:** User explicitly stated a need or pain point (e.g., "Looking for Replicate alternatives")
  - Source: Social media, forums, support tickets, review sites
  - Must include company identification and specific need expressed
- **First-party list match:** Advertiser provided company on their target list
  - Source: Advertiser-uploaded account list

**Required Evidence:**
- URL or transcript of self-reported need
- Company name and verified domain
- Clear link between stated need and advertised solution

#### Tier 2: High-Fit Industry Targets (3x)

**Verification Methods:**
- **Technographic data:** Evidence company uses competitor product
  - Source: BuiltWith, Clearbit, GitHub (imports, dependencies), StackShare
  - Must show active/recent usage (not abandoned projects)
- **Job postings:** Company hiring ML/DevOps roles indicating scale

**Required Evidence:**
- Data source URL or API response showing product usage
- Timestamp within last 90 days
- Company verification (domain matches)

#### Tier 3: General Relevant Audience (1x)

**Verification Methods:**
- **Contextual match:** Company in same industry/vertical, fits ICP (size, role)
  - Source: Company website, LinkedIn, Crunchbase
- **Community membership:** Active in relevant communities (Discord, Slack, forums)

**Required Evidence:**
- Company profile showing industry/vertical alignment
- ICP fit justification (size, role)
- No direct competitor usage confirmed

### 1.5 Verification Flow

1. Miner submits placement with claimed tier
2. Validator verifies signal source exists
3. Tier confirmed or downgraded
4. Miner can appeal with additional evidence

### 1.6 Proportional Distribution

- **90%** of pool: Distributes proportionally based on score weights each cycle
- **10%** of pool: Discovery bounties (distributes proportionally to discovery claims; if unclaimed, rolls back into main pool)

**Example:**

| Miner | Tier | Conversion | Reasoning | Score |
|-------|------|------------|-----------|-------|
| A | Tier 1 | API Signup | 10% | 110 |
| B | Tier 2 | Demo Request | 0% | 15 |
| C | Tier 3 | Engagement | 0% | 1 |

**Total:** 126 | **Miner A:** 87% | **Miner B:** 12% | **Miner C:** 1%

Miner A receives 87% of the pool based on their proportionally higher score.

---

## 2. Incentive Alignment for Miners and Validators

### 2.1 Miner Incentives

Miners earn TAO by:

- Identifying verified competitor users and placing content
- Driving deeper conversions (API signups > demos > downloads > follows > engagement)
- Submitting high-quality reasoning traces (0-20% bonus)
- Discovering new targets, channels, and competitors (discovery bounties)

### 2.2 Validator Incentives

Validators earn dividends by:

- Verifying content reached the intended audience
- Scoring miner reasoning quality
- Validating tier claims (Tier 1/2/3)

Validators operate under **Yuma Consensus** (Bittensor's standard validator mechanism).

### 2.3 Alignment Mechanisms

- **Proportional distribution:** Miners with higher scores receive proportionally more — rewards directly correlate with quality
- **Discovery bounties:** Incentivizes research even before conversions
- **Reasoning bonus:** Rewards thoughtful research over volume
- **Journey-weighted scoring:** Incentivizes long-term relationship building, not just single-touch conversions

---

## 3. Mechanisms to Discourage Low-Quality or Adversarial Behavior

### 3.1 Stake-at-Risk

- All miners stake **0.2 TAO** to participate
- Fraudulent or irrelevant traffic → stake burned
- Reasoning fraud → stake burned + reputation damage

### 3.2 Honey-Link Telemetry

- Validators wrap distributed links in invisible telemetry
- Non-human behavior detected → placement disqualified
- Detection triggers:
  - Linear scroll velocity
  - No cursor movement
  - Instant form submission
  - Bot-like patterns

### 3.3 Frequency Caps

- Validators apply saturation limits per account
- Over-exposing a target → rewards zeroed for that account

### 3.4 Reasoning Consistency Checks

- Fabricated reasoning fails cross-reference validation
- Pattern of low-quality reasoning → reputation penalty

### 3.5 Gaming Detection

| Red Flag | Interpretation |
|----------|----------------|
| Generic reasoning copied across placements | Template-based, not researched |
| Reasoning doesn't match observable evidence | Fabricated justification |
| Target not verifiable as competitor user | False audience claim |

---

## 4. How This Design Qualifies as Proof of Intelligence

### 4.1 Why This Qualifies

| Requirement | Implementation |
|-------------|----------------|
| Non-trivial task | Audience research requires investigation, reasoning, judgment — cannot be computed from data alone |
| Verifiable output | Reasoning traces can be checked against evidence |
| Resistance to gaming | Fabricated reasoning fails consistency checks; volume without quality is penalized |
| Economic alignment | Rewards scale with targeting accuracy, not placement volume |
| Skill differentiation | Miners with better research consistently outperform |

### 4.2 Intelligence Hierarchy

| Level | Description | Reward |
|-------|-------------|--------|
| Level 1 | Channel access — presence in professional communities | Base |
| Level 2 | Strategic matching — asset to verified audience with reasoning | +20% |
| Level 3 | Signal detection — identify needs from noisy data | +50% |
| Level 4 | Audience prediction — anticipate readiness before explicit signals | +100% |

### 4.3 Reasoning Quality Scoring

Validators score each submission on 4 dimensions (0-5 scale each):

| Dimension | What It Measures | Scoring Criteria |
|-----------|------------------|------------------|
| Signal Source Quality | How credible is the targeting signal? | 0 = no source, 5 = verified first-party data |
| Audience Identification | Is the company correctly identified as a target? | 0 = wrong company, 5 = verified domain + role |
| Relevance Match | Does the content address the identified need? | 0 = irrelevant, 5 = perfect alignment |
| Channel Selection | Is this the right platform for this audience? | 0 = wrong platform, 5 = optimal fit |

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

## 5. High-Level Algorithm

### 5.1 Task Assignment

1. Advertiser creates brief (target audience, content, conversion goals)
2. Brief broadcast to all miners
3. Miners select briefs based on difficulty, competition, reward potential

### 5.2 Submission

1. Miner researches target audience
2. Miner places content with tracked link
3. Miner submits reasoning trace and placement proof

### 5.3 Validation

1. Validator verifies signal source exists
2. Validator confirms tier (1/2/3)
3. Validator scores reasoning quality (0-20%)

### 5.4 Scoring

1. Calculate score: Base × Big Fish × Conversion × Reasoning
2. Aggregate all scores for cycle
3. Distribute pool proportionally

### 5.5 Reward Allocation

1. 90% pool distributes proportionally by score weight
2. 10% pool for discovery bounties
3. Unclaimed discovery rolls back to main pool

### 5.6 Brief Structure

Each campaign brief contains:

| Field | Description |
|-------|-------------|
| Advertiser | Project/subnet seeking distribution |
| Target Audience | Tier definition (competitor users, industry, ICP) |
| Content Asset | SN93 video, whitepaper, landing page |
| Conversion Goals | What counts as conversion |
| Success Fee | TAO paid by advertiser per verified conversion |
| Emitter Reward | TAO distributed to miner from protocol emissions |

---

## 6. Journey-Weighted Scoring

### 6.1 Time-Weighted Multipliers

| Journey Length | Multiplier | Rationale |
|----------------|------------|-----------|
| Single touchpoint | 1x | Base conversion value |
| 2-3 touchpoints over 14 days | 1.5x | Demonstrated follow-through |
| 4+ touchpoints over 30 days | 2x | Full nurture sequence |
| Multi-stakeholder engagement | 3x | Account penetration |

### 6.2 Attribution Model (40/40/20)

When multiple miners touch the same account:

| Touch | Reward Share |
|-------|---------------|
| First touch (awareness) | 40% |
| Last touch (conversion) | 40% |
| Highest-engagement touch | 20% |

**Rules:**
- Touches expire after 30 days if no conversion
- One miner = one touch per account per campaign
- If only one touch exists, it receives 80%

### 6.3 Attribution Conflicts

| Scenario | Resolution |
|----------|------------|
| Two miners claim first touch | Earliest timestamp wins |
| Two miners claim last touch | Most recent conversion event wins |
| Touches < 24 hours apart | Split 50/50, flag for review |

---

## 7. Emission Summary

- **90%** of pool: Distributes proportionally based on score weights
- **10%** of pool: Discovery bounties (if unclaimed, rolls back into main pool)
