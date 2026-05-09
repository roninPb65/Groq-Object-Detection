# Detection Modes

Vision AI Surveillance has four modes, each with a tailored AI prompt optimized for the use case.

---

## GENERAL Mode

**Best for:** Everyday use, testing, general surveillance

The AI analyzes the scene and returns:
- `SCENE` — one-sentence scene description
- `OBJECTS` — comma-separated list of all detected objects
- `DETAILS` — 2–3 notable observations
- `ALERT` — urgent issues (or "none")

**Example output:**
```
SCENE: Indoor office environment with multiple workstations visible
OBJECTS: desk, computer monitor, keyboard, office chair, person, window, lamp
DETAILS: One person seated at a workstation facing a monitor. Natural light coming from the window on the left. The room appears tidy with organized desk surfaces.
ALERT: none
```

---

## DRIVING Mode

**Best for:** Dashcam, in-vehicle use, traffic monitoring

The AI acts as a driving safety assistant and returns:
- `SCENE` — road and environment description
- `OBJECTS` — all vehicles, pedestrians, cyclists detected
- `SIGNS` — traffic signs or signals visible
- `HAZARDS` — potential dangers or proximity concerns
- `ALERT` — urgent safety warnings
- `GUIDANCE` — one actionable driving tip

**Example output:**
```
SCENE: Urban intersection with moderate traffic, daytime, clear visibility
OBJECTS: 3 cars, 1 bus, 2 pedestrians crossing, cyclist on right lane
SIGNS: Red traffic light ahead, "STOP" sign on right, 30 km/h speed limit sign
HAZARDS: Cyclist merging into lane approximately 15m ahead
ALERT: Cyclist in blind spot — check mirrors before lane change
GUIDANCE: Reduce speed and yield to cyclist before proceeding through the intersection
```

### Mounting for Driving Mode

**Phone:**
- Use a windshield or dashboard mount with the camera facing forward
- Open the app in your mobile browser (Chrome on Android, Safari on iOS)
- Landscape orientation gives the best field of view

**Laptop:**
- Place on the dashboard facing forward (passenger-side only)
- Do not position where airbag deployment is possible

> ⚠️ **Legal notice:** Laws about in-vehicle cameras and driver assistance technology vary by region. Check local regulations. This app is an AI assistant tool and does not replace driver judgment or mandatory safety systems.

---

## SECURITY Mode

**Best for:** Home surveillance, office monitoring, entry-point watching

The AI returns:
- `SCENE` — location and environment description
- `PERSONS` — count and general description of people (no identification)
- `ACTIVITY` — what's happening in the frame
- `ENTRY POINTS` — visible doors, windows, access areas
- `ALERT` — suspicious activity or security concerns

**Example output:**
```
SCENE: Residential front entrance area, evening, exterior lighting active
PERSONS: 1 person — adult, standing near front door
ACTIVITY: Person appears to be unlocking door with keys
ENTRY POINTS: Front door (center), ground-floor window (left)
ALERT: none
```

### Privacy Notice

Security mode deliberately avoids identifying individuals. The AI describes people only in general terms (count, general appearance, activity). This app does not store, record, or transmit video — analysis is done per-frame via the Groq API.

---

## CUSTOM Mode

**Best for:** Specialized tasks, research, teaching, accessibility

The AI provides a comprehensive freeform description of everything visible. Use the chat interface to give specific instructions:

**Example custom instructions via chat:**
- `"Focus only on reading any text visible in the frame"`
- `"Tell me what plants you can identify"`
- `"Describe the lighting setup for photography purposes"`
- `"Count all people wearing red"`
- `"Is this room ADA accessible? What do you see?"`

---

## Switching Modes

Modes can be switched at any time using the tab buttons at the top. The AI will immediately apply the new mode's prompt on the next analysis cycle.

The auto-analysis timer resets on mode switch to allow you to reposition before the next scan.
