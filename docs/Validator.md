# SignalCast: Validator Design

---

## 1. Validator Tasks

### 1.1 Audience Verification

- Verify that content reached the intended audience tier
- Cross-reference miner claims with data sources (GitHub, LinkedIn, public data)
- Confirm signal source evidence provided by miners

### 1.2 Tier Validation

- Validate miner-claimed tier against evidence
- Confirm tier upgrades or downgrades as needed

### 1.3 Conversion Verification

- Confirm conversion depth achieved (API signup, demo, download, follow, engagement)
- miner's placed content
- Detect and Verify conversion came from reject fraudulent conversions

### 1.4 Anti-Gaming Enforcement

- Monitor honey-link telemetry for non-human behavior
- Apply frequency caps to prevent over-exposure
- Detect and penalize gaming patterns

---

## 2. Scoring and Evaluation Methodology

### 2.1 Tier Verification

#### Tier 1: Verified Competitor Users (10x)

- Check self-reported signal (URL, transcript)
- Verify first-party list match
- Confirm company domain and link to need

#### Tier 2: High-Fit Industry Targets (3x)

- Pull technographic data (GitHub, LinkedIn, public sources)
- Confirm active/recent usage (< 90 days)
- Verify job postings correlate with product category

#### Tier 3: General Relevant Audience (1x)

- Confirm industry/vertical alignment
- Verify ICP fit (size, role)
- Check community membership if applicable

### 2.2 Conversion Verification

| Conversion Type | Multiplier | Verification |
|----------------|------------|--------------|
| API Signup | 10x | Account created, verified domain |
| Demo Request | 5x | Form submitted, valid email |
| Whitepaper Download | 2x | Download confirmed |
| Social Follow | 1x | Account followed |
| Engagement | 0.5x | Click/time on page |

### 2.3 Score Calculation

```
Score = Base (1.0) × Tier Multiplier × Conversion Multiplier
```

---

## 3. Evaluation Cadence

### 3.1 Per-Submission Evaluation

1. Miner submits placement with claimed tier
2. Validator verifies signal source exists
3. Validator confirms tier claim
4. Validator confirms conversion depth
5. Score calculated and recorded

### 3.2 Cycle Aggregation

1. All miner scores aggregated for the cycle
2. Proportional distribution calculated
3. Rewards allocated (80% miners, 20% validators)

### 3.3 Ongoing Monitoring

- Random audit sampling of past verifications
- Pattern detection for gaming behavior
- Reputation tracking for repeat miners

---

## 4. Validator Incentive Alignment

### 4.1 Reward Mechanism

Validators earn 20% of the emission pool by:

- Verifying content reached the intended audience
- Validating tier claims correctly
- Confirming conversion depth accurately

### 4.2 Yuma Consensus

Validators operate under **Bittensor's standard Yuma Consensus**:

- Rewards scale with stake weight in subnet
- Verification work is part of the standard validator role
- Economic incentive to verify correctly

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

### 5.3 Gaming Detection

| Trigger | Action |
|---------|--------|
| Fake traffic / bot clicks | Placement disqualified, stake warning |
| False tier claims | Downgrade tier, score penalty |
| Repeated violations | Stake slash, potential removal |

---

## 6. Input/Output Format

### 6.1 Input (From Network)

| Field | Description |
|-------|-------------|
| `Miner_Submission` | Placement proof, telemetry bundle |
| `Claimed_Tier` | Miner-claimed tier (1, 2, or 3) |
| `Brief_Parameters` | Original campaign targets and goals |

### 6.2 Output (To Network)

| Field | Description |
|-------|-------------|
| `Verified_Tier` | Confirmed tier after validation |
| `Conversion_Depth` | Confirmed conversion type |
| `Final_Score` | Calculated score |
| `Validation_Status` | Approved / Downgraded / Disqualified |
```
