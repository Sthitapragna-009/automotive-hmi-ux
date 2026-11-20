---
name: automotive-hmi
description: Design in-vehicle interfaces for cars and two-wheelers that drivers can use without crashing. Covers glance and task budgets (NHTSA 2 s / 12 s), what must be locked while driving, display placement, which functions need physical controls (Euro NCAP 2026), menu depth and text limits (Android for Cars, CarPlay), instrument clusters, tell-tales, head-up displays, voice and LLM assistants, driver-assistance and automation (SAE levels, UN R171/R157, IIHS safeguards) including mode display, alerts and takeover/handover, driver monitoring, EV range and charging, OTA updates, motorcycle and scooter TFT dashboards and navigation, plus case studies (Tesla, VW, Hyundai, BMW, Mercedes, Polestar, CarPlay Ultra, Royal Enfield, Ather). Use whenever you design, prototype, critique or spec a dashboard, cluster, infotainment screen, HUD, car app, ADAS/autopilot UI, EV app or two-wheeler display.
---

# automotive-hmi

Every glance at a screen is a glance away from the road. Automotive HMI is the most quantified high-stakes domain: regulators, rating bodies and platform owners all publish numbers. This skill turns them into design rules, and is honest where evidence is missing (two-wheelers, EV, HUD).

This skill stands on its own. For alerts, automation trust and payments in the car, the companion [criticalUX](https://github.com/Sthitapragna-009/Critical_UX) skills go deeper.

## How to use this skill

1. **Classify the surface and its driving state.** Cluster, centre display, HUD, steering-wheel controls, voice, phone projection (CarPlay/Android Auto), native app (Android Automotive), two-wheeler TFT, companion phone app. Then: parked, driving, or under automation (which SAE level).
2. **Give every task a glance budget** before designing it (`distraction-and-glance.md`). If a task cannot fit, move it to voice, a physical control or "parked only".
3. **Map controls** to physical, touch, voice or automatic using the control map.
4. **If any automation is involved,** design mode display, escalation and handover with `automation-and-handover.md`.
5. **Design the visual layer** with `clusters-hud-and-visual.md`.
6. **For bikes and scooters,** load `two-wheelers.md` and label borrowed car thresholds as borrowed.
7. **Test** with occlusion or eye tracking against the budgets; compare to a physical-button baseline.

| Reference | Load it for |
|---|---|
| `references/distraction-and-glance.md` | NHTSA glance and occlusion budgets, lockouts, display angles, Euro NCAP physical controls, Android for Cars and CarPlay limits, benchmark test data |
| `references/automation-and-handover.md` | SAE levels, R171/R157, IIHS safeguards, driver monitoring, mode display, escalation, takeover times, Tesla recall lessons |
| `references/clusters-hud-and-visual.md` | Cluster layout, tell-tale colours, speed and limit display, typography, night palettes, HUD, zero-layer surfacing, haptics |
| `references/assistants-ev-ota.md` | Voice and LLM assistants, EV range/charging/regen, OTA updates, connected-car phone apps |
| `references/two-wheelers.md` | Motorcycle and scooter dashboards, glove input, navigation, safety features |
| `references/case-studies.md` | What OEMs did and what it teaches |

## The rules that matter most

Source types: **[REG]** regulation · **[STD]** standard, rating protocol or platform guideline · **[RES]** published research · **[PRAC]** company practice · **[INF]** our synthesis from the sources.

1. **Glances ≤ 2 s, task total ≤ 12 s.** A task must also be completable in 1.5 s occluded glances within 12 s total [STD] (NHTSA 2013, voluntary).
2. **One hand, interruptible at any moment, resumable** where the driver left off [STD].
3. **Lock while moving** (propulsion on and not in Park): video, auto-scrolling text, manual text entry for messages or browsing, reading web, social or message text. Read aloud instead [STD].
4. **Display centre within 30° below the driver's line of sight** [STD]. Measured cars needed 20°–56° to reach the bottom of their screens [PRAC].
5. **Physical controls for indicators, wipers and washer, hazards, horn and the SOS/eCall button** (Euro NCAP 2026). Keep climate and volume physical where possible [STD/PRAC].
6. **Frequent tasks in ≤ 3 taps; ≤ 5 screens per task; driving text 1–3 lines and ≤ 120 characters** (Android for Cars) [STD].
7. **Benchmark against buttons.** A 2005 Volvo with buttons finished four tasks in 10.0 s; touchscreen cars took 13.7–44.9 s at 110 km/h [PRAC, magazine test].
8. **Automation mode is unmissable** and simple to engage and disengage. Weak prominence led to a 2-million-vehicle recall (Tesla 23V-838) [REG].
9. **Monitor eyes and head, not just hands on the wheel** (UN R171) and **escalate**: visual → audible → haptic → slow to a stop with hazards → lock the feature out for the drive (IIHS) [REG/STD].
10. **Plan handovers for the slow driver, not the average one.** Takeover times ranged 1.9–25.7 s; give at least 10 s for Level 3 and a minimal-risk manoeuvre if nobody takes over [RES/REG].
11. **Never blank a safety value.** Show the last known speed limit and say plainly when a sign couldn't be read [STD].
12. **Key functions at the top level** (zero layer); suggestions accepted or dismissed in one tap [PRAC].
13. **One typeface, restricted palette, colour reserved for status** (tell-tales); cluster and centre display agree [PRAC/INF].
14. **Two-wheelers: one glove-friendly input, minimal glance mode by default, auto day/night**, and say which car thresholds you borrowed [PRAC/INF].

## Before you hand over, check

- [ ] Every task listed with its driving state and glance budget; over-budget tasks moved to voice, physical or parked-only
- [ ] Lockouts implemented and explained ("Available when parked"), with voice alternatives
- [ ] The five Euro NCAP functions on physical inputs; climate and volume reachable without menus
- [ ] Menu depth ≤ 3 taps for frequent tasks; text ≤ 120 characters while driving
- [ ] Automation states (off, available, active, degraded, takeover requested, minimal-risk manoeuvre) each designed, in the cluster and HUD
- [ ] Escalation sequence with timings; lockout after repeated misuse
- [ ] Speed limit shows last known value and an "unreadable" state
- [ ] Night palette tested for glare; text sizes tested at the real viewing distance
- [ ] Tested with occlusion or eye tracking, and against a physical-control baseline
- [ ] For two-wheelers: glove input, sunlight legibility, vibration, phone-off behaviour, signal loss

Standards behind several rules (ISO 15005, 15008, 16951, 2575, SAE J2364, J3016, JAMA) are paywalled and were not verified; where this skill cites them it says so.
