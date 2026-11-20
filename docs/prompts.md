# Prompts to try

Copy any of these into Claude once the skill is installed. Claude loads it on its own when the task is about a vehicle interface.

## Get better answers

Tell Claude four things up front. If you leave one out, the skill makes Claude state its assumption at the top of the answer.

| Say | Why it matters | Example |
|---|---|---|
| **Vehicle and market** | Euro NCAP, UN regulations, NHTSA and platform rules differ | "EU-market compact EV", "Indian 125 cc scooter" |
| **Surface** | Each has its own limits | cluster, centre screen, HUD, CarPlay / Android Auto, Android Automotive app, two-wheeler TFT, companion phone app |
| **Driving state** | Decides what's allowed and the glance budget | parked, driving, L2 hands-on, L2 hands-off, L3 |
| **What you want back** | Screens, a state map, copy or an audit | "every state with the copy for each" |

Paste screenshots or photos taken at the driver's seat for audits. Claude reviews what it can see.

## Infotainment and controls

- Design the climate controls for a car with one central touchscreen. What has to stay physical?
- Audit this infotainment screen against the 2-second glance rule and Euro NCAP 2026 physical-control requirements.
- Which of these 30 settings should be locked while driving, and what should the locked state say?
- Redesign this media screen so every frequent task takes three taps or fewer.

## Clusters and HUDs

- Design the instrument cluster for an EV: speed, range, regen, tell-tales and navigation, in day and night palettes.
- What should the speed-limit display show when the camera can't read a sign?
- Design a HUD layout that shows navigation and ADAS state without cluttering the driver's view.

## Driver assistance and automation

- Design the ADAS takeover request for an L2 car, from first cue to escalation.
- Design every automation state (off, available, active, degraded, takeover requested, minimal-risk manoeuvre) in the cluster and HUD.
- Our driver monitoring flags inattention. Design the escalation sequence with timings and the lockout after repeated misuse.

## Voice and assistants

- How should an in-car voice assistant confirm an action that changes how the car drives?
- An LLM assistant can change climate, navigation and settings. Design how it shows what it changed and lets the driver undo.

## EV, OTA and companion apps

- Design the range and charging-stop view for a long trip, showing uncertainty honestly.
- Write the copy and flow for an over-the-air update that moves a control the driver uses every day.
- Design remote unlock and digital-key sharing in the companion app.

## Two-wheelers

- Design a scooter dashboard that's readable in direct sunlight and works with gloves.
- Design turn-by-turn navigation for a motorcycle TFT with a phone connected over Bluetooth.
- Design fall detection and crash SOS with a countdown that prevents false alarms.

---

Got a prompt that worked well? Open a pull request and add it here.
