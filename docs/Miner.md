# SignalCast: Miner Architecture & Operations

The SignalCast miner is a decentralized **Market Intelligence & Distribution Node**. Unlike traditional "click-farms," a SignalCast miner must operate as an autonomous A&R (Artists and Repertoire) agent—identifying the highest-quality assets from Subnet 93 and matching them to high-intent "Pulse Zones" where competitor employees and their customers reside.

---

### Miner Tasks

A SignalCast miner performs a continuous four-stage cycle that requires both computational effort and strategic semantic reasoning:

1. **Asset Scouting (Creative Intelligence):**
   * The miner monitors the Subnet 93 (Bitcast) metagraph to identify high-performing creative assets.
   * Miners use LLMs to analyze asset transcripts and metadata to determine "Market Fit" for specific industrial briefs.

2. **Technographic Reconnaissance (Targeting):**
   * Miners scan the open web for "Market Ruptures" (e.g., a company removing a competitor’s script or posting a relevant job opening).
   * They identify specific, gated B2B environments (specialized forums, Discord servers, industry-specific newsletters) where target accounts are active.

3. **Precision Placement (Distribution):**
   * Miners generate a unique tracking signature and "push" the SN93 asset into the identified zone.
   * The placement must be contextually relevant; miners are incentivized to bypass traditional ad-blockers by using "Native" community-led distribution.

4. **Telemetry Maintenance (Verification):**
   * Miners host a lightweight redirect proxy that captures initial visitor telemetry (IP/User-Agent) before routing to the Bitcast asset.
   * This telemetry is hashed and submitted to validators as a "Proof of Human Signal."

---

### Expected Input → Output Format

To maintain interoperability within the Bittensor ecosystem, miners must adhere to a strict I/O protocol.

* **Input (From Subnet 93 / Validators):**
   * `Asset_UID`: The unique identifier of the content on SN93.
   * `Target_Account_List (TAL)`: A JSON array of corporate domains (e.g., `["competitor.com", "target-client.com"]`).
   * `Brief_Context`: Semantic metadata describing the advertiser's pain points and USP.

* **Output (To Validators):**
   * `Placement_Proof`: A URL or Social Object ID proving where the asset was shared.
   * `Telemetry_Hash`: A cryptographic hash of the visitor’s Firmographic data.
   * `Signal_Identity`: A ZK-proof (if utilizing SN2) verifying the humanity of the interaction.

---

### Performance Dimensions

Miners are scored on a multi-dimensional matrix. High-performance hardware is less important than **Strategic Accuracy**.

* **Conversion Accuracy (The "Quality" Score):**
   * Measured by the ratio of "Total Clicks" to "Verified B2B Leads." Miners who drive 10 high-value corporate clicks are ranked higher than miners who drive 10,000 generic bot clicks.

* **Targeting Precision (The "Sniper" Score):**
   * How closely the traffic matches the TAL. Success is measured by the **Domain Authority** of the incoming IP addresses.

* **Response Speed (The "Bounty" Score):**
   * The latency between a Technographic Signal (e.g., a tech stack change) and the first verified engagement from that account. 

* **Brand Safety (The "Reputation" Score):**
   * Validators use sentiment analysis to ensure the miner’s placement context is professional and not "spammy." High "Flag Rates" from target platforms will degrade this score.
