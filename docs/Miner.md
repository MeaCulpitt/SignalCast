# SignalCast: Miner Architecture & Operations

The SignalCast miner is a decentralized **Market Intelligence & Distribution Node**. Unlike traditional "click-farms," a SignalCast miner must operate as an autonomous A&R (Artists and Repertoire) agent—identifying the highest-quality assets from Subnet 93 and matching them to high-intent "Pulse Zones" where competitor employees and their customers reside.

---

### Miner Tasks

A SignalCast miner performs a continuous four-stage cycle that requires both computational effort and strategic semantic reasoning:

1. **Asset Scouting (Creative Intelligence):**
   * The miner monitors the Subnet 93 (Bitcast) metagraph to identify high-performing creative assets.
   * Miners use LLMs to analyze asset transcripts and metadata to determine "Market Fit" for specific industrial briefs and lead magnets (e.g., matching a technical video to a specific whitepaper).

2. **Technographic Reconnaissance (Targeting):**
   * Miners scan the open web for "Market Ruptures" (e.g., a company removing a competitor’s script, detecting legacy software versions, or identifying relevant job openings).
   * They identify specific, gated B2B environments (specialized forums, Discord servers, industry-specific newsletters) and high-authority X.com threads where target accounts are active.

3. **Precision Placement (The Interest Pipeline):**
   * Miners generate a unique tracking signature and "push" the SN93 asset into the identified zone.
   * Miners are incentivized to bridge the gap between social awareness and industrial intent by driving users toward "Lead Magnets" such as Whitepapers, Demos, and Contact Forms.

4. **Telemetry Maintenance (Verification):**
   * Miners host a lightweight redirect proxy that captures initial visitor telemetry (IP/User-Agent) before routing to the Bitcast asset or landing page.
   * This telemetry is hashed and submitted to validators as a "Proof of Human Signal" to verify the firmographic origin of the lead.

---

### Expected Input → Output Format

To maintain interoperability within the Bittensor ecosystem, miners must adhere to a strict I/O protocol.

* **Input (From Subnet 93 / Validators):**
   * `Asset_UID`: The unique identifier of the content on SN93.
   * `Target_Account_List (TAL)`: A JSON array of corporate domains (e.g., `["competitor.com", "target-client.com"]`).
   * `Conversion_Targets`: Metadata specifying required actions (e.g., X.com Follows, Whitepaper DLs, Demo Signups).

* **Output (To Validators):**
   * `Placement_Proof`: A URL or Social Object ID proving where the asset was shared.
   * `Telemetry_Bundle`: A hashed packet containing the visitor’s Firmographic data and the specific "Interest Signal" triggered.
   * `Signal_Identity`: A ZK-proof verifying the humanity and professional context of the interaction.

---

### Performance Dimensions

Miners are scored on a multi-dimensional matrix where **Strategic Accuracy** outweighs raw volume.

* **Conversion Depth (The "Quality" Score):**
   * Measured by the miner's ability to move a user down the funnel. A "Demo Signup" (Bottom-of-funnel) generates significantly higher rewards than a "Like" (Top-of-funnel).
   
* **Targeting Precision (The "Sniper" Score):**
   * Success is measured by the **Domain Authority** of the incoming traffic. Traffic originating from verified employees of the TAL or their major customers triggers the "Conquest Multiplier."

* **Response Speed (The "Bounty" Score):**
   * The latency between a Technographic Signal (e.g., a competitor tech-stack change) and the first verified engagement from that account. 

* **Contextual Integrity (The "Reputation" Score):**
   * Validators use sentiment analysis and platform feedback to ensure the miner’s placement is professional and brand-safe. High "Spam" reports or low-quality environments result in score degradation and potential slashing.
