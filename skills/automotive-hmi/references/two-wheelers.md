# Motorcycles and scooters

Source types: **[REG]** · **[STD]** · **[RES]** · **[PRAC]** · **[INF]** (see SKILL.md).

**Evidence warning.** No peer-reviewed glance data for riders was found, and NHTSA's distraction guidelines do not cover motorcycles. Riders have less margin than drivers: two wheels, exposure to weather and no protective shell. Car thresholds below are **borrowed and labelled as such**; treat them as upper limits, not targets.

## 1. Context that changes everything [INF]

- Gloves (thick, wet, cold), so touchscreens are unreliable while riding.
- Vibration blurs small text.
- Direct sunlight and glare on the display; helmet visors tint and reflect.
- Head movement is constrained; glances down mean losing peripheral view of the road.
- Noise: audio needs a helmet intercom; haptics through the bars are weak.
- Phones mounted on handlebars or in pockets, with screens off.

## 2. Product precedents [PRAC]

**Royal Enfield Tripper Dash** ([Royal Enfield](https://www.royalenfield.com/in/en/tripper-dash)):

- 4-inch round TFT; one joystick controls everything, "so the phone doesn't need to be taken out".
- Default **Analog mode** with turn-by-turn only; **Digital mode** with a full map is opt-in.
- Automatic day/night from a light sensor.
- Turn-by-turn continues with the phone screen off; the last route stays without signal; around 25 waypoints.
- iPhone users get fewer features than Android users, and the product says so.

**AtherStack 7** (May 2026): built-in voice, Google Maps with two-wheeler routing, Fall Safe, an emergency stop signal, theft and tow alerts, and OTA updates [PRAC, press] ([DriveSpark](https://www.drivespark.com/two-wheelers/2026/ather-stack-7-top-5-features-that-make-ather-scooters-smartest-in-india-084875.html)).

## 3. Rules [INF unless marked]

1. **One glove-friendly physical input** (joystick, rocker or 4-way switch with a centre press) on the left bar; no touch while moving.
2. **Glance mode by default**: speed, gear, next turn, fuel/charge, warnings. Everything else on demand or when stopped.
3. **Borrowed budgets**: no single glance over 2 s and no more than 12 s per task (car figures, NHTSA) — aim far lower; design tasks as one or two presses.
4. **Large, high-contrast type** sized for vibration; tabular figures for speed; test in direct sun with a tinted visor.
5. **Auto day/night**, and a manual override.
6. **Navigation survives**: phone screen off, signal loss, app in background. Show the last instruction and distance even when data drops.
7. **Notifications**: calls show caller and accept/decline via the switch or intercom; messages are never shown as text while riding; read aloud only on request.
8. **Safety features** (fall detection, emergency contacts, theft and tow alerts, crash SOS) are part of the dashboard and companion app, with a countdown to cancel false alarms.
9. **Tell-tales** follow car colour conventions (`clusters-hud-and-visual.md`) and sit where they can't be confused with navigation.
10. **Be honest about platform gaps** (as Royal Enfield is for iOS).

## 4. Not yet researched

Helmet HUDs, rider glance studies, India AIS/BIS two-wheeler display rules, Ola MoveOS, BMW Motorrad Connected, Ducati, TVS, Bajaj. Contributions with primary sources are welcome.
