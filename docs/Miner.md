# SignalCast: Miner Architecture & Operations

The SignalCast miner is a decentralized **Audience Research & Distribution Node**. Unlike traditional ad networks that blast content at random audiences, a SignalCast miner must operate as a precision placement agent—identifying which users currently rely on competitor products and placing relevant content where those decision-makers will see it.

---

## Miner Tasks

A SignalCast miner performs a continuous four-stage cycle that requires both computational effort and strategic reasoning:

### 1. Asset Scouting (Creative Intelligence)

* The miner monitors the Subnet 93 (Bitcast) metagraph to identify high-performing creative assets.
* Miners use LLMs to analyze asset transcripts and metadata to determine "Audience Fit" for specific briefs (e.g., matching a technical video about inference costs to developers using legacy providers).

### 2. Audience Research (Targeting)

* Miners research the open web to identify which companies use which tools (via BuiltWith, GitHub repos, job postings, public case studies).
* They identify specific channels where target audiences gather — specialized forums, Discord servers, industry newsletters, and active X.com threads.
* The goal: understand who would genuinely benefit from seeing the advertised content.

### 3. Precision Placement (The Interest Pipeline)

* Miners generate a unique tracking signature and place the SN93 asset where the right audience will see it.
* Miners are incentivized to bridge the gap between content and the people who need it by driving users toward "Lead Magnets" such as Whitepapers, Demos, and API signups.

### 4. Telemetry Maintenance (Verification)

* Miners host a lightweight redirect proxy that captures initial visitor telemetry (IP/User-Agent) before routing to the Bitcast asset or landing page.
* This telemetry is hashed and submitted to validators as a "Proof of Audience" to verify that content reached the intended users.

---

## Strategic Reasoning Requirements

Miners must submit a **reasoning trace** alongside each placement proof. This demonstrates research quality, not just execution.

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

### Reasoning Dimensions (Validator-Scored)

| Dimension | Weight | What Validators Check |
|-----------|--------|----------------------|
| Audience identification | 25% | Is the target verified as a competitor user? Evidence quality? |
| Relevance match | 25% | Does the asset address a real need for this audience? |
| Timing rationale | 25% | Is this a good moment to reach them? |
| Channel selection | 25% | Is the placement context appropriate and high-quality? |

Strong reasoning earns up to **20% bonus** on the placement score.

### Gaming Detection

Weak reasoning signals attempted gaming:

| Red Flag | Interpretation |
|----------|----------------|
| Generic reasoning copied across placements | Template-based, not researched |
| Reasoning doesn't match observable evidence | Fabricated justification |
| Timing rationale contradicts public data | Made up opportunity |
| Target not verifiable as competitor user | False audience claim |

Miners with consistently weak reasoning receive score penalties and eventual stake slashing.

---

## Channel Development

High-value professional communities are where the right audiences gather:

* Industry Slack workspaces
* Private Discord servers
* Specialized forums
* Professional networking groups

Miners who develop and maintain presence in these channels demonstrate ongoing effort that cannot be automated. This is **Level 1** of the Intelligence Hierarchy and forms the foundation for higher-tier rewards.

---

## Discovery Bounties

Miners earn **Discovery Bounties** for mapping previously unknown audience segments:

* Identifying which companies use which competitor tools
* Detecting when a company starts evaluating alternatives
* Finding channels where specific audiences gather

These discoveries are submitted with evidence and verified by validators before becoming available to the network. This is pure research work—no amount of compute can substitute for accurate audience mapping.

---

## Expected Input → Output Format

To maintain interoperability within the Bittensor ecosystem, miners must adhere to a strict I/O protocol.

### Input (From Subnet 93 / Validators)

* `Asset_UID`: The unique identifier of the content on SN93.
* `Target_Account_List (TAL)`: A JSON array of corporate domains whose users would benefit from the content (e.g., `["replicate.com", "runway.com"]`).
* `Conversion_Targets`: Metadata specifying desired actions (e.g., X.com Follows, API Signups, Discord Joins).

### Output (To Validators)

* `Placement_Proof`: A URL or Social Object ID proving where the asset was shared.
* `Telemetry_Bundle`: A hashed packet containing visitor firmographic data and the specific action triggered.
* `Reasoning_Trace`: JSON object documenting audience identification, relevance match, timing rationale, and channel selection.
* `Signal_Identity`: A ZK-proof verifying the humanity and professional context of the interaction.

---

## Performance Dimensions

Miners are scored on a multi-dimensional matrix where **Targeting Accuracy** outweighs raw volume.

### Conversion Depth (The "Quality" Score)

Measured by the miner's ability to move a user down the funnel. An "API Signup" (Bottom-of-funnel) generates significantly higher rewards than a "Like" (Top-of-funnel).

### Targeting Precision (The "Accuracy" Score)

Success is measured by whether the traffic came from the intended audience. Verified competitor users trigger the "Precision Multiplier."

### Response Speed (The "Bounty" Score)

The latency between identifying an audience opportunity and placing content in front of them.

### Reasoning Quality (The "Intelligence" Score)

Validators evaluate the coherence and verifiability of the miner's reasoning trace. Strong reasoning = bonus multiplier. Weak reasoning = penalty.

### Contextual Integrity (The "Reputation" Score)

Validators use sentiment analysis and platform feedback to ensure the miner's placement is professional and brand-safe. High "Spam" reports or low-quality environments result in score degradation and potential slashing.

---

## The Intelligence Hierarchy

Miners are rewarded based on the sophistication of their audience research:

| Level | Capability | Reward Tier |
|-------|------------|-------------|
| **Level 1** | Channel Access — presence in communities where audiences gather | Base |
| **Level 2** | Strategic Matching — connecting assets to verified audiences with reasoning | 2x |
| **Level 3** | Signal Detection — identifying audience needs from noisy data | 5x |
| **Level 4** | Audience Prediction — anticipating who's ready for alternatives before signals appear | 10x |

---
