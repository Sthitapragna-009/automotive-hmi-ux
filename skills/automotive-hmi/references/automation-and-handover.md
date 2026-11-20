# Driver assistance, automation and handover

Source types: **[REG]** · **[STD]** · **[RES]** · **[PRAC]** · **[INF]** (see SKILL.md).

## 1. Know the level

SAE J3016 defines Levels 0–5 (not re-verified for this repo; widely used). In practice:

| Level | Who drives | Who monitors | UI job |
|---|---|---|---|
| L0–L1 | Driver | Driver | Warnings and single assists (ACC *or* lane centring) |
| L2 | Driver with combined assistance | **Driver, always** | Show what the system is doing; keep the driver engaged |
| L3 | System, within conditions | System; driver must respond to a takeover request | Clear availability, handover with enough time |
| L4–L5 | System | System | Passenger information, remote help, minimal-risk stops |

**Never name or market an L2 system as if it drives itself.** IIHS's safeguard ratings and the Tesla recall both target misuse that names and weak cues encourage [STD/REG].

## 2. Regulation and ratings

- **UN R171 (DCAS, in force Sep 2024)**: Level 2 systems must monitor engagement using **eye gaze and head posture, not steering torque alone** [REG, secondary] ([Applied Intuition](https://www.appliedintuition.com/blog/navigating-dcas-regulations)).
- **UN R157 (ALKS, Level 3, from 22 Jan 2021; EU cars from 22 Jan 2022)**: speed limit raised from 60 to 130 km/h; a **10-second transition demand** before handing back [REG, secondary] ([Wikipedia: ALKS](https://en.wikipedia.org/wiki/Automated_lane_keeping_system)).
- **IIHS safeguard ratings (2022)**, criteria for "good" [STD] ([IIHS](https://www.iihs.org/news/detail/iihs-creates-safeguard-ratings-for-partial-automation)):
  - Monitors eyes on the road and hands on or ready to grab the wheel.
  - Alerts begin and **escalate quickly** through more channels.
  - On no response, slows to a crawl or stop, and **locks the driver out of the feature for the rest of the drive**.
  - Automated lane changes are initiated or confirmed by the driver.
  - ACC doesn't resume automatically if the driver isn't looking at the road.
  - Not usable with the seat belt unfastened or with AEB or lane departure warning off.
  - Steering is shared rather than switching off when the driver steers.
- **Euro NCAP 2026**: five-star cars need camera-based driver monitoring; lane support adapts to whether the driver is attentive or distracted [STD].
- **EU GSR2** driver drowsiness and advanced distraction warning (DDAW/ADDW) dates were not verified.

## 3. The Tesla recall lesson

NHTSA recall 23V-838 covered **2,031,220 vehicles**: Autosteer's controls "may not be sufficient to prevent driver misuse". The remedy: more prominent visual alerts, simpler engagement and disengagement, extra checks off controlled-access highways, and suspension for drivers who repeatedly fail to stay engaged [REG] ([NHTSA recall report](https://static.nhtsa.gov/odi/rcl/2023/RCLRPT-23V838-8276.PDF)).

Rule: **mode prominence is a safety requirement, not styling.**

## 4. Mode display [INF, from Airbus, Bainbridge, IIHS and the recall]

Design every state, in the cluster **and** the HUD, with distinct shape and colour, not just colour:

| State | Display |
|---|---|
| Off | Nothing, or a neutral icon if available |
| Available | Outline icon |
| Active | Filled icon + what it is controlling (speed, lane, gap) + lane lines in the graphic |
| Degraded / limited | Icon changes + text ("Lane lines unclear") |
| Driver attention needed | Escalation sequence (below) |
| Takeover requested | Full-width message, time remaining, sound and haptics |
| Minimal-risk manoeuvre | "Stopping the car" + hazards on + outside indication |
| Locked out | "Unavailable for this drive" + why |

Airbus's golden rules apply directly: "Understand the FMA [mode annunciator] at all times" and "Use the appropriate level of automation at all times" [PRAC] ([Airbus/ICAO](https://www2023.icao.int/ESAF/Documents/meetings/2017/AFI%20FOSAS%202017/Day%201%20Docs/Day_1_2_Airbuspihlo.pdf)). Bainbridge: systems should **fail visibly** and always tell the human what the automation is handling [RES] ([Bainbridge 1983](https://gwern.net/doc/sociology/technology/1983-bainbridge.pdf)).

## 5. Escalation sequence [INF from IIHS]

1. Visual cue in the cluster/HUD when attention drops.
2. Audible chime + text.
3. Haptic (seat or wheel) + louder sound.
4. Slow down, hazards on, stop in lane or move to the shoulder (where capable); call for help if no response.
5. Lock the feature out for the rest of the drive, and say why next time.

Keep steps short (seconds, not tens of seconds) and attention-adaptive: earlier for distracted drivers, fewer nuisance alerts for attentive ones (Euro NCAP 2026).

## 6. Takeover (handover) design

- Eriksson & Stanton (2017, *Human Factors* 59(4)): in non-critical conditions drivers took **1.9 to 25.7 s** to resume control; longer when reading; a 7 s lead time produced stressed, abrupt manoeuvres [RES] ([TRID](https://trid.trb.org/view/1468236)).
- Design for the long tail: at least the regulatory 10 s for L3, with a minimal-risk manoeuvre ready if nobody responds [REG/INF].
- The takeover request says **why** and **what to do** ("Road works ahead. Take the wheel."), shows time remaining, and confirms when the driver has control ("You're driving"). [INF]
- After handover, keep assistance (lane departure warning, AEB) on.
- Bainbridge's ironies of automation: drivers lose skill and vigilance fades after about half an hour of monitoring a reliable system; takeovers are the hardest moments. Training and periodic engagement matter [RES] ([The Morning Paper on Bainbridge](https://blog.acolyer.org/2020/01/08/ironies-of-automation/)).

## 7. Warnings for collisions and hazards [INF; primary research not gathered]

- Forward collision warnings are multimodal (visual + sound, optionally haptic), located near the line of sight (HUD or top of cluster).
- One warning at a time, by priority; never stack two urgent sounds.
- Nuisance alerts train drivers to switch systems off; tune thresholds and give feedback when a driver dismisses repeatedly.
- Haptic seat warnings and AR-HUD hazard highlighting were not researched for this repo.
