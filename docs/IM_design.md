# SignalCast: Incentive & Mechanism Design

---

## 1. Emission and Reward Logic

### Score Calculation

```
Score = Base (1.0) × Tier Multiplier × Conversion Multiplier
```

- **Base:** 1.0 per valid placement submission
- **Tier Multiplier:** Based on audience relevance (10x, 3x, 1x)
- **Conversion Multiplier:** Based on conversion depth (0.5x-10x)

### Tier Multipliers (Audience Relevance)

| Tier | Audience | Multiplier |
|------|----------|------------|
| Tier 1 | Verified competitor users | 10x |
| Tier 2 | High-fit industry targets | 3x |
| Tier 3 | General relevant audience | 1x |

#### Tier 1: Verified Competitor Users (10x)

**Verification Methods:**
- **Self-reported need:** User explicitly stated a need or pain point (e.g., "Looking for Replicate alternatives")
  - Source: Social media, forums, support tickets, review sites
- **First-party list match:** Advertiser provided company on their target list

**Required Evidence:**
- URL or transcript of self-reported need
- Company name and verified domain

#### Tier 2: High-Fit Industry Targets (3x)

**Verification Methods:**
- **Technographic data:** Evidence company uses competitor product
  - Source: BuiltWith, Clearbit, GitHub (imports, dependencies), StackShare
- **Job postings:** Company hiring ML/DevOps roles indicating scale

**Required Evidence:**
- Data source URL or API response showing product usage
- Timestamp within last 90 days
- Company verification (domain matches)

**Note:** Miners are responsible for obtaining their own data access for verification. Free sources (GitHub, LinkedIn) are acceptable alternatives to paid APIs.

#### Tier 3: General Relevant Audience (1x)

**Verification Methods:**
- **Contextual match:** Company in same industry/vertical, fits ICP
- **Community membership:** Active in relevant communities

### Conversion Multipliers

| Conversion Type | Multiplier |
|----------------|------------|
| API Signup | 10x |
| Demo Request | 5x |
| Whitepaper Download | 2x |
| Social Follow | 1x |
| Engagement | 0.5x |

### Distribution

- **80%** to miners
- **20%** to validators
- **90%** of pool: Distributes proportionally based on score weights each cycle
- **10%** of pool: Discovery bounties (if unclaimed, rolls back into main pool)

**Example:**

| Miner | Tier | Conversion | Score |
|-------|------|------------|-------|
| A | Tier 1 | API Signup | 100 |
| B | Tier 2 | Demo Request | 15 |
| C | Tier 3 | Engagement | 0.5 |

**Total:** 115.5 | **Miner A:** 87% | **Miner B:** 13% | **Miner C:** <1%

### Emission Pool Sources

| Source | Description |
|--------|-------------|
| Protocol emissions | Bittensor network emissions (per subnet allocation) |
| Advertiser revenue | Success fees converted to TAO from stablecoins/fiat |

All advertiser revenue is swapped to TAO via oracle and flows directly to miners and validators (80/20 split).

---

## 2. Incentive Alignment for Miners and Validators

### Miner Incentives

Miners earn TAO by:
- Identifying verified competitor users and placing content
- Driving deeper conversions (API signups > demos > downloads > follows > engagement)
- Discovering new targets, channels, and competitors (discovery bounties)

Each conversion maps to one miner — no complex multi-miner attribution.

### Validator Incentives

Validators earn dividends through Bittensor's Yuma Consensus based on their stake weight in the subnet. Verification work is part of the standard validator role.

### Alignment Mechanisms

- **Proportional distribution:** Rewards directly correlate with targeting quality and conversion depth
- **Discovery bounties:** Incentivizes research even before conversions occur
- **Simple one-to-one model:** Each verified conversion maps to one miner
- **Tiered rewards:** Higher tiers (verified competitor users) earn 10x base — rewards accuracy over volume

### Tie-Breaking

When multiple miners target the same account:
1. Validator verifies all competing placements
2. Miner with highest conversion depth wins
3. If same depth, first submission wins (timestamp-based)

---

## 3. Mechanisms to Discourage Low-Quality or Adversarial Behavior

### Stake-at-Risk

- All miners stake **0.2 TAO** to participate
- Fraudulent or irrelevant traffic → stake burned

### Honey-Link Telemetry

- Validators wrap distributed links in invisible telemetry
- Non-human behavior detected → placement disqualified
- Detection triggers:
  - Linear scroll velocity
  - No cursor movement
  - Instant form submission
  - Bot-like patterns

### Frequency Caps

- Validators apply saturation limits per account
- Over-exposing a target → rewards zeroed for that account

### Gaming Detection

| Red Flag | Interpretation |
|----------|----------------|
| Generic reasoning copied across placements | Template-based, not researched |
| Reasoning doesn't match observable evidence | Fabricated justification |
| Target not verifiable as competitor user | False audience claim |

### Verification Flow

1. Miner submits placement with claimed tier
2. Validator verifies signal source exists
3. Tier confirmed or downgraded

---

## 4. How This Design Qualifies as "Proof of Intelligence" or "Proof of Effort"

### Why This Qualifies

| Requirement | Implementation |
|-------------|----------------|
| Non-trivial task | Audience research requires investigation, judgment, and strategic thinking — cannot be computed from data alone |
| Verifiable output | Evidence traces can be checked against observable sources |
| Resistance to gaming | Honey-link telemetry, frequency caps |
| Economic alignment | Rewards scale with targeting accuracy, not placement volume |
| Skill differentiation | Miners with better research consistently outperform |

### Intelligence Hierarchy

| Level | Description | Reward |
|-------|-------------|--------|
| Level 1 | Channel access — presence in professional communities | Base (Tier 3) |
| Level 2 | Strategic matching — asset to verified audience | Tier 1-2 |
| Level 3 | Signal detection — identify needs from noisy data | Tier 1 only |
| Level 4 | Audience prediction — anticipate readiness before explicit signals | Tier 1 |

Higher levels require deeper research and judgment. Miners who invest in understanding their targets earn proportionally more.

### Proof of Effort

Even at Level 1, miners must:
- Identify relevant communities and channels
- Research target audience profiles
- Select appropriate content for the audience
- Document evidence for verification

This requires genuine effort beyond automated scraping or random placement.

---

## 5. High-Level Algorithm

### Task Assignment

1. Advertiser creates brief (target audience, content, conversion goals)
2. Brief broadcast to all miners
3. Miners select briefs based on difficulty and reward potential

### Submission

1. Miner researches target audience
2. Miner places content with tracked link
3. Miner submits evidence and tier claim

### Validation

1. Validator verifies signal source exists
2. Validator confirms tier (1/2/3)
3. Validator confirms conversion depth

### Scoring

1. Calculate score: Base × Tier × Conversion
2. Aggregate all scores for cycle
3. Apply tie-breaking rules if multiple miners target same account

### Reward Allocation

1. 80% of pool distributes to miners proportionally by score
2. 20% of pool goes to validators
3. 90% of miner share distributes by score weight
4. 10% of miner share for discovery bounties (if unclaimed, rolls back to main pool)

---

## Appendix: Cold-Start Strategy

### Seed Data

To solve the cold-start loop:

1. **Public target lists:** Seed with companies identified from public data
   - GitHub analysis (companies using specific repos)
   - Job postings (companies hiring ML/DevOps at scale)
   - Community directories

2. **Miner-proposed targets:** Miners can propose target lists
   - Advertisers review and approve
   - Approved targets become eligible for Tier 1 rewards

### Phased Launch

| Phase | Description |
|-------|-------------|
| Phase 0 | Closed beta with 5-10 anchor advertisers |
| Phase 1 | Public miner registration, seed data active |
| Phase 2 | Open advertiser onboarding |
| Phase 3 | Full emission schedule, market dynamics take over |
```
