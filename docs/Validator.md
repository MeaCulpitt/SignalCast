# SignalCast: Validator Architecture & Audit Logic

The SignalCast validator acts as the **Strategic Arbiter** of the subnet. Its primary responsibility is to audit the **Intent and Authority** of the traffic driven by miners. By interfacing with Subnet 93 (Bitcast) and external Firmographic registries, the validator ensures that every TAO of emission is backed by verified engagement from a competitor's customer base.

---

## Multi-Modal Verification Framework

### The Challenge with Reverse IP Alone

Reverse IP lookup has been a cornerstone of B2B visitor identification for years. However, modern work patterns have reduced its reliability:

| Factor | Impact on Reverse IP |
|--------|---------------------|
| Remote work | ~40% of corporate users now work from home/VPN |
| Cloud NAT | Companies route traffic through AWS/GCP, masking origin |
| Mobile devices | Carrier IPs are residential, not corporate |
| Privacy tools | VPNs, Tor, and privacy browsers block attribution |

**SignalCast addresses this by implementing a multi-modal verification stack.** Reverse IP remains valuable but is no longer sufficient alone.

---

## The Verification Stack

Validators use a layered approach, where each signal contributes to a confidence score:

```
┌─────────────────────────────────────────────────────────┐
│                    VERIFICATION STACK                    │
├─────────────────────────────────────────────────────────┤
│  Layer 5: Conversion Verification (Highest Confidence)  │
│  └─ Work email domain at form submission                │
├─────────────────────────────────────────────────────────┤
│  Layer 4: Referral Context                              │
│  └─ LinkedIn profile → click (professional context)     │
├─────────────────────────────────────────────────────────┤
│  Layer 3: Behavioral Signals                            │
│  └─ Session patterns consistent with professional use   │
├─────────────────────────────────────────────────────────┤
│  Layer 2: Reverse IP / ASN Lookup                       │
│  └─ Corporate network identification                    │
├─────────────────────────────────────────────────────────┤
│  Layer 1: Technographic Context (Lowest Confidence)     │
│  └─ Placement context suggests professional audience    │
└─────────────────────────────────────────────────────────┘
```

---

## Layer-by-Layer Breakdown

### Layer 1: Technographic Context (Weight: 0.5x)

The context of where the asset was placed suggests professional intent.

**Signals:**
* Placed in B2B-specific forum (e.g., Hacker News, industry Slack)
* Placed in thread discussing professional tools
* Time of engagement correlates with business hours in target region

**Limitations:** Contextual only. Does not verify the specific viewer.

### Layer 2: Reverse IP / ASN Lookup (Weight: 3x)

Traditional IP-to-organization mapping.

**Signals:**
* IP resolves to known corporate ASN
* Organization matches Target Account List
* IP not flagged as data center / VPN / residential proxy

**Limitations:** Misses remote workers (~40% of traffic). Can be spoofed with corporate VPN access.

### Layer 3: Behavioral Signals (Weight: 2x)

Session behavior consistent with professional, human engagement.

**Signals:**
* Engagement during business hours (user's timezone)
* Session duration > 60 seconds
* Natural scroll/cursor patterns (Honey-Link)
* Multiple page views suggesting research intent

**Limitations:** Sophisticated bots can mimic some patterns. Does not identify specific organization.

### Layer 4: Referral Context (Weight: 5x)

The user arrived via a platform that provides professional context.

**Signals:**
* Click originated from LinkedIn (profile context available)
* Click from corporate email link (e.g., Outlook click tracking)
* Referrer header indicates professional tool (Slack, Teams link preview)

**Limitations:** Referrer headers can be stripped by privacy settings.

### Layer 5: Conversion Verification (Weight: 10x)

The user voluntarily provides work identity at conversion.

**Signals:**
* Form submission with work email domain (e.g., @voiceflow.ai)
* Email domain matches Target Account List
* Email domain matches Reverse IP result (cross-validation)
* API signup or calendar booking with work email

**Limitations:** Only applies to bottom-of-funnel conversions.

---

## Composite Confidence Scoring

Validators calculate a **Firmographic Confidence Score (FCS)** by combining signals:

```python
def calculate_fcs(signals):
    score = 0.0
    
    # Layer 1: Context
    if signals.professional_context:
        score += 0.5
    
    # Layer 2: Reverse IP
    if signals.reverse_ip_match:
        score += 3.0
    elif signals.reverse_ip_corporate_but_not_tal:
        score += 1.0
    
    # Layer 3: Behavioral
    if signals.human_behavior_verified:
        score += 2.0
    if signals.business_hours:
        score += 0.5
    
    # Layer 4: Referral
    if signals.linkedin_referral:
        score += 5.0
    elif signals.professional_referral:
        score += 2.0
    
    # Layer 5: Conversion
    if signals.work_email_submitted:
        if signals.email_domain_in_tal:
            score += 10.0
        else:
            score += 3.0
    
    return score
```

**Scoring Thresholds:**

| FCS Range | Classification | Reward Tier |
|-----------|----------------|-------------|
| 15+ | Verified Conquest | Tier 1 (10x) |
| 8-14.9 | High Confidence | Tier 2 (3x) |
| 3-7.9 | Moderate Confidence | Tier 3 (1x) |
| < 3 | Low Confidence | Tier 4 (0.1x) |

---

## Handling Remote Workers

**Scenario:** Developer works from home. IP is residential (Comcast). Reverse IP fails.

**But:**
* Clicked from Hacker News thread (Layer 1: +0.5)
* Session shows natural behavior during business hours (Layer 3: +2.5)
* Signs up for API with alex@voiceflow.ai (Layer 5: +10)
* VoiceFlow is on Target Account List (bonus)

**Result:** FCS = 13+ → Tier 2 High Confidence (or Tier 1 with additional signals)

**Without multi-modal verification, this lead would be scored as residential noise.**

---

## Reasoning Quality Scoring

Validators evaluate miner reasoning traces using:

1. **Consistency checks:** Does the stated pain point actually appear in the referenced tweet/review?
2. **Technographic verification:** Is the target actually using the competitor's product?
3. **Temporal logic:** Does the timing rationale align with observable events?
4. **Semantic coherence:** Does the reasoning make logical sense?

Validators use LLMs to assist evaluation but apply human-calibrated scoring rubrics.

### Gaming Detection

| Red Flag | Interpretation |
|----------|----------------|
| Generic reasoning copied across placements | Template-based, not strategic |
| Reasoning doesn't match observable evidence | Fabricated justification |
| Timing rationale contradicts public data | Made up decision window |
| Target not verifiable in technographic registry | False customer claim |

Miners with consistently weak reasoning receive score penalties and eventual stake slashing.

---

## Behavioral Integrity (Honey-Link Protocol)

Utilizing the **Honey-Link Protocol**, validators analyze telemetry for "Human Signatures." Miners are penalized if traffic shows:

* Zero cursor jitter or perfectly linear scroll velocity
* Instantaneous "clicks" following a placement (bot-like reaction time)
* High variance in IP origin but identical User-Agent strings

---

## Evaluation Cadence

To ensure the network remains responsive to fast-moving "Market Ruptures," the evaluation follows a dual-track schedule:

### 1. Real-Time Telemetry Processing

As miners route traffic through their redirectors, validators perform asynchronous firmographic checks. This allows for a **Dynamic Kill-Switch** to be triggered immediately if a miner is detected pushing fraudulent or irrelevant traffic.

### 2. Epoch-Based Weight Commitment

Every **360 blocks (approximately 1 hour)**, the validator aggregates the performance data from all active briefs. The final scores are normalized across the miner set and committed to the Subtensor as weight vectors.

### 3. Bounty Settlement

Technographic Bounties (e.g., detecting a competitor's customer removing a script) are evaluated on a **First-to-Verify** basis. Once a miner submits a "Proof of Signal," validators have a 10-minute window to reach consensus.

---

## Validator Incentive Alignment

SignalCast ensures validators are economically driven to be honest, rigorous, and efficient:

### V-Trust & Consensus

Validators earn dividends based on their **V-Trust score**. Consistently scoring miners outside the stake-weighted median results in V-Trust decay and reduced rewards.

### Attribution Accuracy Rebates

A portion of the advertiser's "Distribution Fee" is held in escrow. Validators demonstrating the highest correlation between internal scores and **actual sales data** reported by the advertiser receive a "Performance Dividend."

### Fraud Detection Bounties

Validators that are the first to identify and provide a "Proof of Adversarial Intent" against a malicious miner are rewarded with a portion of the slashed stake.

---
