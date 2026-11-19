# Roadmap

Plan horizon: **December 2026 → March 2027 (4 months)**, plus a sketch of what comes after.
Every phase ends with a **gate**. If we don't pass the gate, we don't move on.

---

## Horizons at a glance

| Horizon | When | Goal | Exit gate |
|---|---|---|---|
| **Short term: MVP** | Months 1–2 | A stock DJI Flip carries a can, receives an RF command and sprays reliably in a tethered test | 10/10 triggers on the bench, 5/5 in a tethered hover, weight and flight-time data published |
| **Mid term: Field proof** | Months 3–4 | First free-flight mark on an **authorised** mural; 3D-printed remote v1; our own mount design | Signed wall permission, documented flight, repeatability data, beta kit BOM |
| **Long term: Product** | Month 5+ | A safe, legal, sellable "for DJI Flip" kit with a responsible-use programme | Regulatory path confirmed per launch market, insurance, safety testing, artist pilot results |

---

## Known risks (read these first)

1. **Payload.** The DJI Flip is a sub-250 g drone that isn't designed to carry payloads. A full aerosol can may simply be too heavy. We will measure the real lift limit before designing around it, and we'll consider mini cans (50–150 ml) or partly filled cans.
2. **Weight class.** Any attachment pushes the Flip over 250 g. That changes registration, Remote ID and operating category in most countries. See [RESPONSIBLE_USE.md](RESPONSIBLE_USE.md).
3. **Hazardous materials.** Aerosol paint is a flammable compressed gas. Some regulators treat carrying it on a drone as hazmat carriage. This could be the biggest blocker to selling the product.
4. **Open-model licences.** Many printable spray-can triggers are released under *CC BY-NC*. We can test them, but **we can't sell them**. The product mount has to be our own design.
5. **RF coexistence.** The Flip links on 2.4/5.8 GHz. The trigger link should avoid those bands. Sub-GHz (433/868/915 MHz, depending on region) is preferred.

---

## Short term: MVP (Months 1–2)

### Month 1: December 2026. *"Bench"*
**Objective:** choose the attachments, buy the parts, prove that a servo can press a can on the bench.

- **Down-select 2–3 open designs** from public repositories (Printables, Thingiverse, etc.), favouring lightest mass, simple servo lever, top-mount vs. under-slung variety. Log each design's licence.
- **Buy the cheap kit** (target ≤ €120 / $130 total):
  - 3–5 micro servos specified by the chosen designs (e.g. SG90 / MG90S class)
  - Sub-GHz RF pair: 2 small MCU boards + 433/868/915 MHz transceivers, *or* a ready-made RF remote + receiver driven by an MCU
  - 1S LiPo cells (≤ 300 mAh) + small boost/BEC for the servo
  - Big arcade-style push button, project box, jumper wires
  - Mini spray cans (several sizes), PLA/PETG filament, 0.1 g digital scale, luggage scale
- **Print** all 2–3 attachments; measure printed mass.
- **Bench test:** servo force vs. can nozzle force; 20 actuations per design.
- **Lift test:** tethered/caged Flip with dummy weights to find the real payload ceiling and flight time per added gram.

**Gate 1:** at least one design actuates 20/20 on the bench, and its total mass (mount + servo + RF + battery + can) is under the measured lift ceiling with margin.

### Month 2: January 2027. *"Tether"*
**Objective:** integrate everything on the drone and fire it remotely in a controlled hover.

- Flash minimal firmware: button press → RF packet → servo pulse, with a **dead-man default** (servo returns to rest when the link drops).
- Build the **clunky button MVP**: a box with a big button, an arm switch and a status LED. It doesn't need to look good.
- Mount on the Flip; check centre of gravity, prop-guard clearance and downwash on the spray pattern.
- **Tethered hover tests** in open space, on scrap board or cardboard, never near people.
- Down-select to **one** attachment for the field.
- Start the legal homework: national aviation authority classification, insurance quotes, and a first conversation with a mural owner.

**Gate 2:** 5/5 tethered remote sprays, a published test log, and a mural owner willing to sign the permission template.

---

## Mid term: Field proof (Months 3–4)

### Month 3: February 2027. *"First Wall"*
- **First authorised mural flight**, with written owner permission, applicable aviation permissions, a spotter, a cordoned area and a fire extinguisher on site.
- **3D-printed remote activator v1**: a handheld shell around the RF electronics, with a trigger-style button, an arm toggle and a lanyard. This is our **optics piece** for photos, videos and social posts.
- **Mount v2: our own design**, informed by the MVP lessons (lighter, quick-release, licence-clean).
- Publish a short build video and test report.

### Month 4: March 2027. *"Repeat"*
- **Repeatability campaign:** 10+ logged flights covering accuracy, drift, flight time, nozzle clogging and wind limits.
- **Remote v2** with improved ergonomics, battery-level indicator and link-status feedback.
- **Assemble 3–5 beta kits** and hand them to vetted artists for supervised use.
- Publish v0.1 of the **Responsible Use Kit**: legal guide, permission template, pre-flight checklist.
- **Go/no-go review** for the product phase: payload, legality per market, cost per kit.

**Gate 3:** documented free-flight marks on an authorised wall, a beta BOM with cost, and a written regulatory pathway for at least one launch market.

---

## Long term: Product (Month 5+)

- **Regulatory:** formal legal opinion per launch market; exemptions/authorisations where required (e.g. hazmat carriage, specific-category operations); product liability insurance.
- **Hardware:** quick-release mount, weight-optimised actuator, integrated remote, colour-swap cartridges, possibly a non-aerosol paint path to reduce hazmat exposure.
- **Responsible-use programme:** kit registration, an in-box permission template, a "permitted wall" photo log for artists' portfolios, and a public stance on misuse.
- **Artist programme:** commissioned showcase murals, partnerships with festivals and city mural programmes, a gallery of authorised work.
- **Commercial:** small-batch run, direct sales, open-source files remain available for non-commercial use.

---

## Budget snapshot (Months 1–4)

| Item | Est. cost |
|---|---|
| Servos, RF boards, LiPos, button, wiring | €40–60 |
| Filament (PLA/PETG) | €20–40 |
| Mini spray cans, nozzles, test boards | €30–50 |
| Scales, tether line, safety (extinguisher, PPE, cones) | €40–70 |
| Beta kits (×3–5) | €100–200 |
| Insurance / permit fees | varies by country, **budget for it** |
