# SignalCast: Business Logic & Market Rationale

SignalCast is not merely a distribution tool; it is a **Strategic Market-Share Engine**. By decentralizing the logic of competitive conquesting, it provides a high-ROI alternative to the inefficient "spray and pray" models of traditional digital advertising.

---

## The Problem the Subnet Aims to Solve and Why It Matters

In B2B marketing, the primary challenge is not a lack of content, but a **lack of precision**. Brands spend millions on broad social reach, yet **96% of consumers do not trust what they see in ads**. The "noise" of modern marketing has led to:

* **Skyrocketing CAC:** Customer Acquisition Costs have risen steadily, making traditional paid channels unsustainable for many mid-market firms.
* **Poor Attribution:** Proving marketing ROI remains complex due to multi-touch journeys and siloed data.
* **The Trust Gap:** Decision-makers are bombarded with irrelevant communications, leading to "ad blindness" and professional fatigue.

**Why it matters:** Businesses that cannot efficiently acquire customers from their competitors eventually stagnate. SignalCast solves this by turning distribution into an **adversarial intelligence game**, where miners are incentivized to find the "blind spots" of a competitor's marketing and fill them with high-value alternatives.

---

## Privacy & Compliance Framework

SignalCast operates in the B2B marketing intelligence space, processing firmographic data to identify and reach corporate decision-makers. The protocol is designed with privacy-by-design principles.

### Regulatory Acknowledgment

| Regulation | Jurisdiction | Key Requirements |
|------------|--------------|------------------|
| **GDPR** | EU/EEA | Lawful basis, data minimization, right to erasure |
| **CCPA/CPRA** | California | Opt-out rights, disclosure requirements |
| **ePrivacy Directive** | EU | Cookie consent, electronic communications |
| **CAN-SPAM** | United States | Commercial email requirements |

### What SignalCast Processes

| Data Type | Storage | Purpose |
|-----------|---------|---------|
| IP Address | Hashed only | Firmographic attribution |
| ASN/Org Name | Aggregated | Target verification |
| Behavioral Signals | Ephemeral | Bot detection |
| Conversion Data | Hashed | Lead qualification |

### What SignalCast Does NOT Process

* Personal names (unless voluntarily submitted via form)
* Personal email addresses (only domain extracted and hashed)
* Browsing history beyond the single session
* Cross-site tracking or persistent identifiers
* Sensitive categories (health, political views, etc.)

### Privacy-by-Design Principles

1. **Data Minimization:** Raw IP → Reverse Lookup → Org Name + ASN → Hash → Discard Raw IP. No raw IPs stored beyond validation window (~1 hour).

2. **Aggregation Over Identification:** SignalCast targets **organizations**, not individuals. The goal is to verify "this click came from a Replicate customer" — not to identify the specific person.

3. **First-Party Consent at Conversion:** When a user signs up for an API or submits a demo request, they provide work email and consent voluntarily.

4. **No Persistent Tracking:** No cookies, no browser fingerprinting, no persistent user profiles. Each session evaluated independently.

### Lawful Basis (GDPR)

B2B marketing to corporate decision-makers in their professional capacity is recognized as a **legitimate interest** under GDPR Article 6(1)(f), provided:
* Processing is necessary to prevent fraud and ensure advertiser ROI
* Processing is limited to professional context; no sensitive data involved
* Data minimization, hashing, and short retention periods protect individual rights

### Compliance Obligations

**Miners must:**
* Not store raw telemetry beyond submission window
* Not attempt to de-anonymize hashed data
* Not sell or transfer telemetry to third parties

**Validators must:**
* Verify firmographic data only against authorized registries
* Discard raw data after epoch validation
* Maintain audit logs of data handling (hashed, not raw)

**Advertisers must:**
* Maintain compliant landing pages with clear privacy policies
* Obtain proper consent for lead follow-up
* Honor opt-out and erasure requests

---

## Competing Solutions

### Within the Bittensor Ecosystem

* **Subnet 93 (Bitcast):** While SignalCast leverages SN93, the two are distinct. Bitcast focuses on the **creation** of content; SignalCast focuses on the **tactical distribution** of that content.
* **Subnet 71 (Leadpoet):** Leadpoet utilizes AI agents to find and qualify leads. SignalCast differs by acting as the **delivery vehicle** that moves those leads through a content-driven funnel, rather than just identifying them.

### Outside of Bittensor

* **Traditional ABM Platforms (Terminus, 6sense):** These are centralized, expensive SaaS tools that rely on proprietary data silos. SignalCast provides a **decentralized alternative** where a global network of miners competes to find placements that centralized algorithms often miss.
* **Google/Meta Ads:** These platforms prioritize their own ad revenue over advertiser ROI. SignalCast aligns incentives so that miners only earn when **verified industrial interest** is generated.

---

## Why This Use Case is Well-Suited to a Bittensor Subnet

Bittensor is the only infrastructure capable of incentivizing **Digital Reconnaissance** at scale.

* **Proof of Intelligence:** Identifying a competitor's customer base through "Technographic Ruptures" is a task requiring semantic reasoning and real-time research—perfect for Bittensor's competitive miner/validator architecture.
* **Incentive Alignment:** By using **Yuma Consensus**, SignalCast can reward the *quality* of a lead over the *quantity* of clicks. This is impossible in centralized ad networks where the platform is incentivized to maximize impressions.
* **Global Scale:** A decentralized network of miners can infiltrate niche industry forums, gated communities, and "Dark Social" channels that no centralized crawler can reach.

---

## Content Source Flexibility

SignalCast's core value proposition—**precision B2B distribution with verified firmographic targeting**—does not depend on any single content source.

### Supported Asset Types

| Source | Asset Type | Integration Status |
|--------|------------|-------------------|
| **SN93 (Bitcast)** | AI-generated video | Primary (native) |
| **Advertiser-provided** | Whitepapers, case studies, landing pages | Supported |
| **Other Bittensor subnets** | SN17 (3D), SN59 (audio), future content subnets | Planned |
| **External CDNs** | Any URL-addressable content | Supported |

### SN93 Integration Advantages

When content originates from SN93, additional features are available:
* **On-chain attribution:** Bitcast creators receive attribution credits when their content converts
* **Quality signals:** SN93's internal scoring can inform SignalCast's asset selection
* **Unified analytics:** Cross-subnet dashboards showing creation → distribution → conversion

These are **bonuses**, not requirements. SignalCast is **SN93-compatible, not SN93-dependent**.

---

## Path to Long-term Adoption and Sustainable Business

The path to sustainability for SignalCast lies in **Vertical Integration** with the B2B sales cycle.

### Phase 1: The Conquest Phase

Advertisers use SignalCast specifically to "snipe" competitor customers during renewal windows or tech migrations.

### Phase 2: The Lead-Gen Ecosystem

As validators improve at verifying firmographic data, SignalCast becomes a primary source for high-intent B2B leads, potentially charging a **Success Fee** (denominated in TAO) for every verified demo signup.

### Phase 3: Sustainable Revenue

By proving a lower **Cost Per Lead (CPL)** than LinkedIn or Google, SignalCast attracts external "Real World" capital into the Bittensor ecosystem. Advertisers pay to have their SN93 assets distributed, creating a non-inflationary demand for the subnet's Alpha token.

---
