# MatMod v0 — Build Spec

**A 3D-printable module that turns your existing desk mat into a charging surface.**

No new mat. No adhesive. No drill. One USB-C in, one USB-C out.  
Snaps magnetically through the mat. Remove it any time, zero marks left behind.

---

## What It Is

A two-part printed enclosure that sandwiches your desk mat using embedded neodymium magnets. The top module sits on the mat surface and exposes two USB-C ports. The anchor plate rides underneath. They hold together through 2–6mm of mat material without any fasteners.

Inside lives a USB-C female-to-female coupler — the only non-printed component other than the magnets. Wall adapter plugs into one port. Laptop USB-C cable plugs into the other. That's the entire circuit.

```
[Wall adapter] ──USB-C──▶ [MatMod IN port] ═══ coupler ═══ [MatMod OUT port] ──USB-C──▶ [Laptop]
                                          ↕ magnet sandwich ↕
                                          [Desk mat material]
                                          [Anchor plate underneath]
```

---

## Bill of Materials

| Part | Spec | Qty | Approx. Cost |
|------|------|-----|------|
| USB-C female-to-female coupler | USB-C barrel coupler, USB 3.2 Gen 2 rated | 1 | $4–8 |
| Neodymium magnets | N52, 10mm diameter × 3mm thick | 8 | $5–9 |
| PETG filament | Any brand, any colour | ~25g | $1–2 |
| (Optional) Heat-shrink or foam tape | Coupler retention backup | — | <$1 |

**Total BOM: ~$10–20**

No PCB. No soldering. No firmware.

---

## 3D Print Specs

| Parameter | Value | Notes |
|-----------|-------|-------|
| Material | PETG | Preferred — heat tolerant, slight flex for snap-fit |
| Alternative | PLA+ | Works, less heat tolerant near hot adapters |
| Layer height | 0.15mm | For clean port openings and magnet pocket walls |
| Infill | 20% gyroid | Sufficient for a static housing |
| Perimeters/walls | 3 | Ensures magnet pockets are solid |
| Supports | None | Parts designed to print support-free |
| Bed adhesion | Brim | Anchor plate especially — large flat first layer |
| Print temp (PETG) | 235°C nozzle / 70°C bed | Adjust ±5°C per brand |
| Cooling | 50% fan | Balances layer adhesion vs. bridging quality |

---

## Dimensions

### Top Module (sits on mat surface)

```
         80mm
    ┌────────────────┐  ─┐
    │  [USB-C OUT]   │   │ 20mm
    │                │   │
    │  [USB-C IN ]   │  ─┘
    └────────────────┘
         40mm depth
```

| Dimension | Value |
|-----------|-------|
| Width | 80mm |
| Depth | 40mm |
| Height | 20mm |
| USB-C port opening | 10.5mm W × 4mm H (chamfered entry 1mm) |
| Magnet pockets | 4× recesses, 10.3mm dia × 3.2mm deep |
| Magnet pocket positions | 15mm from each corner, centred on base face |
| Internal cable channel | 12mm W × 8mm H, runs full depth |
| Wall thickness (minimum) | 1.8mm |

**Port placement:** IN port on rear face (wall side). OUT port on left or right face (laptop side). User chooses orientation at print time — two variants, mirrored.

### Anchor Plate (under mat)

| Dimension | Value |
|-----------|-------|
| Width | 80mm |
| Depth | 40mm |
| Height | 3mm |
| Magnet pockets | 4× recesses, 10.3mm dia × 3.2mm deep |
| Magnet pocket positions | Mirrors top module exactly |

The anchor plate is intentionally minimal — flat slab with magnet pockets. No features. No branding. You never see it.

---

## Magnet Placement

8 magnets total. 4 in the top module (base face, pressing down through mat). 4 in the anchor plate (pressing up). Orientation: **alternate polarity** in each pair so they attract through the mat, not repel.

```
Top module base:    N  S  N  S   (pressed into pockets, flush with face)
                    ↕  ↕  ↕  ↕   (through mat)
Anchor plate top:   S  N  S  N   (attracted to top module)
```

**Mat thickness compatibility:**
- 2–3mm (leather pads): full pull strength, very secure
- 4–5mm (neoprene): good pull strength, recommended
- 6mm+ (thick rubber-base): reduced hold; add 2 extra magnets or use M3 bolt variant (see below)

**Hold strength estimate:** 8× N52 10mm×3mm through 4mm material ≈ 2.5–3.5 kg pull. Enough to resist laptop cable tugging. Not enough to hold if the whole mat is yanked.

---

## Assembly

1. Press magnets into top module pockets. Check orientation — they should attract toward the floor (toward the mat), not repel.
2. Press magnets into anchor plate pockets. Check orientation matches top module.
3. Optional: add a small dab of super glue to each pocket after confirming polarity. Magnets can walk out under vibration.
4. Thread USB-C coupler into internal cavity from the port face. It should sit flush with the port openings. Friction-fit is designed tight; if loose, wrap coupler body once with electrical tape.
5. Close and snap lid (lid is a snap-fit cover over the cable channel — printed separately, no fasteners).
6. Place anchor plate under your mat at desired location.
7. Lower top module onto mat — magnets grab through the mat and snap it into position.
8. Plug wall adapter into IN port. Plug laptop USB-C cable into OUT port.

---

## Coupler Spec Note

The USB-C female-to-female coupler carries whatever your wall adapter negotiates with your laptop — USB PD up to 100W (or 240W with USB PD 3.1 adapters). The coupler is not the limiting factor; your wall adapter and laptop are.

For a trickle-charge-during-work use case (target: 15–30W), any USB-C coupler rated USB 3.2 Gen 2 or better is fine. Avoid generic couplers marked only "USB 2.0" — they may not carry PD negotiation signals correctly.

Recommended test: plug adapter → coupler → laptop *before* inserting into enclosure. Confirm laptop charges. Then assemble.

---

## Variants Planned

| Variant | Change | Status |
|---------|--------|--------|
| v0 (this) | Magnetic sandwich, single coupler | Spec complete |
| v0-bolt | M3 bolt variant for thick mats | Spec planned |
| v1 | Inductive Qi transmitter built in, magnetic alignment for laptop receiver | Concept stage |
| v1-gamer | v1 + heat pipe routing, RGB LED status indicator | Concept stage |

---

## Files

```
matmod-v0/
├── README.md           (this document)
├── stl/
│   ├── top-module-left.stl      (OUT port on left)
│   ├── top-module-right.stl     (OUT port on right, mirrored)
│   ├── lid.stl
│   └── anchor-plate.stl
├── step/
│   ├── top-module.step
│   ├── lid.step
│   └── anchor-plate.step
└── bom.csv
```

> **Status:** Dimensions and specs finalised. CAD files in progress.

---

## License

CERN Open Hardware Licence Version 2 — Permissive (CERN-OHL-P v2).  
Build it, sell it, modify it. Attribution appreciated.

---

## Why

The G14 is the best laptop I've ever owned. Most days I use my MacBook instead because the G14 charger is a 180W brick. This is the first step toward fixing that — not with new technology, but with a piece of plastic, some magnets, and a $6 coupler. If it works, we build the inductive version. If that works, we build the product.

Build logs and devlog: [hackaday.io/project/tiredofwires]  
GitHub: [github.com/darthcoder/matmod]
