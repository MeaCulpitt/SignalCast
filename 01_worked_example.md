# SignalCast: Worked Example

## Scenario: Acme CRM vs. Salesforce

This walkthrough demonstrates the complete SignalCast interest pipeline from asset placement to validated conquest reward.

---

### Context

**Advertiser:** Acme CRM (mid-market Salesforce competitor)
**Target:** Salesforce customers experiencing pain points
**Asset:** SN93-generated case study video: "How TechCorp Cut CRM Costs 40% by Switching from Salesforce"
**Lead Magnet:** Technical whitepaper download + demo signup form

---

### Stage 1: Task Ingest & Discovery

The validator broadcasts a brief to the miner network:

```json
{
  "asset_uid": "sn93_acme_techcorp_casestudy_v2",
  "target_account_list": ["salesforce.com", "known-sf-customers.json"],
  "conversion_targets": {
    "tier_1": ["demo_signup", "contact_form"],
    "tier_2": ["whitepaper_download"],
    "tier_3": ["x_follow", "linkedin_follow"]
  },
  "lead_magnet_url": "https://acme.com/sf-migration-guide",
  "budget_tao": 50,
  "expires": "2026-02-15T00:00:00Z"
}
```

---

### Stage 2: Miner Reconnaissance

**Miner 0x7A3F** performs adversarial reconnaissance:

1. **Technographic scan:** Queries BuiltWith API, detects that NovaTech Inc. runs Salesforce Sales Cloud.
2. **Churn signal detection:** Finds a recent G2 review from a NovaTech employee: "Salesforce is overpriced for what we use."
3. **Pulse zone identification:** Locates an active X.com thread where NovaTech's VP of Revenue Operations (@sarah_novatech) is discussing CRM frustrations.
4. **Strategic match:** Uses LLM to confirm the Acme case study addresses NovaTech's specific pain points (cost, complexity).

**Miner reasoning submitted:**
> "NovaTech is a verified Salesforce customer (BuiltWith confirmation). Recent G2 review indicates pricing dissatisfaction. VP of RevOps is active in CRM discussion thread. Asset directly addresses cost reduction use case. High conquest probability."

---

### Stage 3: Precision Placement

Miner 0x7A3F:

1. Generates a unique tracking URL: `https://sc.link/a7f3x9`
2. Posts a reply in the X.com thread: "Saw a case study on this exact problem — TechCorp cut their Salesforce bill 40%. [link]"
3. The link routes through the miner's telemetry proxy before redirecting to the Acme landing page.

---

### Stage 4: Engagement & Conversion

**What happens:**

1. @sarah_novatech clicks the link from her office laptop.
2. Watches the case study video (4 min 32 sec watch time).
3. Downloads the technical whitepaper using her work email: sarah.chen@novatech.com
4. Two days later, submits a demo request form.

**Telemetry captured:**
```json
{
  "click_ip": "198.51.100.47",
  "reverse_ip_result": "NovaTech Inc. (AS12345)",
  "user_agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7)...",
  "cursor_jitter": 0.73,
  "scroll_variance": "natural",
  "watch_time_sec": 272,
  "conversion_email_domain": "novatech.com",
  "conversion_type": "demo_signup",
  "time_to_convert": "48h"
}
```

---

### Stage 5: Validation & Scoring

**Validator checks:**

| Check | Result | Score Impact |
|-------|--------|--------------|
| Reverse IP matches corporate ASN | NovaTech Inc. | +base |
| NovaTech in Target Account List | Salesforce customer | **10x Conquest Multiplier** |
| Email domain matches IP org | novatech.com | +verification bonus |
| Behavioral integrity (Honey-Link) | Human signatures detected | No penalty |
| Conversion depth | Demo signup (Tier 1) | **10x conversion weight** |
| Miner reasoning quality | Strong strategic logic | +5% bonus |

**Final score calculation:**
```
Base_Score = 1.0
Conquest_Multiplier = 10x (verified competitor customer)
Conversion_Weight = 10x (demo signup)
Reasoning_Bonus = 1.05

Final_Score = 1.0 x 10 x 10 x 1.05 = 105 points
```

Compare to a residential click with a "Like": `1.0 x 0.1 x 1 x 1.0 = 0.1 points`

**Miner 0x7A3F receives 1,050x more reward for the strategic conquest than for a generic impression.**

---

### Stage 6: Reward Allocation

At epoch close (360 blocks):

1. Validator aggregates all miner scores.
2. Miner 0x7A3F's 105-point conversion represents 12% of total epoch value.
3. TAO emissions allocated proportionally.
4. Advertiser's escrow releases success fee to subnet.

---

### Outcome Summary

| Metric | Value |
|--------|-------|
| Asset placed | SN93 case study |
| Target acquired | NovaTech (Salesforce customer) |
| Conversion | Demo signup |
| Miner reward | ~6 TAO |
| Advertiser cost | ~2 TAO (pay-on-conversion) |
| Salesforce | Lost a customer touchpoint |

**This is SignalCast: turning decentralized distribution into verified competitive conquest.**

---
