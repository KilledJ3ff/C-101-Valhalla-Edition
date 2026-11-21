# CHANGELOG — CASA C-101 Valhalla Edition

> Change register of the **Valhalla Edition** fork vs the upstream FGMEMBERS/C-101 (ViveFG Hangar).
> Maintained by **Projeto Valhalla — NEXUS**.

---

## [2026-11-19] — 3D cockpit mouse interaction

### Added
- **Clickable 3D cockpit controls** (`Models/cockpit_PILOT.xml`, +479 lines): landing gear lever, parking brake, flaps lever/placards, canopy levers (front & rear), altimeter QNH knob (28–31 inHg), HSI course/OBS knob, heading bug knob, COM1/NAV1 volume knobs, pitch trim wheel, nav/beacon/formation light switches
- Rotary knobs as `<type>knob</type>` animations: mouse wheel both directions, left click/hold increases, middle click decreases, drag turns
- Hover tooltips showing current state of each control
- README: new "Mouse in the 3D cockpit" section documenting all clickable controls

### Fixed
- `Models/cockpit_INT_FG.ac` minor adjustments
- VLH liveries (CC): line-ending normalization

---

## [Valhalla Edition — 2026 merged build]

### Added
- **C-101BB and C-101CC variants** grafted onto the 2023 airframe/cockpit (from the 2015 package):
  external detail sets, DEFA 553 cannon, SAAB RGS-2 gunsight, engine data, liveries
- Variant grouping: single launcher entry with variant selector (EB / BB / CC), per-variant previews
- Installable/removable gunsight (BB/CC) — menu toggle `/sim/model/c101/sight`, blocks forward view by design
- Canvas cockpit displays: NAV1, COM1, N1, N2, ITT
- Animated gear, doors, speedbrake, flaps; aerobatic smoke (EB); pushback
- Multiplayer sync: control surfaces, doors, cannon trigger
- Per-variant liveries (FACH, FAH, RJAF, Patrulla Águila, festive schemes)

### Fixed
- Gear-helper polygons in `Models/CASA_C-101.ac`: absolute macOS texture path → `Textures/Default.png`
- Light model paths: Windows backslashes → forward slashes (beacon/nav/taxi lights now work on Linux/macOS)
- Cannon submodel: non-existent `Models/Geometry/null.ac` → `Models/Armament/DEFA553/null.ac`

### Changed
- 2023 airframe/cockpit is the base for all variants; BB/CC reuse the EB JSBSim aero model
- Minimum FlightGear version declared as 2020.3; validated on 2024.1

---

## [Upstream history] (FGMEMBERS/C-101 / ViveFG Hangar)

- **2011–2013** — Original aircraft, flight model, models and liveries: Pavel Cueto, Fernando Espinosa
- **2015** — BB/CC attack variants package (DEFA 553, RGS-2 gunsight, detail sets, liveries)
- **2020** — External model and cockpit update: John Bray ("Warty")
- **2023** — Updated external model, current cockpit with canvas instruments

---

## Statistics

| Metric | Upstream | Valhalla Edition |
|--------|----------|------------------|
| Variants | 1 (EB) | 3 (EB/BB/CC) |
| Canvas displays | 0 | 5 (NAV1, COM1, N1, N2, ITT) |
| Cannon | none | DEFA 553 (BB/CC) |
| Gunsight | fixed | installable/removable |
| Cross-platform fixes | Windows paths | Linux/macOS validated |

---

## Credits

- **Valhalla Edition fork & 2026 merge** — **Killed J3ff**
- **2020 model/cockpit update** — John Bray ("Warty")
- **Original C-101 (2011–2013)** — Pavel Cueto, Fernando Espinosa

## License

GNU GPL v3 — see `LICENSE` / `COPYING.txt`.

---

*Last updated: 2026-11-07*