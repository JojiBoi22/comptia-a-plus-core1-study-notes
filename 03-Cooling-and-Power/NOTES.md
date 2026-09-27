# Cooling and power (Objectives 3.5, 3.6)

Yellow tab: **Cooling and Power**.

Heat comes mainly from the **CPU**, **GPU** (graphics), voltage regulators, and the **PSU** (power supply unit). Cooling keeps parts in a safe range so they do not throttle or die.

## Air cooling

- **Passive**: metal fins only (low-power chips).
- **Active**: heatsink **plus fan**.

Air path: cool air in the **front / bottom** → across parts → hot air out the **rear / top**.

Positive pressure (a bit more intake than exhaust) helps keep dust out.

**Thermal paste** fills microscopic gaps between the chip lid and the heatsink.

### Install an active cooler

1. Clean old paste with isopropyl alcohol.
2. Pea-size new paste (or the pattern the cooler maker shows).
3. Seat the cooler. Tighten screws in a cross pattern.
4. Plug the fan into **CPU_FAN** (processor) or **SYS_FAN / CHA_FAN** (case).
5. Check firmware temps and RPM after boot. If the cooler is loose, reseat it.

## Liquid cooling

- **AIO** (all-in-one / closed loop): pump + block + tubes + radiator + fans.
- **Custom loop**: reservoir, pump, blocks, radiator — more performance and more leak risk.

Liquid takes heat from the block to the radiator; fans dump it into air.

Pros: quieter under load, good for high **TDP** (thermal design power) chips, clean look.  
Cons: leak, pump failure, cost, radiator still needs case airflow. Mount the AIO radiator as exhaust so heat leaves the case.

## Power supply unit

Converts wall **AC** (alternating current) to **DC** (direct current) the PC uses.

Form factors: **ATX**, **SFX**, and similar. Look for **80 PLUS** on the label — that is **efficiency**, not extra watts. Modular cables unplug if unused.

### Connectors (use only what you need)

- **24-pin ATX** — main board
- **4+4 / 8-pin EPS** — extra CPU power
- **6-pin / 8-pin PCIe** — extra GPU power
- **SATA** power (15-pin) — disks
- **Molex** (4-pin) — older drives, some fans, adapters
- **Berg / floppy** (tiny 4-pin) — rare now
- Front-panel and case fans often take power from **motherboard headers**, not from the PSU directly

### Input / output voltage

- Wall input: **115 V or 230 V**. Set the red slide switch, or use an auto-switching PSU. Wrong setting can destroy the unit.
- DC rails the PC uses:
  - **+12 V** — CPU, GPU, most motors and drives (the heavy rail)
  - **+5 V** — some older logic, USB
  - **+3.3 V** — motherboard logic, RAM, PCIe
  - **+5 VSB** (standby) — stays on for wake / power button even when the PC looks off
  - **−12 V** — legacy, almost unused

Rails should stay inside ATX spec (about **±5%**).

### Wattage rating

Rated wattage = maximum the unit can deliver **continuously**, not a burst.

Size the PSU to what the PC actually draws, plus **20–30%** headroom. GPU and CPU eat most of the budget. A little oversize is safer than 100% load (shutdowns, instability, early PSU death). Check the **+12 V** rail amps on the label.

### Install a PSU

1. Power off, unplug, disconnect old cables.
2. Match fan orientation to the case (fan toward a vent).
3. Screw the unit in.
4. 24-pin to the board, 8-pin (4+4) to the CPU corner.
5. PCIe power to the graphics card, SATA / Molex to drives.
6. Route cables so they do not block fans.
7. Check the voltage slide.
8. Plug wall AC last. Confirm case fans spin on first boot.
