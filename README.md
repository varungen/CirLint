# CirLint ⚡
### AI-Powered Semantic & Datasheet-Aware Schematic and PCB Layout Review Platform

> **CirLint** transforms hardware engineering reviews into an automated, verifiable pre-fab pipeline. It combines **Schematic Design Reviews (SDR)** and **PCB Physical Layout Reviews (LDR)** with verbatim manufacturer datasheet citations, IPC-2152 current analysis, 2D interactive canvas layout cross-probing, automated safe ECO change orders, and revision regression tracking across board spins.

---

## 🏛️ Platform Architecture

```
                    ┌─────────────────────────────────────────────────────────┐
                    │               Hardware Engineer / Laptop                │
                    │   (Altium .SchDoc / .PcbDoc  &  KiCad .kicad_sch/.pcb)   │
                    └────────────────────────────┬────────────────────────────┘
                                                 │
                                 ┌───────────────▼───────────────┐
                                 │    CirLint Desktop Engine     │
                                 │  (100% Offline & Local-First) │
                                 └───────┬───────────────┬───────┘
                                         │               │
            ┌────────────────────────────┴───┐       ┌───┴─────────────────────────────┐
            │   Schematic Review (SDR)       │       │    PCB Layout Review (LDR)      │
            │ • Datasheet Abs Max Ratings    │       │ • IPC-2152 Current vs. Width    │
            │ • 5V Non-Tolerant Overstress   │       │ • Decoupling Proximity (<3.5mm) │
            │ • Power / Decoupling Ratios    │       │ • Thermal Via Array Matrices    │
            │ • CAN Termination (120Ω)       │       │ • 3W Fast Signal Crosstalk      │
            │ • BOM Supply Chain & EOL/NRND  │       │ • Microstrip Z0 Impedance (50Ω) │
            └────────────────┬───────────────┘       └───────────────┬─────────────────┘
                             │                                       │
                             └───────────────────┬───────────────────┘
                                                 │
                                 ┌───────────────▼───────────────┐
                                 │   Reporting & Tracking Core   │
                                 └───────┬───────────────┬───────┘
                                         │               │
        ┌────────────────────────────────┼───────────────┼────────────────────────────────┐
        │                                │               │                                │
┌───────▼──────────────┐ ┌───────────────▼──────┐ ┌──────▼─────────────┐ ┌────────────────▼─────────┐
│ Interactive 2D Canvas│ │ Official PDF Reports │ │ Safe Markdown ECOs │ │ Revision Timeline Tracker │
│ Web Layout Viewer    │ │ (Jira/Review Ready)  │ │ (Human-in-the-Loop)│ │ (Rev 1.0 ➔ Rev 10.0 Delta)│
└──────────────────────┘ └──────────────────────┘ └────────────────────┘ └───────────────────────────┘
```

---

## 🚀 Standalone Windows Desktop App (Zero-Install)

No Python, compiler, or external dependency setup is required. Your CAD files never leave your machine.

1. **Download the Release**: Download **`CirLint-v1.0.0-Beta-Windows-x64.zip`** from [**Releases**](https://github.com/varungen/CirLint/releases).
2. **Launch**: Extract the archive and double-click **`Launch-CirLint.bat`** or **`CirLint\CirLint.exe`**.
3. **Try the Demo**: Click **`⚡ Try Demo Board (Telematics Gateway)`** on the landing screen to run an instant full-board audit in 5 seconds.
4. **Audit Your Own CAD Projects**: Open any folder containing Altium (`.SchDoc`/`.PcbDoc`) or KiCad (`.kicad_sch`/`.kicad_pcb`) files.

> 🎁 **Public Beta Launch Promo**: Click the account badge in the top-right corner and click **"Public Beta Launch: Click to Auto-Fill Free Pro License"** (or enter Key: **`CIRLINT-PRO-BETA-LAUNCH-2026`**) for unlimited reviews, multi-spin revision diffs, and executive PDF report generation!

---

## 🖥️ CirLint Desktop ("SourceTree for Hardware")

### Key Capabilities:
1. **📁 Auto-Detect Workspace & Multi-Revision Discovery**: Point CirLint to your project root; it automatically discovers your Altium (`.SchDoc`/`.PcbDoc`) or KiCad (`.kicad_sch`/`.kicad_pcb`) files—including multi-spin revision folders (`Rev 7` ➔ `Rev 10`).
2. **🔲 2-Button Stage Gate**:
   - `⚡ Run Schematic Review`
   - `📐 Run PCB Layout Review`
   - `🚀 Run Full Board Review`
3. **📊 Live Health Score & Delta**: Displays board readiness score (0–100%) and tracks progression across spins (`+40% vs Rev 9` • `Issues Resolved`).
4. **👁️ Auto-Audit on Save (`Ctrl+S`)**: Optional background CAD file watcher triggers instant re-audits whenever you save in Altium or KiCad.
5. **📂 Standardized Output**: Executive PDF sign-off reports and interactive 2D layout viewers are organized cleanly inside `<Your_Project>/CirLint_Audits/Rev_<N>/`.
6. **🔒 100% Offline & Private**: Runs locally on your workstation with optional offline local LLM support (Qwen 2.5) or bring-your-own enterprise AWS Bedrock / Azure OpenAI endpoint.

---

## 💰 Plans & Licensing

| Plan | Pricing | Features & Quotas |
| :--- | :--- | :--- |
| **Community Free** | **$0** (Free Forever) | • Full Schematic & PCB Layout Verification<br>• Verbatim manufacturer datasheet citations with page numbers<br>• 1-Click Demo Board & instant local health scores |
| **Pro Engineer (Beta)** | **$0 During Beta**<br>(Normally $49/mo) | • **Unlimited Scans & Multi-Spin Reviews**<br>• Multi-Revision Auto-Discovery & Timeline Diffs (`Rev 7` ➔ `Rev 10`)<br>• Offline & Enterprise AI Copilot (Qwen 2.5, Bedrock, Azure)<br>• Official Executive PDF Audit Certificate Generation<br>• BOM Supply Chain & Obsolete/NRND Component Alerts |
| **Enterprise / Team** | **$199 / seat / mo** | • Automated GitHub Actions / GitLab CI/CD Gatekeeper<br>• Custom Corporate Verification Rulebooks & Jira/ERP Integration<br>• Team Central Dashboard & Multi-seat Sync<br>• Dedicated Support & SLA |

---

## 💬 Feedback, Rule Requests & Bug Reports

Have a rule suggestion (e.g., specific IC families, power topologies, or DFM checks) or found a bug?
- Open an issue on [**GitHub Issues**](https://github.com/varungen/CirLint/issues).
- Please see [`QUICKSTART.txt`](./QUICKSTART.txt) for a 1-minute onboarding checklist.
