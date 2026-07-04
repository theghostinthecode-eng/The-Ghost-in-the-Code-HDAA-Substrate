
<sub><b>Part V — The HDAA Framework Hierarchical Map · Version P05.v07 · 1 July 2026</b></sub>

<div align="center">

  <h1>&#129518; THE HDAA&trade; FRAMEWORK &mdash; COMPLETE HIERARCHICAL MAP</h1>
  <h2>Four-Tier Architecture: Trademark Lineage &middot; Ring Stack &middot; Execution Flow &middot; Sovereignty Stack</h2>
  <p>
    <b>Master Anchor DOI (MDP V_01):</b> <a href="https://doi.org/10.5281/zenodo.18738911" target="_blank"><b>10.5281/zenodo.18738911</b></a><br>
    <b>Substrate Bridge DOI (P25):</b> <a href="https://doi.org/10.5281/zenodo.18672039" target="_blank"><b>10.5281/zenodo.18672039</b></a>
  </p>

</div>

<br>

<div style="border-left: 6px solid #cb2431; padding: 14px 22px; color: inherit;">
  <p>&#127919; <strong>THE REPLICATION MISSION &mdash; NOTHING MORE, NOTHING LESS.</strong></p>
  <p>Researchers are asked to prove exactly <strong>one</strong> thing: the <strong>physical reset law</strong> &mdash; that a write to I/O port <code>0xCF9</code> from SMM (Ring &minus;2) collapses the platform power state in <strong>&Delta;t &le; 2.38&mu;s</strong>. That is the entire objective. Reproducing this single bounded law &mdash; one logged waveform showing sub-2.38&mu;s collapse on your own bench &mdash; confirms that the <strong>December 15, 2017</strong> prototype and its simulation were real. No sealed intelligence is required to validate it. The mechanism is legible and reproducible; the calibrated core that decides <em>when</em> the veto fires remains sovereign. <strong>Prove the reset law. That is the mission.</strong></p>
</div>


<div style="border-left: 4px solid #1f6feb; padding: 10px 18px; color: inherit;">
  <p>&#128270; <strong>HOW TO READ THIS MAP.</strong> Four tiers descend from legal origin to physical enforcement. <strong>Green</strong> nodes are Tier 1 &mdash; disclosed for prior-art purposes and independently replicable. <strong>Red / locked</strong> nodes are Tier 3 &mdash; sealed trade secrets under 18 U.S.C. &sect;&thinsp;1836, shown as locked boxes whose contents are never disclosed. <strong>Amber</strong> denotes a public formula with sealed calibration constants. The diagram itself enforces the 30/70 boundary: what is shown is the architecture; what is locked is the sovereign core.</p>
</div>

<div style="border-left: 5px solid #1f6feb; padding: 10px 20px; color: inherit;">
  <p>&#9881;&#65039; <strong>CONTROLLING NOMENCLATURE.</strong> The x86 privilege planes are Ring 3 (user), Ring 0 (kernel), Ring &minus;1 (hypervisor), <strong>Ring &minus;2 (System Management Mode / SMM)</strong> &mdash; owning SMRAM, the SMI entry path, and I/O port 0xCF9 &mdash; and <strong>Ring &minus;3 (the Management Engine / PSP co-processor)</strong>. All reduction-to-practice enforcement in this map is realised at <strong>Ring &minus;2 (SMM)</strong>; Ring &minus;3 (ME/PSP) is the declared forward frontier. The registered mark <strong>Substrate Sovereignty (Ring &minus;3 / SMM)&trade;</strong> names the unified plane spanning both.</p>
</div>

---

## &#127991;&#65039; TIER 1 — TRADEMARK LINEAGE (THE FEDERAL TIMESTAMP CHAIN)

The three 2017 USPTO marks and the HDAA&trade; components each one maps to (P11 Tables 4.3a / 4.3b). Every component descends from a dated federal mark.

```mermaid
%%{init: {"theme":"dark","themeVariables": {"fontSize":"11px"},"flowchart": {"nodeSpacing":55,"rankSpacing":60,"padding":18,"useMaxWidth":true,"htmlLabels":true,"wrap":true}}}%%
flowchart TD
    PT["PROCESS AND TIME&trade;<br>S.N. 87333731 - Feb 13 2017<br>IC 009<br>DB-optimisation<br>of ML workloads"]
    FWA["FREE WILL AI&trade;<br>S.N. 87728683 - Dec 20 2017<br>Autonomous agency /<br>intentionality"]
    FWL["FREE WILL LEARNING&trade;<br>S.N. 87728732 - Dec 20 2017<br>Assembler-level<br>recursive optimisation"]
    FOUND["2007-2011 Foundation<br>3 ML workloads<br>prototyped<br>via simulation"]
    HDAA["HDAA&trade; FRAMEWORK<br>Reduced to practice Dec 15 2017"]
    C1["ADAM CODE&trade; core<br>187-line NASM - SEALED"]
    C2["0xCF9 Delegated Primitive&trade;<br>Hardware Kill-Switch"]
    C3["Ghost Constant Gamma&trade;<br>256-bit PUF identity"]
    C4["Dark Harvest Formula&trade;<br>Z-score engine - sealed constants"]

    PT --> FOUND
    FOUND --> HDAA
    FWA --> HDAA
    FWL --> HDAA
    HDAA --> C1
    HDAA --> C2
    HDAA --> C3
    HDAA --> C4

    classDef open fill:#0c2417,stroke:#2ecc71,stroke-width:2px,color:#d6ffe6;
    classDef lock fill:#0a0a0a,stroke:#ff3b3b,stroke-width:2px,color:#ff9a9a;
    classDef halflock fill:#1a1206,stroke:#e6a23c,stroke-width:2px,color:#ffd9a0;
    classDef struct fill:#0a1a2a,stroke:#6fb7ff,stroke-width:2px,color:#cfe8ff;

    class PT,FWA,FWL,FOUND,C2,C3 open;
    class C1 lock;
    class C4 halflock;
    class HDAA struct;
