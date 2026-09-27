# Network servers and services (Objective 2.3)

A **client** asks. A **server** answers with a service.

## File and print

On the LAN: Windows uses **SMB** (Server Message Block) on port 445. Older name services: **NetBIOS** on 137/139. Linux can speak SMB with **Samba** so Windows PCs can map a drive letter.

On the internet: **FTP** (ports 20/21) is clear text — anonymous only, or use **SFTP** (FTP through SSH) / **FTPS**. Cloud print: job goes to a vendor server, then back to the office printer.

## Web servers

**HTTP** port 80, **HTTPS** port 443 (certificate + encrypted tunnel). Software: Microsoft **IIS** (Internet Information Services), **Apache**, **Nginx** (also a reverse proxy / load balancer).

Pages are **HTML / CSS / JavaScript**. Browser sends GET.

**FQDN** (fully qualified domain name) = host + domain + TLD, example `www.diontraining.com`. **URL** (uniform resource locator) = protocol + FQDN, example `https://www.diontraining.com`. Look for the padlock.

## Mail servers

- **SMTP** port 25 — **send** between domains (“Send Mail” memory trick).
- **POP3** port 110 — download to one PC; often deletes from server.
- **IMAP** port 143 — mailbox stays on the server; good for many devices.
- **Exchange** — Microsoft’s mail product; still uses those protocols underneath.

## AAA — authentication, authorization, accounting

One box (or service) that:
1. **Authenticates** — proves who you are (password, MFA, certificate).
2. **Authorizes** — what you may do after login.
3. **Accounts** — logs what you did.

## Database

Stores records in tables that programs query. Business apps almost always talk to a database server, not a flat file.

## NTP — Network Time Protocol

Keeps every clock the same. Certificates, logs, and Kerberos logins break if clocks drift.

## Syslog

Devices send their log lines to one collector so you can search in one place.

## Proxy

Sits between users and the internet. Can cache pages, filter sites, hide internal addresses.

## Load balancer

Spreads requests across several identical servers so one box is not crushed. Often sends you to the nearest healthy copy.

## UTM — unified threat management

One appliance that stacks firewall + antivirus + anti-spam + VPN + content filter + IPS (intrusion prevention) + DLP (data loss prevention).

Pros: cheaper and simpler for a small office. Cons: **single point of failure** — if it dies, every function dies; not as deep as a dedicated next-generation firewall on a huge network.

Sits between the LAN and the internet, same place as a classic firewall.

**ACL** (access control list): allow/deny rules, first match wins, specific rules at the top.

## ICS / SCADA (operational technology)

**OT** (operational technology) drives the physical world. **IT** is office computers.

- **ICS** (industrial control system): one plant — valves, pumps, power.
- **DCS** (distributed control system): several ICS units in one site.
- **SCADA** (supervisory control and data acquisition): many sites over a WAN (smart meters on cellular).

Building blocks: **PLC** (programmable logic controller) + **Fieldbus** + **HMI** (human-machine interface — screens and buttons).

In OT, **availability** beats confidentiality. A down plant loses money; the old networks were not on the public internet.

## Embedded systems

A computer with **one job** (drip counter, smart meter). Often a **static** image that is rarely patched.

- **PLC** firmware — patches are rare.
- **RTOS** (real-time operating system) — answers in milliseconds; no casual reboot (aircraft, plant).
- **SoC** (system on a chip) — whole computer on one chip (robot vacuum).

Put them on their **own** network. Do not hang a 20-year-old meter on the office Wi-Fi.

## Legacy and proprietary

**Legacy** = vendor gone, no patches (Windows XP still in some plants). Compensate: isolate, firewall, no internet.

**Proprietary** = only the original vendor can patch, on their schedule. Plan for slow fixes.
