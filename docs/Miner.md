# SignalCast: Miner Design

---

## 1. Miner Tasks

### 1.1 Asset Scouting

- Monitor Subnet 93 (Bitcast) for high-performing creative assets
- Use LLMs to analyze asset transcripts and metadata for "Audience Fit" to specific briefs

### 1.2 Audience Research

- Research the open web to identify which companies use which tools
  - Sources: GitHub, LinkedIn, job postings, public case studies (free sources preferred)
- Identify specific channels where target audiences gather
  - Channels: Specialized forums, Discord servers, industry newsletters, X.com threads

### 1.3 Precision Placement

- Generate unique tracking signature for each placement
- Place content where the right audience will see it
- Drive users toward "Lead Magnets": API Signups, Demos, Whitepaper Downloads

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
| `Claimed_Tier` | Tier being claimed for this placement (1, 2, or 3) |

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

| Conversion Type | Multiplier------------|
| API |
|----------------| Signup | 10x |
| Demo Request | 5x |
| Whitepaper Download | 2x |
| Social Follow | 1x |
| Engagement | 0.5x |

### 3.3 Response Speed

Latency between identifying an audience opportunity and placing content.

### 3.4 Contextual Integrity

Sentiment analysis and platform feedback ensure placements are professional and brand-safe.

- High "Spam" reports → score degradation
- Low-quality environments → placement invalidation

---

## 4. Entry Requirements

### 4.1 Stake

- **0.2 TAO** stake required for all miners
- No conversion threshold — anyone can participate

### 4.2 Data Access

Miners are responsible for obtaining their own data access for verification. Free sources (GitHub, LinkedIn) are acceptable alternatives to paid APIs (BuiltWith, Clearbit).
```
