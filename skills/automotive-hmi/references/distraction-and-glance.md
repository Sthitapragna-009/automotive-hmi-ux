# Distraction, glances and controls

Source types: **[REG]** · **[STD]** · **[RES]** · **[PRAC]** · **[INF]** (see SKILL.md).

## 1. NHTSA Visual-Manual Driver Distraction Guidelines (2013)

Voluntary, for vehicles up to 10,000 lb GVWR; the most widely used numeric baseline [STD] ([Federal Register text via Justia](https://regulations.justia.com/regulations/fedreg/2013/04/26/2013-09883.html)).

| Rule | Value |
|---|---|
| Single glance away from the road | ≤ 2 s |
| Total eyes-off-road per task | ≤ 12 s |
| Occlusion test | Task completable in 1.5 s glances with ≤ 12 s total shutter-open time |
| Hands | One hand only |
| Interruptibility | Every task can be paused at any time |
| Display placement | Display centre within 30.00° below the driver's horizontal line of sight (2D method) or 28.16° (3D) |
| "Driving" for lockouts | Propulsion on and transmission not in Park |

**Lock while driving**: video not related to driving; auto-scrolling text; manual text entry for text messaging or web browsing; reading books, web pages, social media or text messages. The final text dropped the proposed 30-character reading allowance, so "short text is fine" is not a safe reading [STD].

Also from the proposal, not confirmed in the final text: an acceptance test where at least 21 of 24 participants meet the criteria with no more than 15% of glances over 2 s, and a six-key-press limit [STD, unverified]. Other often-cited figures — JAMA (Japan) 8 s total glance, SAE J2364 "15-second rule" — were not verified for this repo.

## 2. Turning budgets into design [INF]

- Write a **task inventory**: every task, its frequency, driving state, and glances needed. Anything that cannot meet 2 s / 12 s moves to voice, a physical control, automation, or "available when parked".
- Make tasks **resumable**: leaving mid-task and coming back returns to the same place.
- Lockouts say why and offer an alternative: "Available when parked. Ask the assistant to read it?"
- Passengers: a passenger-side screen may run content that is locked for the driver only if the driver cannot see it.

## 3. Physical controls (Euro NCAP 2026)

From 2026, Euro NCAP scores whether these use a **direct physical input** rather than a touchscreen menu [STD] ([Euro NCAP](https://www.euroncap.com/en/press-media/buttons-are-back-for-basic-functions-euro-ncap-confirms-in-testing/); [ETSC](https://etsc.eu/euro-ncap-new-2026-protocols-target-distraction-impairment-and-speeding/)):

1. Turn indicators
2. Windscreen wipers and washer
3. Hazard lights
4. Horn
5. SOS / eCall button

First results: Audi Q7 100% on essential tasks, XPENG X9 20%, Leapmotor B05 0%. Five-star ratings also require camera-based eye and head tracking, and lane-support warnings must adapt to attentive vs distracted drivers.

**Control map** [INF, supported by J.D. Power and OEM reversals]:

| Physical (always) | Physical (strongly preferred) | Touch / voice OK | Parked only |
|---|---|---|---|
| The five above, gear, parking brake, steering-wheel volume and next/previous | Climate temperature and fan, defrost, volume knob, drive mode | Navigation destination (voice), media browsing (limited), phone (voice) | Settings, account, long text, video, app stores, payments |

J.D. Power's 2025 Initial Quality Study found infotainment the most problematic category at 42.6 problems per 100 vehicles, with touchscreen complaints rising as climate and other controls moved on-screen [PRAC] ([Business Wire](https://www.businesswire.com/news/home/20250626729527/en/Fewer-Physical-Vehicle-Controls-and-More-Problematic-Touchscreen-Make-Infotainment-System-a-Modern-Catch-All-Drawer-J.D.-Power-Finds)).

## 4. Platform limits

**Android for Cars** [STD] ([design principles](https://developer.android.com/design/ui/cars/guides/foundations/design-principles); [template restrictions](https://developer.android.com/training/cars/apps/library/template-restrictions)):

- Common tasks in **3 taps or fewer**.
- At most **5 templates per task**; the fifth must be a terminal template, or the host closes the app.
- Text while driving: **1–3 lines, ≤ 120 characters**.
- Notifications suppressed during manoeuvres; UI adapts to driving state; easy to pause and resume.
- List caps (often cited as 6 items) and touch-target sizes (often cited as 76 dp) were not verified.

**Apple CarPlay**: CarPlay Ultra (May 2025) extends to the instrument cluster and coexists with physical controls [PRAC]. CarPlay HIG numbers were not verified for this repo.

## 5. Benchmark: buttons vs touchscreens

Vi Bilägare (2022) timed four routine tasks at 110 km/h in 12 cars [PRAC, magazine test] ([Vi Bilägare](https://www.vibilagare.se/english/physical-buttons-outperform-touchscreens-new-cars-test-finds)):

| Car | Time | Note |
|---|---|---|
| Volvo V70 (2005, buttons) | 10.0 s | Baseline |
| Volvo C40 | 13.7 s | Best touchscreen |
| Tesla Model 3 | 23.5 s | |
| VW ID.3 | 25.7 s | |
| BMW iX | 30.4 s | |
| MG Marvel R | 44.9 s | 1,372 m travelled at 110 km/h (the article's text says 44.6 s) |

Downward gaze to reach the bottom of each screen ranged from 20° to 56°.

Lesson [INF]: task depth and placement matter more than "screen vs button". Reuse this four-task protocol (for example: adjust temperature, turn on seat heating, set radio station, reset trip meter) as a regression test for every release.

## 6. Testing methods

- **Occlusion** (glasses or shutters that open for 1.5 s): total shutter-open time ≤ 12 s.
- **Eye tracking** in a simulator or on track: single glances ≤ 2 s; count long glances.
- **Lane-keeping and speed variation** as secondary measures (ISO 26022 lane change test; not verified).
- Test with older drivers, new drivers, and at night.
