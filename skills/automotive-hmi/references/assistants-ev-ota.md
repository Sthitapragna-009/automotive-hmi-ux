# Voice and AI assistants, EVs, OTA and companion apps

Source types: **[REG]** · **[STD]** · **[RES]** · **[PRAC]** · **[INF]** (see SKILL.md).

## 1. Voice and LLM assistants

- Assistants are moving from about 20 scripted commands to multi-turn LLM agents: Mercedes' MBUX Virtual Assistant runs on Google's Automotive AI Agent; BMW's new assistant uses an Amazon LLM [PRAC] ([R&D World](https://www.rdworldonline.com/mercedes-shifts-from-voice-commands-to-agentic-copilots/)).
- Android for Cars: voice for frequent tasks; show a visible microphone state while listening [STD].

Rules [INF]:

- Voice is the default way to do over-budget tasks while driving, but voice still costs attention; keep dialogues short and confirm actions in one turn.
- **Agent actions are visible**: when the assistant changes settings, navigation or climate, show what changed in the cluster or centre display, with one-tap undo.
- Safety-critical functions (driving modes, ADAS settings, door locks while moving) are not changed by voice alone without confirmation.
- Payments in the car: read back the amount and payee, and confirm on a screen when parked. The full payment rules are in [criticalUX](https://github.com/Sthitapragna-009/Critical_UX) money-flows.
- Calibrate trust: say when the assistant isn't sure, and offer choices ([Google PAIR](https://pair.withgoogle.com/chapter/explainability-trust/)).
- Cognitive-load research on in-car voice (AAA Foundation, University of Utah) was not gathered for this repo.

## 2. EV range, charging and regen

**Not yet researched with primary sources.** Working rules [INF]:

- Show range as a range when uncertain ("180–210 km"), with what affects it (temperature, speed, climate), never a single precise number when the estimate is uncertain.
- State of charge as percentage and distance; the arrival state of charge on every route.
- Route planning includes charging stops with expected charge time, charger availability (with freshness: "Updated 2 min ago") and a plan B.
- Charging session: connector status, power now, time to target, cost so far (formatted in the local currency, with the total visible), and a clear "Charging stopped" reason.
- Regen level visible and changeable with a physical control or paddle.
- Low-range warnings are tiered; the last one routes to the nearest charger, not just an alarm.

## 3. Over-the-air updates

Rules [INF]:

- Never update while driving; schedule for parked times with an estimate and a "car can't be used during update" warning.
- Release notes in plain language, with what moved. PhonePe used release notes, interstitials and onboarding animation to keep familiar flows learnable after a redesign [PRAC] ([PhonePe Design](https://design.phonepe.com/stories/behind-phonepe-redesign)).
- **Never move or relabel safety-relevant controls in an update without transitional help**; prefer not moving them at all.
- Roll back on failure and tell the driver what happened.

## 4. Companion phone apps

- Remote unlock, climate and charging are high-stakes: confirm the action and show the car's state after it (locked, unlocked) with time.
- Location sharing and access sharing (digital keys) need clear consent: who, what, for how long, and revoke in one tap.
- Theft and tow alerts include "This is me" and "Call help" actions.
