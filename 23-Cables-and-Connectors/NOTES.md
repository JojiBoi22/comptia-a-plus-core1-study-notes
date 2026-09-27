# Cables and connectors (Objectives 3.1, 3.2)

Yellow tab: **Cable Types**.

## Bits versus bytes

- **Bit (b)** = one 0 or 1. Speed on a wire is usually in **bits** per second.
- **4 bits** = one **nibble**.
- **8 bits** = one **byte (B)**. Disk size is usually in **bytes**.

Rule of thumb: divide bits by 8 to get bytes. Example: 1 000 bits ÷ 8 = 125 bytes.

| Name | About this many bits |
|------|----------------------|
| Kilobit (Kb) | 1 000 |
| Megabit (Mb) | 1 million |
| Gigabit (Gb) | 1 billion |
| Terabit (Tb) | 1 trillion |

**1 MB** (megabyte) ≈ 1 million **bytes** of stored data.

## USB versions

**USB** = Universal Serial Bus. One host controller runs the bus. Old spec allowed up to **127** devices on a tree (hubs, not a true daisy chain of 127 cables).

| Name you see | Older name | Transfer (marketing) |
|--------------|------------|----------------------|
| Low Speed | USB 1.0 | 1.5 megabits per second |
| Full Speed | USB 1.1 | 12 megabits per second |
| High Speed | USB 2.0 | 480 megabits per second |
| SuperSpeed / Gen 1 | USB 3.0 / 3.1 Gen 1 | 5 gigabits per second |
| SuperSpeed 10 / Gen 2 | USB 3.1 Gen 2 | 10 gigabits per second |
| SuperSpeed 20 / Gen 2x2 | USB 3.2 | 20 gigabits per second |
| USB4 | USB4 | 40 gigabits per second |

Cable length (typical rated):

- USB 1.0 ≈ 3 m (9 ft)
- USB 1.1 / 2.0 ≈ 5 m (15 ft)
- USB 3.x SuperSpeed ≈ 3 m (9 ft) unless an active / certified cable says otherwise

### USB shapes

- **Type-A** — flat rectangle on PCs. USB 1.x / 2.0 / 3.x (3.x Type-A is usually blue inside).
- **Type-B** — squarer plug on printers. Mini-B and Micro-B on older phones / cameras. USB 3 Type-B is a different, larger shape.
- **Type-C** — small oval, reversible. Phones, laptops, video + power + data.

Legacy serial (not USB): **DB-9** and **DB-25** D-shaped connectors on old consoles and modems.

## Video cables

- **HDMI** (High-Definition Multimedia Interface) — digital video + audio.
- **DisplayPort** — digital video + audio; common on PCs.
- **DVI** (Digital Visual Interface) — digital and/or analog pins.
- **VGA** (Video Graphics Array) — analog only, 15-pin blue.
- **Thunderbolt** — very fast; modern versions use the Type-C shape and can carry video, data, and power.
- **USB Type-C** with DisplayPort Alt Mode — video on a USB-C lead.

**HDCP** (High-bandwidth Digital Content Protection) — the player and the display shake hands so protected video (movies) will play. If HDCP fails you get a black screen or “HDCP error,” not a bad GPU.
