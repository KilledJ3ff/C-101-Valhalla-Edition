# CASA C-101 Aviojet — Valhalla Edition

##### Two-seat jet trainer / light attack aircraft for FlightGear — Valhalla Edition fork.

[![FlightGear](https://img.shields.io/badge/FlightGear-2020.3%2B%20%2F%202024.1-blue.svg)]()
[![FDM](https://img.shields.io/badge/FDM-JSBSim-green.svg)]()
[![License](https://img.shields.io/badge/License-GPL--3.0-red.svg)]()

> **Valhalla Edition** — fork of FGMEMBERS/C-101 maintained under **Projeto Valhalla** (ala NEXUS).

Two-seat jet trainer / light attack aircraft built by CASA (Construcciones Aeronáuticas S.A.).
This package contains three variants sharing one airframe model and one JSBSim flight model,
differing in engine data, external details, armament and liveries.

| Variant | Role | Engine | Thrust |
|---|---|---|---|
| C-101EB | Trainer | Garrett TFE731-2 | 3,550 lb |
| C-101BB | Armed trainer / attack | Garrett TFE731-3 | 3,700 lb |
| C-101CC | Light attack | Garrett TFE731-5 | 4,700 lb |

In the launcher the aircraft appears as **one entry**; pick the variant (EB / BB / CC) from the
variant selector. Each variant has its own preview picture.

## About this build

This is a merged build (2026) that combines two packages:

* the **2023 package** — updated external model and the current cockpit with canvas instruments;
* the **2015 package** — the C-101BB and C-101CC attack variants (external detail sets, DEFA 553
  cannon, SAAB RGS-2 gunsight, engine data and liveries).

The 2023 airframe/cockpit is the base; the BB/CC specific parts were grafted onto it. Both BB and CC
reuse the EB JSBSim aero model and differ only in engine definition, so handling is very similar
across the three variants.

### Features

* Updated external model (2020) and detailed cockpit with working canvas displays
  (NAV1, COM1, N1, N2, ITT).
* BB/CC: DEFA 553 cannon and SAAB RGS-2 gunsight with camera.
* Gunsight can be installed/removed in flight (see below).
* Per-variant liveries (FACH, FAH, RJAF, Patrulla Águila, festive schemes, ...).
* Animated gear, doors, speedbrake and flaps; aerobatic smoke (EB); pushback.
* Multiplayer: control surfaces, doors and cannon trigger are shared.

## Controls

| Key | Action |
|---|---|
| `e` | EB: aerobatic smoke on/off — BB/CC: DEFA 553 cannon trigger |
| `d` | open/close front cockpit |
| `Shift` + `d` | open/close rear cockpit |
| `l` | landing lights |
| `Ctrl` + `b` | speedbrake |

### Aircraft menu (BB / CC)

* **Aircraft lights**
* **Select Livery**
* **Pushback**
* **Gunsight (install / remove)** — toggles `/sim/model/c101/sight`

The gunsight is installed by default on BB/CC. Removing it clears the forward view; it blocks part of
the view by design, as on the real aircraft. The toggle is local (not transmitted in multiplayer).

## Installation

Copy the `C-101` folder into your aircraft folder (e.g. `Addons/` or `Aircraft/`), or point
FlightGear at the folder that contains it:

```
fgfs --fg-aircraft=/path/to/Addons --aircraft=1981_C-101BB
```

Set files:

* `1977_C-101EB-set.xml` (base variant)
* `1981_C-101BB-set.xml`
* `1986_C-101CC-set.xml`

## Notes and known issues

* All three variants were validated with FlightGear 2024.1 (no missing models, textures or lights).
  Minimum version is declared as 2020.3.
* Gear-helper polygons in `Models/CASA_C-101.ac` used to point at an absolute macOS texture path;
  they now use `Textures/Default.png`.
* Light model paths in the shared model file used Windows backslashes, which made beacon/nav/taxi
  lights fail on Linux/macOS. Fixed in this build.
* The cannon submodel pointed at a non-existent `Models/Geometry/null.ac`; it now points at
  `Models/Armament/DEFA553/null.ac`.
* BB/CC use the EB aero model, so performance differences come only from the engine definition.

## Development

- **Roadmap:** See [ROADMAP.md](ROADMAP.md)
- **Changelog:** See [CHANGELOG.md](CHANGELOG.md)
- **Design docs:** Obsidian Vault `Valhalla/Nexus/` (Projeto Valhalla)
- **Upstream:** https://github.com/FGMEMBERS/C-101

## Credits

* **Valhalla Edition fork** — **Killed J3ff** (Projeto Valhalla — NEXUS)
* **Original aircraft, flight model, models and liveries (2011–2013)** —
  Pavel Cueto, Fernando Espinosa
* **2020 external model and cockpit update** — John Bray ("Warty")
* **2026 merge of the 2015 BB/CC content onto the updated airframe, installable gunsight, variant
  grouping and fixes** — Killed J3ff

## License

GNU General Public License v3. See `LICENSE` and `COPYING.txt`.
This package is derived from the original CASA C-101 Aviojet for FlightGear and remains under the
same license.
