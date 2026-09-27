# Printer types (Objective 3.8)

Maintenance differs by engine. Know the parts and the safe steps.

## Laser — toner powder + heat

The whole page is rendered in memory first (not line-by-line). If only half a page prints, add printer memory.

Parts: imaging **drum**, **fuser** (hot roller + pressure roller), transfer belt/roller, pickup rollers, separation pad, optional **duplexer** (flips the page).

Toner is plastic + carbon (+ colour pigment). Small printers combine toner + drum; office printers sell them separately (drum lasts ~4× longer).

Colour uses **CMYK**: cyan, magenta, yellow, black (K).

### Seven-step EP (electrophotographic) process

1. **Processing** — driver sends a **PDL** (page description language); printer builds a bitmap.
2. **Charging** — primary charge roller / corona wire puts a uniform negative charge on the drum.
3. **Exposing** — laser writes the image by neutralizing spots on the drum.
4. **Developing** — toner sticks to those spots.
5. **Transferring** — paper gets a positive charge; toner jumps from drum to paper.
6. **Fusing** — heat + pressure melt toner into the fibres.
7. **Cleaning** — blade scrapes leftover toner; drum is ready again.

```mermaid
flowchart LR
  P[Process] --> C[Charge]
  C --> E[Expose]
  E --> D[Develop]
  D --> T[Transfer]
  T --> F[Fuse]
  F --> CL[Clean]
```

### Laser maintenance

Power off and **cool** first. Fuser burns. Corona is high voltage.

- Paper: correct weight, fan the stack, set guides, store dry. Light paper double-feeds; thick paper jams.
- Toner: starter cartridge is short. Shake gently side-to-side to use the last powder. Bag the old cartridge. Never hot-water a toner stain (it sets). Toner-safe vacuum only — no compressed air (you will breathe dust).
- **Maintenance kit:** pickup/transfer rollers + fuser after a page-count. Reset the counter.
- **Calibrate** if colour looks wrong.
- Recycle toner as hazardous waste per local rules.

## Inkjet — liquid drops

Print head sprays CMYK (and sometimes extra tanks). Head can be in the cartridge or fixed in the printer.

Maintenance: replace cartridges / tanks, run a **nozzle check** and clean cycle if lines are missing, use the cap/park position so heads do not dry. Do not let an inkjet sit unused for months.

## Thermal — receipts

A heated line cooks coating on special paper. No ink. Used at tills.

Maintenance: correct thermal paper (shiny side toward the head), clean the heating bar, clear crumbs from the feed. Paper that is the wrong type prints blank or grey.

## Impact / dot-matrix

Pins smack an inked **ribbon** onto paper. Low DPI (about 100–240) but it can print **carbon / multi-part forms** in one pass. **Tractor feed** = holes on the paper edges.

Used in workshops, warehouses, clinics.

Maintenance: replace the ribbon cassette (not refillable), replace a worn **print head** (cool it first — it gets hot), load tractor paper on the sprockets and lock the flaps.

## 3D printers

Build a real object, layer by layer, from a sliced 3D model (USB, Wi-Fi, or SD card). Home units are slow (a cup can take a day).

Parts: heated **bed / build plate**, grip surface, **extruder** (melts and squirts), motors on X/Y/Z, cooling fans.

**Filament** (the “ink”): usually **PLA** or **ABS** plastic on a spool, 1.75 mm or 3 mm. Match nozzle and bed temperatures to the plastic. Fine nozzles = detail and clogs.

Some machines use liquid **resin** cured by ultraviolet light instead of filament.
