# LEGO Technic 42114 — Volvo Articulated Hauler (A60H)

Design brief for an ldraw-nova agent / modular LDraw rebuild, driven from the official building instructions PDF.

## Subject

- **Set:** 42114 LEGO Technic Volvo Articulated Hauler
- **Scale:** Technic (not minifig); full functional model with motors, gearboxes, articulated joint, 6×6 drive, dump bed
- **Palette:** Yellow body (LEGO colour 14 / Bright Yellow), Black (0), Dark Bluish Gray (72) / Light Bluish Gray (71) structure, Orange (4) accents (rails, beacon), Blue friction pins (often 1 or 23 for long pins in instructions callouts)
- **Power:** 2× Large Angular Motors (bag 1) + hub (later bags); app control via Control+

## Modules (match PDF bag overview, pages 4–5)

| Module | PDF bag | Role | Origin / envelope |
|--------|---------|------|-------------------|
| `rear-gearbox-core` | 1 early | Nested 5×7 frames, gear stacks, motor mounts | Rear drivetrain centre |
| `rear-chassis` | 1 | Full rear frame, axles, wheel hubs, longitudinal beams | Negative Y up; length along +X |
| `front-chassis-cab` | 2 | Cab frame, steering, front axle, articulation half | Articulation interface aft |
| `articulation-joint` | 2–3 | Turntable / pivot between front and rear | Shared origin on pivot axis |
| `body-panels-cab` | 3 | Black/yellow cab cladding, A60H stickers | Attached to front structure mounts |
| `dump-bed` | 4 | Dump body, lift mechanism, rear axle trio | Hinge mounts on rear chassis |
| `wheels-tires` | 1–4 | 6× wheel/tire assemblies | Axle ends |

## Build order (from PDF)

1. Bag 1: rectangular Technic frames → stacked core → gear trains → motor wiring path → rear longitudinal chassis.
2. Bag 2: cab skeleton + front driveline + second motor area + join to rear via articulation.
3. Bag 3: cab skin, mirrors, lights, Volvo branding surfaces.
4. Bag 4: dump bed structure, lift, remaining wheels, finish.

## Focal features

- Working 6×6 drive with differentials / reduction (visible gear cages in PDF steps ~17–80).
- Articulated steering joint between cab and rear.
- Powered dump bed raise/lower.
- App-controlled motors (not simulated in static LDraw; model as mounted motors + cable paths).

## Constraints for the agent

- Follow `instructions.md`, `docs/agent/technic.md`, and `docs/agent/plans.md`.
- Prefer measured Technic ports from the registry; seat pins before closing frames.
- Split into sections with unique `.ldr` names; use anchors at articulation and dump hinge.
- Do not invent part IDs; use real LDraw `.dat` names.
- Physical validity remains **not_proven** after automatic checks.

## Deliverables

- Modular `*.plan.json` sources under this folder
- Built `.mpd` after `./ldraw-agent build`
- `technic check` contracts for static frames
- Review folder with previews opened and notes
