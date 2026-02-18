# SignalCast: Miner Design

---

## 1. Miner Tasks

### 1.1 Asset Scouting

- Monitor Subnet 93 (Bitcast) for high-performing creative assets
- Use LLMs to analyze asset transcripts and metadata for "Audience Fit" to specific briefs

### 1.2 Audience Research

- Research the open web to identify which companies use which tools
  - Sources: BuiltWith, Clearbit, GitHub repos, job postings, public case studies
- Identify specific channels where target audiences gather
  - Channels: Specialized forums, Discord servers, industry newsletters, X.com threads

### 1.3 Precision Placement

- Generate unique tracking signature for each placement
- Place content where the right audience will see it
- Drive users toward "Lead Magnets": Whitepapers, Demos, API Signups

### 1.4 Telemetry Maintenance

- Host lightweight redirect proxy capturing initial visitor telemetry (IP, User-Agent)
- Hash and submit telemetry to validators as "Proof of Audience"

---

## 2. Expected Input → Output Format

### 2.1 Input (From Validators)

| Field | Description |
|-------|-------------|
| `Brief` | Campaign parameters (target audience, content, conversion goals) |
| `Target_Account_List` | Optional list of specific companies to target |
| `Conversion_Targets` | Desired actions (API signups, demos, downloads, follows) |

### 2.2 Output (To Validators)

| Field | Description |
|-------|-------------|
| `Placement_Proof` | URL proving where content was shared |
| `Telemetry_Bundle` | Hashed visitor firmographic data |
| `Reasoning_Trace` | JSON documenting research and targeting rationale |
| `Claimed_Tier` | Tier being claimed for this placement (1, 2, or 3) |

### 2.3 Reasoning Trace Format

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
    "channel_selection": "Technical audience, [platform], [reason]"
  }
}
```

---

## 3. Performance Dimensions

### 3.1 Targeting Accuracy

Measured by whether traffic came from the intended audience tier.

| Tier | Description | Multiplier |
|------|-------------|------------|
| Tier 1 | Verified competitor users | 10x |
| Tier 2 | High-fit industry targets | 3x |
| Tier 3 | General relevant audience | 1x |

### 3.2 Conversion Depth

Measured by ability to move users down the funnel.

| Conversion Type | Multiplier |
|----------------|------------|
| API Signup | 10x |
| Demo Request | 5x |
| Whitepaper Download | 2x |
| Social Follow | 2x |
| Engagement | 1x |

### 3.3 Reasoning Quality

Validators evaluate the coherence and verifiability of the miner's reasoning trace.

- Strong reasoning = 0-20% bonus
- Weak reasoning = penalty

### 3.4 Response Speed

Latency between identifying an audience opportunity and placing content.

### 3.5 Contextual Integrity

Sentiment analysis and platform feedback ensure placements are professional and brand-safe.

- High "Spam" reports → score degradation
- Low-quality environments → placement invalidation

---

## 4. Entry Requirements

### 4.1 Stake

- **0.2 TAO** stake required for all miners
- No conversion threshold — anyone can participate

### 4.2 Sandbox Mode

- New miners practice on test briefs with validator-controlled scenarios
- No stake required in sandbox
- Builds "practice reputation" before real participation

---

## 5. Discovery Bounties

10% of the emission pool is allocated for discovery bounties each cycle.

### 5.1 Discovery Activities

| Activity | Requirements |
|----------|-------------|
| Identify a new verified competitor user | Company name, domain, competitor used, source URL |
| Find a target company's decision-maker contact | Name, role, LinkedIn/email, company verification |
| Discover a new channel where targets gather | Platform, community URL, member count, relevance |
| First to identify emerging competitor | New competitor, evidence of product/market fit |

### 5.2 Distribution

- Claims are weighted proportionally within the 10% pool
- If pool is unclaimed, it rolls back into the main pool proportionally

---

## 6. The Intelligence Hierarchy

Miners are rewarded based on research sophistication.

| Level | Capability | Reward |
|-------|------------|--------|
| Level 1 | Channel Access — presence in communities where audiences gather | Base |
| Level 2 | Strategic Matching — connecting assets to verified audiences | +20% |
| Level 3 | Signal Detection — identifying needs from noisy data | +50% |
| Level 4 | Audience Prediction — anticipating readiness before signals | +100% |# SignalCast: Miner Design

---

## 1. Miner Tasks

### 1.1 Asset Scouting

- Monitor Subnet 93 (Bitcast) for high-performing creative assets
- Use LLMs to analyze asset transcripts and metadata for "Audience Fit" to specific briefs

### 1.2 Audience Research

- Research the open web to identify which companies use which tools
  - Sources: BuiltWith, Clearbit, GitHub repos, job postings, public case studies
- Identify specific channels where target audiences gather
  - Channels: Specialized forums, Discord servers, industry newsletters, X.com threads

### 1.3 Precision Placement

- Generate unique tracking signature for each placement
- Place content where the right audience will see it
- Drive users toward "Lead Magnets": Whitepapers, Demos, API Signups

### 1.4 Telemetry Maintenance

- Host lightweight redirect proxy capturing initial visitor telemetry (IP, User-Agent)
- Hash and submit telemetry to validators as "Proof of Audience"

---

## 2. Expected Input → Output Format

### 2.1 Input (From Validators)

| Field | Description |
|-------|-------------|
| `Brief` | Campaign parameters (target audience, content, conversion goals) |
| `Target_Account_List` | Optional list of specific companies to target |
| `Conversion_Targets` | Desired actions (API signups, demos, downloads, follows) |

### 2.2 Output (To Validators)

| Field | Description |
|-------|-------------|
| `Placement_Proof` | URL proving where content was shared |
| `Telemetry_Bundle` | Hashed visitor firmographic data |
| `Reasoning_Trace` | JSON documenting research and targeting rationale |
| `Claimed_Tier` | Tier being claimed for this placement (1, 2, or 3) |

### 2.3 Reasoning Trace Format

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
    "channel_selection": "Technical audience, [platform], [reason]"
  }
}
```

---

## 3. Performance Dimensions

### 3.1 Targeting Accuracy

Measured by whether traffic came from the intended audience tier.

| Tier | Description | Multiplier |
|------|-------------|------------|
| Tier 1 | Verified competitor users | 10x |
| Tier 2 | High-fit industry targets | 3x |
| Tier 3 | General relevant audience | 1x |

### 3.2 Conversion Depth

Measured by ability to move users down the funnel.

| Conversion Type | Multiplier |
|----------------|------------|
| API Signup | 10x |
| Demo Request | 5x |
| Whitepaper Download | 2x |
| Social Follow | 2x |
| Engagement | 1x |

### 3.3 Reasoning Quality

Validators evaluate the coherence and verifiability of the miner's reasoning trace.

- Strong reasoning = 0-20% bonus
- Weak reasoning = penalty

### 3.4 Response Speed

Latency between identifying an audience opportunity and placing content.

### 3.5 Contextual Integrity

Sentiment analysis and platform feedback ensure placements are professional and brand-safe.

- High "Spam" reports → score degradation
- Low-quality environments → placement invalidation

---

## 4. Entry Requirements

### 4.1 Stake

- **0.2 TAO** stake required for all miners
- No conversion threshold — anyone can participate

### 4.2 Sandbox Mode

- New miners practice on test briefs with validator-controlled scenarios
- No stake required in sandbox
- Builds "practice reputation" before real participation

---

## 5. Discovery Bounties

10% of the emission pool is allocated for discovery bounties each cycle.

### 5.1 Discovery Activities

| Activity | Requirements |
|----------|-------------|
| Identify a new verified competitor user | Company name, domain, competitor used, source URL |
| Find a target company's decision-maker contact | Name, role, LinkedIn/email, company verification |
| Discover a new channel where targets gather | Platform, community URL, member count, relevance |
| First to identify emerging competitor | New competitor, evidence of product/market fit |

### 5.2 Distribution

- Claims are weighted proportionally within the 10% pool
- If pool is unclaimed, it rolls back into the main pool proportionally

---

## 6. The Intelligence Hierarchy

Miners are rewarded based on research sophistication.

| Level | Capability | Reward |
|-------|------------|--------|
| Level 1 | Channel Access — presence in communities where audiences gather | Base |
| Level 2 | Strategic Matching — connecting assets to verified audiences | +20% |
| Level 3 | Signal Detection — identifying needs from noisy data | +50% |
| Level 4 | Audience Prediction — anticipating readiness before signals | +100% |
