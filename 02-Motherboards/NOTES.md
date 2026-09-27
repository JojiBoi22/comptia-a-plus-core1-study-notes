# Motherboards and processors (Objective 3.5)

The **motherboard** is the backbone for power, data, and sockets. Pick the board **first** when you build — memory type and storage connectors must match it.

## Four jobs around the processor

| Job | Meaning |
|-----|---------|
| **Input** | Accept data in a form the processor can use |
| **Processing** | The **CPU** (central processing unit) acts on that data |
| **Output** | Result leaves through the board to screen, disk, network |
| **Storage** | Keep data a short time in **cache** or **RAM** (random access memory), or for good on a disk |

## Form factors (board size and hole pattern)

Form factor = shape, screw layout, case, and power-supply style.

| Name | Size (inches) | Size (mm) | Notes |
|------|---------------|-----------|-------|
| **ATX** (Advanced Technology eXtended) | 12 × 9.6 | 305 × 244 | Full desktop, rear port cluster |
| Mini-ATX | 11.2 × 8.2 | 284 × 208 | Same idea, slightly smaller |
| Micro-ATX | 9.6 × 9.6 | 244 × 244 | About four expansion slots |
| Mini-ITX (Information Technology eXtended) | 6.7 × 6.7 | 170 × 170 | Small / home theatre / embedded |

Even smaller ITX cousins: nano, pico, mobile-ITX for appliances.

## CPU sockets

**ZIF** (Zero Insertion Force) lever: lift, drop the chip in flat, close. Do not bend pins.

- **Intel LGA** (Land Grid Array) — pins live **on the board**.
- **AMD PGA** (Pin Grid Array) — pins live **on the chip** (example AM4). Newer AMD also uses LGA (AM5).

## Processor features

- **SMT** (Simultaneous Multithreading) / Intel **Hyper-Threading**: one physical core runs two instruction streams. Software must be multi-thread aware or you still have one busy thread.
- **SMP** (Symmetric Multiprocessing): two or more **physical packages** on one board (2 or 4 sockets). All chips must match; the operating system must support it.
- **Multi-core**: several cores in **one** package (dual / quad / hexa / octa). Can combine with SMT (8 cores + SMT ≈ 16 threads).
- **Virtualization**: Intel **VT-x** plus **EPT** / **SLAT**; AMD **AMD-V** plus **RVI** / **SLAT**. Needed for VMware, VirtualBox, Hyper-V to run well. Enable in firmware.

### Architecture

Fetch → decode → execute in the **ALU** (arithmetic logic unit) / **FPU** (floating-point unit) → write result.

| Family | Meaning |
|--------|---------|
| **x86** (IA-32) | 32-bit. Rough ceiling ~4 GB RAM |
| **x64** (AMD64 / Intel 64) | 64-bit. Today’s desktop standard |
| **ARM** (RISC) | Smaller instruction set, low power and heat. Phones and many laptops |

## Connectors on an ATX / B550-style board

- CPU socket + ZIF lever
- **DIMM** slots (RAM)
- **24-pin ATX** main power
- **8-pin (4+4) EPS** processor power
- 4-pin fan headers (CPU_FAN, SYS_FAN / CHA_FAN)
- **SATA** data ports (7-pin L)
- **M.2** for NVMe or SATA SSDs
- **PCIe** slots
- Front-panel headers: USB, audio, power switch, LEDs
- **CMOS** battery keeps firmware settings and clock
- Rear I/O: USB 2 / 3 / C, HDMI, and so on

## Expansion slots

Legacy: **PCI**, **PCI-X**, **AGP** (Accelerated Graphics Port).

**PCIe** (Peripheral Component Interconnect Express):

- **x1** short — NIC, sound, capture (slot gives about **25 W**)
- **x16** long — graphics. Slot can supply about **75 W**; hungry cards need extra 6-pin / 8-pin power from the PSU
- **Mini-PCIe** — Wi-Fi / WWAN in laptops
