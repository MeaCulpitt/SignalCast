# SignalCast: Content Source Flexibility

## Relationship with Subnet 93 (Bitcast)

SignalCast is designed as the **distribution layer** for the Bittensor content ecosystem. While Subnet 93 (Bitcast) is our primary integration partner for AI-generated creative assets, SignalCast's architecture is **content-source agnostic**.

---

## Why SN93 is the Primary Partner

Bitcast (SN93) provides:

- High-quality AI-generated video content
- On-chain asset provenance and attribution
- Native Bittensor ecosystem integration
- Shared incentive alignment (Bitcast creators benefit from SignalCast distribution)

This makes SN93 the natural first integration. SignalCast amplifies Bitcast content; Bitcast creators gain reach through SignalCast miners.

---

## Content Source Independence

However, SignalCast's core value proposition—**precision B2B distribution with verified firmographic targeting**—does not depend on any single content source.

### Supported Asset Types

SignalCast miners can distribute:

| Source | Asset Type | Integration Status |
|--------|------------|-------------------|
| **SN93 (Bitcast)** | AI-generated video | Primary (native) |
| **Advertiser-provided** | Whitepapers, case studies, landing pages | Supported |
| **Other Bittensor subnets** | SN17 (3D), SN59 (audio), future content subnets | Planned |
| **External CDNs** | Any URL-addressable content | Supported |

### Input Format

The validator brief accepts any valid content reference:

```json
{
  "asset_source": "sn93 | url | ipfs",
  "asset_ref": "sn93_uid_xxx | https://example.com/asset | ipfs://Qm...",
  "asset_metadata": {
    "type": "video | pdf | landing_page",
    "duration_sec": 180,
    "topic_tags": ["crm", "cost-reduction", "migration"]
  }
}
```

Miners and validators process the distribution and verification logic identically, regardless of where the content originates.

---

## Resilience Benefits

This architecture provides:

1. **Ecosystem resilience:** If SN93 pivots or pauses, SignalCast continues operating with other content sources.

2. **Advertiser flexibility:** Enterprises can use their existing content libraries, not just AI-generated assets.

3. **Cross-subnet synergy:** As new content-generating subnets launch, SignalCast can integrate without protocol changes.

4. **Faster adoption:** Advertisers don't need to wait for SN93 content creation to test SignalCast distribution.

---

## SN93 Integration Advantages

When content originates from SN93, additional features are available:

- **On-chain attribution:** Bitcast creators receive attribution credits when their content converts.
- **Quality signals:** SN93's internal scoring can inform SignalCast's asset selection.
- **Unified analytics:** Cross-subnet dashboards showing creation → distribution → conversion.

These are **bonuses**, not requirements. SignalCast functions fully with or without SN93 integration.

---

## Summary

SignalCast is **SN93-compatible, not SN93-dependent**.

The subnet's core innovation—decentralized precision B2B distribution with firmographic verification—is valuable for any content. Bitcast is the ideal first partner, but SignalCast's architecture ensures long-term flexibility and resilience.

---
