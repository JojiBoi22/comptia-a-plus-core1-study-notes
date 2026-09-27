# Troubleshooting networks (Objective 5.7)

Yellow tab: **Troubleshooting Networks**.

Buckets: wired link, performance, wireless, **VoIP** (Voice over Internet Protocol), limited connectivity, authentication.

## Wired path

Client **NIC** (network interface card) → patch lead → wall jack → cable in the wall → **patch panel** → switch (often 24 or 48 ports) → router / firewall / gateway → internet.

```mermaid
flowchart LR
  PC[PC + NIC] --> Wall[Wall jack]
  Wall --> Panel[Patch panel]
  Panel --> SW[Switch]
  SW --> R[Router / firewall]
  R --> Inet[Internet]
```

Test with a **cable tester** from wall jack to patch panel. A wire-map test checks every pair through the wall. If the jack is bad, re-terminate. Always replace a suspect patch lead first — it is the cheap part.

**NIC lights** (typical):
- Link light = layer-1 is up.
- No link = cable, port, or card.
- Activity blinks with traffic.
- Some cards show speed (10 / 100 / 1000 megabits per second).

**Cable length:** unshielded twisted pair is rated to **100 metres** end to end (PC → jack → panel → switch). Longer than that needs a switch or repeater, not hope.

## Interference and port flapping

Interference: power lines, fluorescent lights, motors, generators next to the cable.

**Port flapping** = link up/down/up. Causes: bad cable, external noise, dying NIC. Check switch logs for the port bouncing.

## Performance (slow)

**Duplex mismatch** on NIC or switch.

- **Half duplex** (old): send **or** receive, not both at once.
- **Full duplex:** send **and** receive at the same time.

Full duplex is normal on a switch. One half-duplex device on a switch port can wreck that port. Most NICs **auto-negotiate** when they first connect.

If speed falls after auto-negotiate:
- Log in and check both sides (NIC and switch).
- Set both to the same speed and full duplex, or leave **both** on auto.
- Update the NIC driver.

One client vs many clients:
- One PC: patch lead, wall path, ping the **DHCP** server, check **VLAN** (virtual LAN). A wrong VLAN can block DHCP so the PC never gets an address.
- Many PCs: DHCP server down, not plugged into the network, or **out of leases**. Grow the scope, or release stale leases.

## Limited connectivity / APIPA

The operating system shows a special message: physical link is up but there is no lease from DHCP, so you cannot reach past the local box.

Windows then gives an **APIPA** address (Automatic Private IP Addressing): `169.254.x.x`. That range is **only** for the local link. It is not valid on the internet. Linux often shows `0.0.0.0` until it has a real address.

## Quality of Service

To cut **latency** (delay) and **jitter** (delay that jumps around): raise overall capacity, and use **QoS** (Quality of Service) so voice and video jump the queue.

## Wireless

If the PC may have malware: take it off the LAN, boot to safe mode, scan with Windows Security plus a second tool.

Wireless problems split into: **interference**, **low signal**, **standards mismatch**.

**Interference:** neighbour access points, microwaves, Bluetooth, cordless phones, motors. Low **SNR** (signal-to-noise ratio), retries, drops.

Fix: Wi-Fi analyser. Move to a cleaner channel (1, 6, or 11 on 2.4 GHz) or to 5 GHz / 6 GHz. Relocate the access point away from noise. Turn transmit power down if cells overlap too much.

**Low signal:** distance, walls, metal, poor antenna aim.

Fix: move the client closer, raise or aim the access point, add another access point or mesh node or extender. Stay inside legal power limits.

**Standards mismatch:** client and access point do not share a band, security type, or channel width.

Fix: confirm both sides support the same band (2.4 / 5 / 6 GHz) and standard (n / ac / ax). Compatibility mode only if you must. For old devices, a **separate SSID**. Match encryption (WPA2 / WPA3) on both ends.

## VoIP

Voice over Internet Protocol = voice (and video) as data in real time. Most VoIP uses **UDP** (User Datagram Protocol).

Two quality killers:
- **Latency** — you hear your own voice as an echo.
- **Jitter** — words chop.

## Authentication failures

Causes: wrong password, config mismatch, expired or revoked account, network path down, bad certificate.

Eight-step check:

1. Verify the credentials.
2. Check account status (locked, expired).
3. Confirm the network path.
4. Inspect server settings.
5. Check the certificate dates and trust.
6. Read the logs.
7. Reset or reissue credentials.
8. Update authentication policy if it is the real problem.

Reduce repeats: strong password policy, **MFA** (multi-factor authentication), audit server settings so clients still match, teach users to spot phishing.
