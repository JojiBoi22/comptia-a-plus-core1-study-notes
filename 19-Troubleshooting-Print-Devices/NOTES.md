# Troubleshooting print devices (Objective 5.6)

Yellow tab: **Troubleshooting Print Devices**.

## Print path words

- **Print driver** — turns the document on the PC into a language the printer understands.
- **Print queue** — list of waiting jobs created by the operating system.
- **Print spooler** — service that holds jobs on disk and feeds them to the printer.
- **Print monitor** — software that sends the job to the printer and reports status back to the user.

```mermaid
flowchart LR
  App[Application] --> Drv[Driver]
  Drv --> Q[Queue / spooler]
  Q --> Mon[Print monitor]
  Mon --> Ptr[Printer]
```

## Connectivity

Operating system does not see the printer, frozen queue, test the link, then **power cycle** (off, wait, on). If that fails, factory **reset** the printer.

Printer shows **offline** even when plugged in:
- Out of paper
- Feed error
- Corrupted job sitting in the queue

Network printer will not connect:
- Failed to get an address from **DHCP** (Dynamic Host Configuration Protocol)
- Fix: assign a static address, or fix DHCP

### Frozen queue

Causes: corrupted job, dropped connection, software glitch.

Fix:
1. Cancel jobs in Printer settings / Printer properties.
2. Restart the **Print Spooler** service (Windows Services → Print Spooler → Restart).
3. Update or reinstall the driver.

## Paper feed

Symptoms: jams, nothing feeding, two sheets at once, grinding, tray not recognised.

| Symptom | What to try |
|---------|-------------|
| Jam | Read the printer panel. Pull the tray. If paper is deeper, open the other covers. Pull **with** the path, not against it. |
| Not feeding | Worn pickup rollers. Load the tray square. Try different paper. Check guides. |
| Multi-page misfeed | Damp or wrong-weight paper. Fan the stack. |
| Grinding | Look at carriage, gears, rollers. Find the noise before you replace parts. |
| Laser (toner, fuser, roller) | Inspect and replace worn parts. Fuser is hot — let it cool. |
| Tray not seen | Paper seated correctly. Dust in the sensors. Reset tray type in the menu. |

## Print quality

Faded pages, white or black stripes, speckling, toner sitting loose (not fused), wrong colours, ghosting, blank pages, missing dots or characters.

Checks in order:

1. Ink / toner level. Shake a laser cartridge side to side.
2. Impact: platen gap and ribbon. Replace ribbon if faded.
3. Tape still on a new cartridge?
4. Dirty drum? Clean carefully. If toner is everywhere, replace drum or cartridge.
5. Inkjet: nozzle check, then clean cycle if jets are clogged.
6. Laser: inspect corona / charge wire; replace drum or toner.
7. Clean the inside with a **toner-safe vacuum**. Clean or replace feed rollers. Photosensitive drum: replace if scratched.
8. Fuser voltage / heat: if toner rubs off, replace the fuser.
9. Right cartridge in the right slot. Update driver (host restart).
10. Empty cartridge: replace it. Clean contacts between cartridge and printer.
11. Check spooler and printer settings.
12. Replace a damaged print head.

## Finishing

Wrong page size, wrong orientation (portrait vs landscape), staple / punch problems, white banding on finished sets. Fix in driver preferences and the MFD finishing menu. Confirm paper size matches the tray.
