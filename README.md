# 42114 Volvo Articulated Hauler — ldraw-nova plan package

Reconstructed from the official LEGO Technic 42114 building instructions PDF (6332383, 456 pages), following the **ldraw-nova** agent workflow (`instructions.md`, `docs/agent/plans.md`, `docs/agent/technic.md`).

## What’s here

| File | Purpose |
|------|--------|
| `BRIEF.md` | Design brief: modules, palette, bag map, constraints |
| `STEPS.md` | **Complete step outline** — detailed transcription of steps 1–56 + full high-level map of steps 57–end with PDF page ranges and major sub-assemblies |
| `scene.plan.json` | Top-level scene (includes modules) |
| `modules/rear-gearbox-core.plan.json` | Bag 1 early steps: stacked 5×7 frames + side beams (steps 1–8 core) |

## How to build (on a machine with ldraw-nova set up)

```bash
export LDRAW_DIR=/path/to/ldraw
cd /path/to/ldraw-nova
./setup.sh   # if needed

# Build the core module
./ldraw-agent build /path/to/42114-volvo/modules/rear-gearbox-core.plan.json \
  --output output/42114-rear-gearbox-core.mpd

# Or the scene
./ldraw-agent build /path/to/42114-volvo/scene.plan.json \
  --output output/42114-volvo.mpd

# Review (geometry + previews)
./ldraw-agent review output/42114-rear-gearbox-core.mpd \
  --outdir output/42114-rear-gearbox-core-review

# Technic structural check (after adding a structure contract)
./ldraw-agent technic check output/42114-rear-gearbox-core.mpd \
  --contract /path/to/contract.json
```

Open every PNG under `previews/` before accepting. Automatic checks do **not** prove physical buildability.

## PDF mapping (official instructions)

- **Pages 1–3:** Cover, app QR, bag overview.
- **Pages 4–5:** Bag 1 → rear drivetrain; bag 2 → cab + join; bag 3 → cab body; bag 4 → dump bed + finish.
- **Pages 6–38:** Steps 1–56 — 5×7 frames, pins, 11-hole yellow beams, gear stacks, axles (detailed in `STEPS.md`).
- **Pages 38–110:** Steps 57–~175 — complete rear gearbox + longitudinal chassis + wheel hubs + motors (Bag 1).
- **Pages ~110–220:** Steps ~174–~350 — front chassis, cab skeleton, second motor, articulation joint (Bag 2).
- **Pages ~220–320:** Steps ~350–~550 — cab body panels, cladding, details (Bag 3).
- **Pages ~320–440:** Steps ~550–~680 — dump bed, lift, remaining wheels, finish (Bag 4).

## Next agent steps

1. Extend `rear-gearbox-core` with PDF steps 9–56 (gear/axle subassemblies) using the detailed STEPS.md entries.
2. Add `rear-chassis.plan.json` for longitudinal beams and wheel hubs (steps 80–175).
3. Add `front-chassis-cab.plan.json` with articulation anchor matching rear.
4. Mechanism studies for dump lift and differentials via `mechanism export` patterns.
5. Full `review` + visual notes; keep `physical_validity: not_proven`.

Request any specific range (e.g. “write detailed steps 57–80”) for full part lists + plan JSON expansions.

## Part ID notes

Common refs used / planned:

- `64179.dat` — Technic Beam Frame 5×7 Open Center  
- `2780.dat` — Technic Pin with Friction Ridges  
- `6558.dat` — Technic Pin Long with Friction  
- `32525.dat` — Technic Beam 1×11  
- `43093.dat` — Technic Axle Pin with Friction  
- `32054.dat` — Technic Pin Long with Bush / axle-pin variants  
- `3713.dat` — Technic Bush  
- `18946.dat` — Technic Gear 16 Tooth with Clutch  
- `15462.dat` — Technic Axle 5.5 with Stop  

Verify every ID against the installed LDraw library before treating the plan as final. Coordinates are approximate LDU placements derived from hole pitch (20 LDU) and PDF step order; refine with `./ldraw-agent connectors` / `snap` once geometry is built.

## Attribution

Official set and instructions © LEGO Group. This package is an unofficial fan reconstruction for use with open LDraw tooling (ldraw-nova). Not sponsored or authorized by LEGO.
