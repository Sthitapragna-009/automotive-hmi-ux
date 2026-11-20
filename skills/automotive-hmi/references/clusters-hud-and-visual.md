# Clusters, HUDs and the visual layer

Source types: **[REG]** · **[STD]** · **[RES]** · **[PRAC]** · **[INF]** (see SKILL.md).

## 1. Cluster hierarchy [INF]

Top priority, always visible, nearest the line of sight:

1. Speed (largest, tabular figures) and the current speed limit
2. Active warnings and tell-tales
3. Automation mode and what it controls
4. Navigation next manoeuvre (distance + arrow + street)
5. Range/fuel, gear, odometer, time

Everything else is on demand. Mercedes' "zero layer" surfaces key apps without menu navigation and lets context suggestions be accepted or dismissed in one tap [PRAC] ([Mercedes-Benz Group](https://group.mercedes-benz.com/technologie/digitalisierung/konnektivitaet/mbux-hyperscreen.html)). BMW's Panoramic iDrive projects key information along the base of the windscreen, nearest the line of sight [PRAC].

## 2. Never blank a safety value

Euro NCAP 2026 marked down a car that didn't show the last known speed limit with a clear indication that a sign could not be read [STD] ([Euro NCAP](https://www.euroncap.com/en/press-media/buttons-are-back-for-basic-functions-euro-ncap-confirms-in-testing/)). Generalise: speed limit, range, tyre pressure and battery temperature show the last known value plus an explicit "unknown/unreadable" state, never an empty space. [INF]

## 3. Tell-tales and colour

- Widely used convention (ISO 2575; not verified for this repo): **red** = danger or failure needing immediate action, **amber/yellow** = caution or malfunction, **green** = system on/working, **blue** = high beam. Do not use these colours for decoration or brand. [STD, unverified]
- ISA-101's "gray is good" from process control transfers to clusters: neutral by default so colour means something [PRAC] ([Going gray](https://control.com/technical-articles/going-gray/)).
- Colour is never the only signal: tell-tales also have distinct symbols and positions.

## 4. Typography and legibility

- **One typeface**, restricted palette; cluster and centre display mirror each other (Polestar) [PRAC] ([GoAuto](https://goauto.com.au/amp/93827/polestar-details-hi-tech-hmi-for-3-and-4-suvs.html)).
- Large x-height, open apertures, distinct 1/7 and 0/8; tabular figures for speed and range so digits don't jump. [INF]
- Size text for the real viewing distance (often 70–90 cm to the cluster, further to a centre screen) and test in a buck or car, not on a desktop monitor. ISO 15008 sets legibility requirements (character size and contrast; not verified). [INF/STD]
- Driving text: 1–3 lines, ≤ 120 characters (Android for Cars) [STD].
- Use positive phrasing and verbs: "Take the wheel", not "Autosteer unavailable condition detected".

## 5. Night and glare [INF]

- Dark UI at night with low-luminance backgrounds; no large white areas; automatic day/night switching from a light sensor (Royal Enfield Tripper Dash does this) [PRAC].
- Avoid saturated blue and pure white at night (glare and night vision); dim everything except warnings.
- Reflections: test screens in the windscreen at night.

## 6. Head-up displays

**Not yet researched with primary sources.** Working rules [INF]:

- Show only what's needed in the line of sight: speed, limit, next turn, critical warnings, automation mode.
- Never show content that invites reading.
- AR overlays must register accurately or not appear; misplaced graphics are worse than none.
- Keep the HUD consistent with the cluster (same symbols and colours).

## 7. Steering-wheel and haptic controls

- BMW uses haptic pads with raised elements on the wheel and shows some controls only when needed [PRAC].
- Controls must be findable by feel and distinguishable without activation (ADA §707 principle for ATMs applies) [REG, by analogy].
- Capacitive wheel controls that trigger by accident while steering fail this test. [INF]

## 8. Motion

- Animations in the cluster explain change (mode switching, navigation progress), never decorate.
- Respect a reduced-motion setting; no motion in peripheral vision that mimics a warning. [INF]
