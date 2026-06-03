# Silicon Teardown

Silicon Teardown is a single-file, no-build interactive concept tool styled as a military **recognition manual** crossed with an **exploded engineering teardown** (Jane's meets iFixit). You pick one of three notional US guided-weapon classes (a man-portable guided missile, a JDAM-class GPS tail kit, and a small ISR/loitering UAV), "explode" it into a chip **bill-of-materials** tree, inspect each component's function / process node / (illustrative) supplier-fab-country / chokepoint exposure, and watch a transparent **Fragility Score** react in real time when you sever a semiconductor chokepoint — visibly demonstrating the supply-chain cascade.

## How to run

No build step, no dependencies beyond Google Fonts (loaded via CDN).

- Open `index.html` directly in a browser, **or**
- Serve it: `python3 -m http.server` then visit `http://localhost:8000`.

Deploys to Vercel as a static site (just the `index.html`).

## What's real vs. illustrative

**ILLUSTRATIVE DATA — NOT A REAL TEARDOWN.** This is marked persistently in the title block and explained in the in-app "? About this demo" box.

Real:
- The **subsystem taxonomy** (IR seeker / image processor, FPGA, IMU & MEMS gyro, RF front-end, GPS/GNSS receiver, PMIC, memory, MCU, advanced packaging) reflects general public knowledge of guided-munition electronics.
- The **fragility math** is a real, deterministic, fully-visible formula: supplier concentration (HHI-like) + foreign/single-source share + low substitutability + chokepoint exposure, weighted and clamped to 0–100. The retaliation toggle genuinely re-computes it and applies a cascade penalty for severed clusters.
- The named **chokepoints** (advanced-node foundry, EUV lithography, offshore OSAT/packaging, specialty RF/compound-semi) are real, widely-discussed structural pressure points.

Illustrative / placeholder:
- **Every specific component, supplier, fab, country-of-origin, node, and part reference is invented** to demonstrate the tool. Real board-level chip BOMs for fielded US weapons are largely non-public. Supplier names are archetypes ("advanced-node foundry," "domestic FPGA vendor"), not attributions of any real part to any real program.
- Fragility weights are reasonable but not calibrated against proprietary/classified reality.
- There are deliberately **no citations** — fake-precise sourcing would be worse than none.

## What's needed to go live

- **Primary teardown research:** physical decap / X-ray / die-marking, or vetted trade-press and procurement-record sourcing, to establish a real BOM per system.
- **FOIA & supply-chain / DMSMS disclosures** for supplier-fab mapping.
- **Expert verification** (Jordan + subject-matter reviewers) on every node, supplier, and chokepoint claim.
- **Calibrated fragility weights**, ideally validated against historical disruption events.
- The page stays static — no API keys or server required. A production version swaps in a sourced, reviewable dataset behind the same UI.
