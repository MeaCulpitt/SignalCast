# SignalCast: Validator Architecture & Audit Logic

The SignalCast validator acts as the **Strategic Arbiter** of the subnet. Its primary responsibility is to audit the **Intent and Authority** of the traffic driven by miners. By interfacing with Subnet 93 (Bitcast) and external Firmographic registries, the validator ensures that every TAO of emission is backed by verified engagement from a competitor's customer base.

---

### Scoring and Evaluation Methodology

The evaluation of a miner is a multi-dimensional process that prioritizes **Strategic Conquest** over raw volume. Internal traffic from competitor corporate domains is filtered out to ensure miners focus exclusively on the **Competitor's Customer Base**.

* **Firmographic Accuracy ($W_a$):**
    The validator performs a **Reverse IP Lookup** and **ASN Path Analysis** on every incoming click. Clicks are categorized into tiers:
    * **Tier 1 (Verified Competitor Customers):** Verified employees of companies currently using a competitor's technology stack ($10\times$ weight).
    * **Tier 2 (High-Fit Industry Targets):** Verified employees within the same B2B vertical with high propensity to switch ($3\times$ weight).
    * **Tier 3 (Generic/Competitor Internal):** Residential traffic or internal competitor staff ($0.1\times$ weight).
    * **Tier 4 (Data Center/VPN):** Disqualified ($0$ weight).
* **Behavioral Integrity ($W_i$):**
    Utilizing the **Honey-Link Protocol**, validators analyze the telemetry for "Human Signatures." Miners are penalized if the traffic shows:
    * Zero cursor jitter or perfectly linear scroll velocity.
    * Instantaneous "clicks" following a placement (bot-like reaction time).
    * High variance in IP origin but identical User-Agent strings.
* **Conversion Success ($W_c$):**
    Success is measured by the **Depth of Interest** tracked via the **Subnet 93 Data Loop** and social APIs:
    * **Direct Leads (10x):** Whitepaper downloads, demo requests, or contact form submissions.
    * **Social Growth (5x):** New "Follows" on the advertiser's X.com or professional profiles from verified customer domains.
    * **Engagement Velocity (3x):** High-authority Likes, Reposts, and Bookmarks on the distributed creative asset.
    * **Attention Retention (1x):** Sustained "Watch-Time" proving audience relevance.

---

### Evaluation Cadence

To ensure the network remains responsive to fast-moving "Market Ruptures," the evaluation follows a dual-track schedule:

1. **Real-Time Telemetry Processing:**
    As miners route traffic through their redirectors, validators perform asynchronous firmographic checks. This allows for a **Dynamic Kill-Switch** to be triggered immediately if a miner is detected pushing fraudulent or irrelevant traffic.
2. **Epoch-Based Weight Commitment:**
    Every **360 blocks (approximately 1 hour)**, the validator aggregates the performance data from all active briefs. The final scores are normalized across the miner set and committed to the Subtensor as weight vectors.
3. **Bounty Settlement:**
    Technographic Bounties (e.g., detecting a competitor's customer removing a script) are evaluated on a **First-to-Verify** basis. Once a miner submits a "Proof of Signal," validators have a 10-minute window to reach consensus.

---

### Validator Incentive Alignment

SignalCast ensures validators are economically driven to be honest, rigorous, and efficient:

* **V-Trust & Consensus:**
    Validators earn dividends based on their **V-Trust score**. Consistently scoring miners outside the stake-weighted median results in V-Trust decay and reduced rewards.
* **Attribution Accuracy Rebates:**
    A portion of the advertiser's "Distribution Fee" is held in escrow. Validators demonstrating the highest correlation between internal scores and **actual sales data** reported by the advertiser receive a "Performance Dividend."
* **Fraud Detection Bounties:**
    Validators that are the first to identify and provide a "Proof of Adversarial Intent" against a malicious miner are rewarded with a portion of the slashed stake.
