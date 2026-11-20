# Contributing to automotive-hmi-ux

Thanks for helping designers build in-vehicle interfaces that don't put drivers at risk.

## Ground rules

1. **Every rule needs a source and a tag.** Link the primary source where possible (the regulation, rating protocol, platform guideline, study or the car maker's own publication) and tag it: `[REG]` law or regulation, `[STD]` standard, rating protocol or platform guideline, `[RES]` published research, `[PRAC]` documented company practice, `[INF]` our inference. Secondary summaries are fine when the primary isn't reachable; say so.
2. **Paraphrase, never paste.** Write rules in your own words. Keep published numbers (glance times, angles, takeover seconds, dates). Quotations only where the exact wording matters, and short.
3. **Date everything that can change.** Regulations and rating protocols get an "applies from" date and the market they apply to. Drafts and proposals are labelled as such.
4. **Mark what you didn't verify.** Many automotive standards are paywalled. If you're relying on a summary, or on memory, say "not verified".
5. **Say what's borrowed.** Two-wheeler and HUD evidence is thin. If a rule borrows a car threshold, label it as borrowed.
6. **No brand assets.** No logos, tell-tale artwork, proprietary fonts, vehicle or app screenshots. Name styles descriptively.

## Where things go

| Change | File in `skills/automotive-hmi/references/` |
|---|---|
| Glance budgets, lockouts, display placement, physical controls, platform limits, testing | `distraction-and-glance.md` |
| SAE levels, ADAS and automation rules, driver monitoring, mode display, escalation, takeover | `automation-and-handover.md` |
| Cluster, tell-tales, typography, night and glare, HUD, steering-wheel controls, motion | `clusters-hud-and-visual.md` |
| Voice and LLM assistants, EV, OTA, companion apps | `assistants-ev-ota.md` |
| Motorcycles and scooters | `two-wheelers.md` |
| What a car maker did and what it teaches | `case-studies.md` |

Keep `SKILL.md` short: the most important rules, the checklist and a routing table. Detail belongs in the references.

## Most wanted

The gaps are listed at the end of each reference file. The biggest:

- Two-wheeler glance and rider-distraction research; India AIS/BIS two-wheeler display rules
- Helmet and car HUD studies; AR-HUD hazard highlighting
- In-car voice workload research (AAA Foundation, University of Utah)
- EV charging UX studies
- ISO 15005/15008/16951/2575 and SAE J3016 details from the standards themselves
- Case studies: Rivian, Lucid, Toyota, BYD, NIO, Ola, BMW Motorrad, Ducati

## Pull requests

Describe what changed, link the sources you used, and say which claims you verified against a primary source.
