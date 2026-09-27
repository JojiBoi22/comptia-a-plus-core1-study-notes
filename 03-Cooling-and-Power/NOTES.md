# Cooling and power (Objectives 3.5, 3.6)

Heat path: hot chip → **thermal paste** (thin grease that fills gaps) → metal heatsink → air or liquid → out of the case.

```mermaid
flowchart LR
  CPU[Processor] --> Paste[Thermal paste]
  Paste --> Sink[Heatsink]
  Sink --> Air[Fans move air]
  Air --> Exhaust[Rear or roof exhaust]
```

- **Active air cooling:** heatsink plus fan. Plug the processor fan into the **CPU_FAN** header on the motherboard. Front of case = intake, rear/top = exhaust.
- **AIO** (all-in-one liquid cooler): pump on the block, tubes to a radiator with fans. Better for hot chips; watch for leaks; the pump needs power.
- Firmware fan profiles: quiet / balanced / cool.

## Power supply unit (PSU)

The box that turns wall alternating current into the direct-current voltages the PC uses.

- **80 PLUS** rating = how efficient it is at turning wall power into PC power. It is **not** “more watts.”
- **Modular** cables unplug if unused (easier airflow). Non-modular cables are all permanently attached.

Connectors:
- **24-pin ATX** — main board power.
- **8-pin EPS** — extra processor power.
- **6-pin / 8-pin PCIe** — extra graphics-card power.
- **SATA** power — drives.
- **Molex** — older 4-pin devices.

Voltage **rails** (the named outputs):
- **+12 volt** does most of the heavy work today (processor, graphics, fans, disks).
- **+5 volt** and **+3.3 volt** for logic.
- **+5 volt standby** stays on so the board can wake from sleep.

Size the unit with headroom (typical draw plus about 20–30%). Match the **115 / 230 volt** switch to your wall, or use an auto-switching unit.

Install: screw the unit to the case, connect 24-pin and processor 8-pin first, then drives and graphics, keep cables out of the airflow.
