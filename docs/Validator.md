# SignalCast: Validator Architecture & Audit Logic

The SignalCast validator acts as the **Strategic Arbiter** of the subnet. Its primary responsibility is not just to verify data, but to audit the **Intent and Authority** of the traffic driven by miners. By interfacing with Subnet 93 (Bitcast) and external Firmographic registries, the validator ensures that every TAO of emission is backed by genuine industrial influence.

---

### Scoring and Evaluation Methodology

The evaluation of a miner is a multi-dimensional process that prioritizes **Lead Quality** over **Traffic Volume**. Scoring is calculated using a weighted composite of three primary vectors:

* **Firmographic Accuracy ($W_a$):**
    The validator performs a **Reverse IP Lookup** and **ASN Path Analysis** on every incoming click. Clicks are categorized into tiers:
    * **Tier 1 (Target Account List):** Verified employees of the competitor or their customers ($5\times$ weight).
    * **Tier 2 (Industry Relevant):** Verified employees within the same B2B vertical but not on the TAL ($2\times$ weight).
    * **Tier 3 (Generic):** Residential or non-corporate traffic ($0.1\times$ weight).
    * **Tier 4 (Data Center/VPN):** Disqualified ($0$ weight).
* **Behavioral Integrity ($W_i$):**
    Utilizing the **Honey-Link Protocol**, validators analyze the telemetry for "Human Signatures." Miners are penalized if the traffic shows:
    * Zero cursor jitter or perfectly linear scroll velocity.
    * Instantaneous "clicks" following a placement (bot-like reaction time).
    * High variance in IP origin but identical User-Agent strings.
* **Conversion Success ($W_c$):**
    The validator pings the **Subnet 93 Data Loop** to verify downstream actions. A miner who drives a single "Demo Request" or "Whitepaper Download" from a target domain receives a significantly higher score than a miner driving 1,000 "Top-of-Funnel" impressions.

---

### Evaluation Cadence

To ensure the network remains responsive to the fast-moving "Market Ruptures" of competitive industries, the evaluation follows a dual-track schedule:

1. **Real-Time Telemetry Processing:**
    As miners route traffic through their redirectors, validators perform asynchronous firmographic checks. This allows for the **Dynamic Kill-Switch** to be triggered immediately if a miner is detected pushing fraudulent or bot-heavy traffic.
2. **Epoch-Based Weight Commitment:**
    Every **360 blocks (approximately 1 hour)**, the validator aggregates the performance data from all active briefs. The final scores are normalized across the miner set and committed to the Subtensor as weight vectors.
3. **Bounty Settlement:**
    Technographic Bounties are evaluated on a **First-to-Verify** basis. Once a miner submits a "Proof of Signal" (e.g., a competitor tech-stack change), validators have a 10-minute window to reach consensus on the signal's validity before the bounty multiplier is activated.

---

### Validator Incentive Alignment

SignalCast ensures validators are economically driven to be honest, rigorous, and efficient:

* **V-Trust & Consensus:**
    Validators earn dividends based on their **V-Trust score**. If a validator consistently scores a miner differently than the stake-weighted median of the network (e.g., by being "too lenient" on a friendly miner), their V-Trust decays, reducing their own TAO rewards.
* **Attribution Accuracy Rebates:**
    A portion of the advertiser's "Distribution Fee" is held in an escrow pool. Validators who demonstrate the highest correlation between their internal scoring and the **actual sales data** reported by the advertiser receive a "Performance Dividend."
* **Fraud Detection Bounties:**
    Validators that are the first to identify and provide a "Proof of Adversarial Intent" against a malicious miner (resulting in a slash) are rewarded with a portion of the burned stake.
