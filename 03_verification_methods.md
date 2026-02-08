# SignalCast: Multi-Modal Verification Framework

## The Challenge with Reverse IP Alone

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

SignalCast validators use a layered approach, where each signal contributes to a confidence score:

```
┌─────────────────────────────────────────────────────────┐
│                    VERIFICATION STACK                    │
├─────────────────────────────────────────────────────────┤
│  Layer 5: Conversion Verification (Highest Confidence)  │
│  └─ Work email domain at form submission                │
├─────────────────────────────────────────────────────────┤
│  Layer 4: Referral Context                              │
│  └─ LinkedIn profile → click (professional context)    │
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

**What it is:** The context of where the asset was placed suggests professional intent.

**Signals:**
- Placed in B2B-specific forum (e.g., r/salesforce, industry Slack)
- Placed in thread discussing professional tools
- Time of engagement correlates with business hours in target region

**Limitations:** Contextual only. Does not verify the specific viewer.

**Use case:** Establishes baseline relevance. A click from a gaming subreddit scores lower than one from a SaaS discussion thread.

---

### Layer 2: Reverse IP / ASN Lookup (Weight: 3x)

**What it is:** Traditional IP-to-organization mapping.

**Signals:**
- IP resolves to known corporate ASN
- Organization matches Target Account List
- IP not flagged as data center / VPN / residential proxy

**Limitations:** 
- Misses remote workers (~40% of traffic)
- Can be spoofed with corporate VPN access
- Some organizations share ASN ranges

**Use case:** Strong signal when available. Remote workers fall through to other layers.

---

### Layer 3: Behavioral Signals (Weight: 2x)

**What it is:** Session behavior consistent with professional, human engagement.

**Signals:**
- Engagement during business hours (user's timezone)
- Session duration > 60 seconds
- Natural scroll/cursor patterns (Honey-Link)
- Multiple page views suggesting research intent
- Return visits within professional timeframe

**Limitations:** 
- Sophisticated bots can mimic some patterns
- Does not identify specific organization

**Use case:** Filters out bot traffic. Combined with other layers, increases confidence.

---

### Layer 4: Referral Context (Weight: 5x)

**What it is:** The user arrived via a platform that provides professional context.

**Signals:**
- Click originated from LinkedIn (profile context available)
- Click from corporate email link (e.g., Outlook click tracking)
- Referrer header indicates professional tool (Slack, Teams link preview)

**Limitations:**
- Referrer headers can be stripped by privacy settings
- Requires platform-specific integration

**Use case:** When a user clicks from their LinkedIn profile or corporate email, we have high confidence of professional context even without IP verification.

---

### Layer 5: Conversion Verification (Weight: 10x)

**What it is:** The user voluntarily provides work identity at conversion.

**Signals:**
- Form submission with work email domain (e.g., @novatech.com)
- Email domain matches Target Account List
- Email domain matches Reverse IP result (cross-validation)
- Calendar booking with work email

**Limitations:**
- Only applies to bottom-of-funnel conversions
- Users can submit personal email (lower score)

**Use case:** Highest confidence. A demo signup with matching work email is near-certain verification.

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

The multi-modal approach specifically addresses the remote work challenge:

**Scenario:** Sarah works from home. Her IP is residential (Comcast). Reverse IP fails.

**But:**
- She clicked from a LinkedIn thread (Layer 4: +5)
- Session shows natural behavior during business hours (Layer 3: +2.5)
- She downloads whitepaper with sarah@novatech.com (Layer 5: +10)
- NovaTech is on Target Account List (bonus)

**Result:** FCS = 17.5 → Tier 1 Verified Conquest

**Without multi-modal verification, this lead would be scored as residential noise.**

---

## Summary

SignalCast's multi-modal verification ensures:

1. **Reverse IP is used but not relied upon exclusively**
2. **Remote workers are captured through behavioral and conversion signals**
3. **Each layer compensates for the limitations of others**
4. **Confidence scoring is transparent and auditable**

This approach maintains targeting precision while adapting to modern work patterns.

---
