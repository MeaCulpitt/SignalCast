# SignalCast: Validator Design

---

## 1. Validator Tasks

### 1.1 Audience Verification

- Verify that content reached the intended audience tier
- Cross-reference miner claims with technographic data sources
- Confirm signal source evidence provided by miners

### 1.2 Reasoning Scoring

- Score miner reasoning traces on 4 dimensions (0-5 each)
- Calculate reasoning bonus (0-20%)
- Flag fabricated or weak reasoning

### 1.3 Tier Validation

- Validate miner-claimed tier against evidence
- Confirm tier upgrades or downgrades as needed
- Handle miner appeals with additional evidence review

### 1.4 Anti-Gaming Enforcement

- Monitor honey-link telemetry for non-human behavior
- Apply frequency caps to prevent over-exposure
- Detect and penalize gaming patterns

---

## 2. Scoring and Evaluation Methodology

### 2.1 Reasoning Quality Scoring

Validators score each submission on 4 dimensions (0-5 scale each):

| Dimension | What It Measures | Scoring Criteria |
|-----------|------------------|------------------|
| Signal Source Quality | How credible is the targeting signal? | 0 = no source, 5 = verified first-party data |
| Audience Identification | Is the company correctly identified as a target? | 0 = wrong company, 5 = verified domain + role |
| Relevance Match | Does the content address the identified need? | 0 = irrelevant, 5 = perfect alignment |
| Channel Selection | Is this the right platform for this audience? | 0 = wrong platform, 5 = optimal fit |

### 2.2 Reasoning Bonus Calculation

- Each dimension: 0-5 score
- Total: 0-20 points → 0-20% bonus applied to final score

| Total Score | Reasoning Bonus |
|-------------|------------------|
| 0-4 | 0% |
| 5-8 | 5% |
| 9-12 | 10% |
| 13-16 | 15% |
| 17-20 | 20% |

### 2.3 Tier Verification

#### Tier 1 Verification

- Check self-reported signal (URL, transcript)
- Verify first-party list match
- Confirm company domain and link to need

#### Tier 2 Verification

- Pull technographic data (BuiltWith, Clearbit, GitHub)
- Confirm active/recent usage (< 90 days)
- Verify job postings correlate with product category

#### Tier 3 Verification

- Confirm industry/vertical alignment
- Verify ICP fit (size, role)
- Check community membership if applicable

### 2.4 Score Calculation

```
Final Score = Base (1.0) × Big Fish Multiplier × Conversion Multiplier × Reasoning Bonus
```

---

## 3. Evaluation Cadence

### 3.1 Per-Submission Evaluation

1. Miner submits placement with reasoning trace
2. Validator verifies signal source exists
3. Validator confirms tier claim
4. Validator scores reasoning quality
5. Score calculated and recorded

### 3.2 Cycle Aggregation

1. All miner scores aggregated for the cycle
2. Discovery bounty claims collected
3. Proportional distribution calculated
4. Rewards allocated

### 3.3 Ongoing Monitoring

- Random audit sampling of past verifications
- Pattern detection for gaming behavior
- Reputation tracking for repeat miners

---

## 4. Validator Incentive Alignment

### 4.1 Reward Mechanism

Validators earn dividends by:

- Verifying content reached the intended audience
- Scoring miner reasoning quality accurately
- Validating tier claims correctly

### 4.2 Yuma Consensus

Validators operate under **Bittensor's standard Yuma Consensus**:

- Rewards scale with verification accuracy
- Poor verification impacts consensus weight
- Economic incentive to verify correctly

### 4.3 Alignment with Miners

- Validators benefit from miner success (more submissions = more verification rewards)
- Quality verification encourages high-quality miner participation
- Fair scoring builds trusted ecosystem

---

## 5. Anti-Gaming Mechanisms

### 5.1 Honey-Link Telemetry

- Wrap distributed links in invisible telemetry layers
- Detect non-human behavior patterns:
  - Linear scroll velocity
  - No cursor movement
  - Instant form submission
  - Repeated bot-like patterns
- Disqualify placements with bot detection

### 5.2 Frequency Caps

- Apply saturation limits per account
- Zero rewards for over-exposed accounts
- Prevent advertiser brand damage from spam

### 5.3 Reasoning Consistency Checks

- Cross-reference reasoning with observable evidence
- Flag fabricated justifications
- Pattern of weak reasoning → reputation penalty

### 5.4 Fraud Detection

| Trigger | Action |
|---------|--------|
| Fake traffic / bot clicks | Placement disqualified, stake warning |
| Fabricated reasoning | Stake penalty, reputation damage |
| False tier claims | Downgrade tier, score penalty |
| Repeated violations | Stake slash, potential removal |

---

## 6. Input/Output Format

### 6.1 Input (From Network)

| Field | Description |
|-------|-------------|
| `Miner_Submission` | Placement proof, telemetry bundle, reasoning trace |
| `Claimed_Tier` | Miner-claimed tier (1, 2, or 3) |
| `Brief_Parameters` | Original campaign targets and goals |

### 6.2 Output (To Network)

| Field | Description |
|-------|-------------|
| `Verified_Tier` | Confirmed tier after validation |
| `Reasoning_Score` | 0-20 points |
| `Reasoning_Bonus` | 0-20% |
| `Final_Score` | Calculated score |
| `Validation_Status` | Approved / Downgraded / Disqualified |
