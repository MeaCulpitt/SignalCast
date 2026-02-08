# SignalCast: Miner Architecture & Operations

The SignalCast miner is a decentralized **Market Intelligence & Distribution Node**. Unlike traditional "click-farms," a SignalCast miner must operate as an autonomous A&R (Artists and Repertoire) agent—identifying the highest-quality assets from Subnet 93 and matching them to high-intent "Pulse Zones" where competitor employees and their customers reside.

---

## Miner Tasks

A SignalCast miner performs a continuous four-stage cycle that requires both computational effort and strategic semantic reasoning:

### 1. Asset Scouting (Creative Intelligence)

* The miner monitors the Subnet 93 (Bitcast) metagraph to identify high-performing creative assets.
* Miners use LLMs to analyze asset transcripts and metadata to determine "Market Fit" for specific industrial briefs and lead magnets (e.g., matching a technical video to a specific whitepaper).

### 2. Technographic Reconnaissance (Targeting)

* Miners scan the open web for "Market Ruptures" (e.g., a company removing a competitor's script, detecting legacy software versions, or identifying relevant job openings).
* They identify specific, gated B2B environments (specialized forums, Discord servers, industry-specific newsletters) and high-authority X.com threads where target accounts are active.

### 3. Precision Placement (The Interest Pipeline)

* Miners generate a unique tracking signature and "push" the SN93 asset into the identified zone.
* Miners are incentivized to bridge the gap between social awareness and industrial intent by driving users toward "Lead Magnets" such as Whitepapers, Demos, and Contact Forms.

### 4. Telemetry Maintenance (Verification)

* Miners host a lightweight redirect proxy that captures initial visitor telemetry (IP/User-Agent) before routing to the Bitcast asset or landing page.
* This telemetry is hashed and submitted to validators as a "Proof of Human Signal" to verify the firmographic origin of the lead.

---

## Strategic Reasoning Requirements

Miners must submit a **reasoning trace** alongside each placement proof. This demonstrates intelligence, not just execution.

```json
{
  "placement_proof": "https://news.ycombinator.com/item?id=...",
  "telemetry_bundle": "hash:0x7a3f...",
  "reasoning": {
    "target_identification": "VoiceFlow identified as Replicate customer via GitHub repo imports",
    "pain_point_match": "Asset addresses cold start latency; CTO tweet mentions this exact issue",
    "timing_rationale": "Active HN thread on inference costs; high visibility window",
    "channel_selection": "Technical audience, high-authority context, CTO known to be active"
  }
}
```

### Reasoning Dimensions (Validator-Scored)

| Dimension | Weight | What Validators Check |
|-----------|--------|----------------------|
| Target identification | 25% | Is the customer relationship verified? Evidence quality? |
| Pain point match | 25% | Does the asset address the stated pain point? |
| Timing rationale | 25% | Is there a credible decision window? |
| Channel selection | 25% | Is the placement context appropriate and high-authority? |

Strong reasoning earns up to **20% bonus** on the placement score.

### Gaming Detection

Weak reasoning signals attempted gaming:

| Red Flag | Interpretation |
|----------|----------------|
| Generic reasoning copied across placements | Template-based, not strategic |
| Reasoning doesn't match observable evidence | Fabricated justification |
| Timing rationale contradicts public data | Made up decision window |
| Target not verifiable in technographic registry | False customer claim |

Miners with consistently weak reasoning receive score penalties and eventual stake slashing.

---

## Channel Development

High-value professional communities are gated and require earned access:

* Industry Slack workspaces
* Private Discord servers
* Invite-only forums
* Executive networking groups

Miners who develop and maintain access to these "Pulse Zones" demonstrate ongoing effort and relationship-building that cannot be automated. This is **Level 1** of the Intelligence Hierarchy and forms the foundation for higher-tier rewards.

---

## Discovery Bounties

Miners earn **Discovery Bounties** for identifying previously unknown competitive intelligence:

* Mapping a competitor's customer base
* Detecting a technographic shift (e.g., customer removing competitor's script)
* Identifying decision-maker social activity patterns

These discoveries are submitted with evidence and verified by validators before becoming available to the network. This is pure intelligence work—no amount of compute can substitute for accurate competitive mapping.

---

## Expected Input → Output Format

To maintain interoperability within the Bittensor ecosystem, miners must adhere to a strict I/O protocol.

### Input (From Subnet 93 / Validators)

* `Asset_UID`: The unique identifier of the content on SN93.
* `Target_Account_List (TAL)`: A JSON array of corporate domains (e.g., `["replicate.com", "runway.com"]`).
* `Conversion_Targets`: Metadata specifying required actions (e.g., X.com Follows, API Signups, Discord Joins).

### Output (To Validators)

* `Placement_Proof`: A URL or Social Object ID proving where the asset was shared.
* `Telemetry_Bundle`: A hashed packet containing the visitor's Firmographic data and the specific "Interest Signal" triggered.
* `Reasoning_Trace`: JSON object documenting target identification, pain point match, timing rationale, and channel selection.
* `Signal_Identity`: A ZK-proof verifying the humanity and professional context of the interaction.

---

## Performance Dimensions

Miners are scored on a multi-dimensional matrix where **Strategic Accuracy** outweighs raw volume.

### Conversion Depth (The "Quality" Score)

Measured by the miner's ability to move a user down the funnel. A "Demo Signup" (Bottom-of-funnel) generates significantly higher rewards than a "Like" (Top-of-funnel).

### Targeting Precision (The "Sniper" Score)

Success is measured by the **Domain Authority** of the incoming traffic. Traffic originating from verified employees of the TAL or their major customers triggers the "Conquest Multiplier."

### Response Speed (The "Bounty" Score)

The latency between a Technographic Signal (e.g., a competitor tech-stack change) and the first verified engagement from that account.

### Reasoning Quality (The "Intelligence" Score)

Validators evaluate the coherence and verifiability of the miner's reasoning trace. Strong reasoning = bonus multiplier. Weak reasoning = penalty.

### Contextual Integrity (The "Reputation" Score)

Validators use sentiment analysis and platform feedback to ensure the miner's placement is professional and brand-safe. High "Spam" reports or low-quality environments result in score degradation and potential slashing.

---

## The Intelligence Hierarchy

Miners are rewarded based on the sophistication of their intelligence:

| Level | Capability | Reward Tier |
|-------|------------|-------------|
| **Level 1** | Channel Access — presence in gated communities | Base |
| **Level 2** | Strategic Matching — connecting assets to targets with reasoning | 2x |
| **Level 3** | Signal Detection — identifying shifts from noisy data | 5x |
| **Level 4** | Market Prediction — anticipating windows before signals appear | 10x |

---
