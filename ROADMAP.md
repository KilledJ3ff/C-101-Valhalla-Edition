# ROADMAP — CASA C-101 Valhalla Edition

> **Source of Truth:** This fork of FGMEMBERS/C-101, maintained under **Projeto Valhalla (NEXUS)**.
> **Status Convention:** ✅ = Implemented | 🟡 = Partial | ⬜ = Planned | 🔒 = Blocked

---

## Phase Overview

| Phase | Focus | Status | Notes |
|-------|-------|--------|-------|
| **P0 — Fork Baseline** | Fork of FGMEMBERS/C-101, rename to Valhalla Edition | ✅ Done | This repo |
| **P1 — 2026 Merged Build** | Merge 2015 BB/CC content onto 2023 airframe/cockpit | ✅ Done | 3 variants (EB/BB/CC) in one entry |
| **P2 — Cross-platform fixes** | Linux/macOS texture & light paths, cannon submodel path | ✅ Done | Validated on FG 2024.1 |
| **P3 — Cockpit Canvas** | NAV1, COM1, N1, N2, ITT canvas displays | ✅ Done | Working displays |
| **P4 — Armament (BB/CC)** | DEFA 553 cannon + SAAB RGS-2 gunsight with camera | ✅ Done | Installable/removable in flight |
| **P5 — Systems depth** | Fuel model, electrical, hydraulics, failure manager | 🟡 Partial | Basic systems present |
| **P6 — Avionics modernization** | GPS/FMS, moving map, MFD pages, datalink | ⬜ | Next major phase |
| **P7 — Tactical/DiEV** | MP validation, doctrine scenarios, Red Air profiles | ⬜ | With TACTICAL/DiEV alas |

---

## Detailed Tracking

### Variants
| Variant | Role | Engine | Thrust | Status |
|---------|------|--------|--------|--------|
| C-101EB | Trainer | Garrett TFE731-2 | 3,550 lb | ✅ |
| C-101BB | Armed trainer / attack | Garrett TFE731-3 | 3,700 lb | ✅ |
| C-101CC | Light attack | Garrett TFE731-5 | 4,700 lb | ✅ |

All three share one airframe model and the EB JSBSim aero model — performance differences come only from the engine definition.

### Cockpit & HMI
| Item | Status | Gap |
|------|--------|-----|
| Canvas displays (NAV1, COM1, N1, N2, ITT) | ✅ | Add MFD/GPS pages |
| SAAB RGS-2 gunsight (BB/CC) | ✅ | Camera view functional |
| Animated gear, doors, speedbrake, flaps | ✅ | — |
| Aerobatic smoke (EB) | ✅ | Key `e` |
| Pushback | ✅ | — |

### Weapons
| Item | Status | Gap |
|------|--------|-----|
| DEFA 553 cannon (BB/CC) | ✅ | Key `e`; submodels working |
| Bombs / rockets on hardpoints | 🟡 | Submodels exist; SMS page ⬜ |
| Gunsight install/remove | ✅ | Menu toggle `/sim/model/c101/sight` |

### Systems
| Item | Status | Gap |
|------|--------|-----|
| JSBSim FDM (shared EB aero) | ✅ | Per-variant engine only |
| Fuel (`Systems/Fuel.xml`) | 🟡 | Basic; no transfer/totalizer |
| Crash detect | ✅ | `Systems/Crash-detect.xml` |
| Multiplayer sync | ✅ | Surfaces, doors, cannon trigger |
| Electrical / hydraulics modeling | ⬜ | Not modeled in depth |
| Failure manager integration | ⬜ | — |

### Known Issues → Roadmap
| Issue | Phase |
|-------|-------|
| No FMS/GPS integrated | P6 |
| No MFD pages | P6 |
| Limited fuel/electrical depth | P5 |
| No failure injection | P5/P7 |

---

## Projeto Valhalla

| Ala | Role |
|-----|------|
| **NEXUS** | Engineering & systems development (this fork) |
| **TACTICAL** | Doctrine & TTPs |
| **DiEV** | Flight testing & certification |

---

## Links

- Changelog: [CHANGELOG.md](CHANGELOG.md)
- Upstream: https://github.com/FGMEMBERS/C-101
- FlightGear Wiki: https://wiki.flightgear.org/

---

*Last updated: 2026-11-07*