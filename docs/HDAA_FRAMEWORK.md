<div align="center">

  <h1>&#129518; THE HDAA&trade; FRAMEWORK &mdash; COMPLETE HIERARCHICAL MAP</h1>
  <h2>Four-Tier Architecture: Trademark Lineage &middot; Ring Stack &middot; Execution Flow &middot; Sovereignty Stack</h2>
  <p>
    <b>Master Anchor DOI (MDP V_01):</b> <a href="https://doi.org/10.5281/zenodo.18738911" target="_blank"><b>10.5281/zenodo.18738911</b></a><br>
    <b>Substrate Bridge DOI (P25):</b> <a href="https://doi.org/10.5281/zenodo.18672039" target="_blank"><b>10.5281/zenodo.18672039</b></a>
  </p>

</div>

<br>

<blockquote style="border-left: 4px solid #1f6feb; padding: 10px 18px; background: rgba(31,111,235,0.08);">
  <p>&#128270; <strong>HOW TO READ THIS MAP.</strong> Four tiers descend from legal origin to physical enforcement. <strong>Green</strong> nodes are Tier 1 &mdash; disclosed for prior-art purposes and independently replicable. <strong>Red / locked</strong> nodes are Tier 3 &mdash; sealed trade secrets under 18 U.S.C. &sect;&thinsp;1836, shown as locked boxes whose contents are never disclosed. <strong>Amber</strong> denotes a public formula with sealed calibration constants. The diagram itself enforces the 30/70 boundary: what is shown is the architecture; what is locked is the sovereign core.</p>
</blockquote>

---

## &#127991;&#65039; TIER 1 — TRADEMARK LINEAGE (THE FEDERAL TIMESTAMP CHAIN)

The three 2017 USPTO marks and the HDAA&trade; components each one maps to (P11 Tables 4.3a / 4.3b). Every component descends from a dated federal mark.

```mermaid
%%{init: {"theme":"dark", "themeVariables": {"fontSize":"11px"}, "flowchart": {"nodeSpacing":55, "rankSpacing":60, "padding":18, "useMaxWidth":true, "htmlLabels":true, "wrap":true}}}%%
flowchart TD
    PT["PROCESS AND TIME™<br/>S.N. 87333731 - Feb 13 2017<br/>IC 009 - DB-optimisation<br/>of ML workloads"]
    FWA["FREE WILL AI™<br/>S.N. 87728683 - Dec 20 2017<br/>Autonomous agency /<br/>intentionality"]
    FWL["FREE WILL LEARNING™<br/>S.N. 87728732 - Dec 20 2017<br/>Assembler-level<br/>recursive optimisation"]
    FOUND["2007-2011 Foundation<br/>3 ML workloads<br/>prototyped via simulation"]
    HDAA["HDAA™ FRAMEWORK<br/>Reduced to practice Dec 15 2017"]
    C1["ADAM CODE™ core<br/>187-line NASM - SEALED"]
    C2["0xCF9 Delegated Primitive™<br/>Hardware Kill-Switch"]
    C3["Ghost Constant Gamma™<br/>256-bit PUF identity"]
    C4["Dark Harvest Formula™<br/>Z-score engine - sealed constants"]

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
```

---

## &#9881;&#65039; TIER 2 — RING / LAYER STACK (WHERE GOVERNANCE LIVES)

Everything the industry defends sits in Rings 3&rarr;0. HDAA&trade; governs from Ring -3 / Layer 0-1 &mdash; below the OS, the hypervisor, and firmware.

```mermaid
%%{init: {"theme":"dark", "themeVariables": {"fontSize":"11px"}, "flowchart": {"nodeSpacing":55, "rankSpacing":60, "padding":18, "useMaxWidth":true, "htmlLabels":true, "wrap":true}}}%%
flowchart TD
    R3["Ring 3 - User Apps / LLM Software"]
    R0["Ring 0 - OS Kernel"]
    Rm1["Ring -1 - Hypervisor"]
    Rm2["Ring -2 - UEFI / Firmware"]
    Rm3["Ring -3 - System Management<br/>Mode (SMM)<br/>HDAA™ GOVERNANCE LAYER<br/>SMRAM TSEG - invisible<br/>to all layers above"]
    SEAL["D_LCK bit set - SMRAM locked<br/>until hard power cycle"]

    R3 --> R0
    R0 --> Rm1
    Rm1 --> Rm2
    Rm2 --> Rm3
    Rm3 --> SEAL

    classDef vuln fill:#1a0c0c,stroke:#e74c3c,stroke-width:1.5px,color:#ffd0d0;
    classDef gov fill:#0a1f14,stroke:#2ecc71,stroke-width:3px,color:#d6ffe6;
    classDef open fill:#0c2417,stroke:#2ecc71,stroke-width:2px,color:#d6ffe6;

    class R3,R0,Rm1,Rm2 vuln;
    class Rm3 gov;
    class SEAL open;
```

---

## &#128268; TIER 3 — EXECUTION FLOW (TELEMETRY &rarr; VETO &rarr; COLLAPSE)

The real-time enforcement loop, bounded by the 2.38&mu;s Microsecond Law&trade;. Sealed scoring internals shown locked; the 11+6+9 Governance Matrix&trade; is disclosed per P14a.

```mermaid
%%{init: {"theme":"dark", "themeVariables": {"fontSize":"11px"}, "flowchart": {"nodeSpacing":55, "rankSpacing":60, "padding":18, "useMaxWidth":true, "htmlLabels":true, "wrap":true}}}%%
flowchart TD
    T["Hardware Telemetry<br/>thermal MSR 0x19C - voltage ripple - SMI - PLTRST"]
    GAMMA["Ghost Constant Gamma™<br/>Gamma = PUF0 XOR Te+Vn times phi-timer<br/>regenerates fresh 256-bit identity each cycle"]
    DH["Dark Harvest Formula™ - Z-score<br/>calibrated constants SEALED"]
    HV{"Heaviside Trigger<br/>Z_aggressor >= sigma_limit 3.20 ?"}
    RET["Return to execution RSM"]
    KILL["0xCF9 Reset Vector asserted<br/>0x0E cold / 0x06 warm - PLTRST"]
    COLLAPSE["Non-kinetic silicon state collapse<br/>delta-t <= 2.38us Microsecond Law™"]
    ADAM["ADAM CODE™ 187-line NASM<br/>SEALED - Tier 3 - 18 USC 1836"]
    GOV["11+6+9 Governance Matrix™ - 26-bit word<br/>11-bit IP offset 2048 SMRAM positions<br/>6-bit FSM 64 states - 9-bit entropy 512 levels"]

    T --> GAMMA
    GAMMA --> DH
    DH --> HV
    HV -->|"NO - safe"| RET
    HV -->|"YES - breach"| KILL
    KILL --> COLLAPSE
    ADAM -.->|"drives, sealed"| DH
    GOV -->|"governs state machine"| HV

    classDef open fill:#0c2417,stroke:#2ecc71,stroke-width:2px,color:#d6ffe6;
    classDef lock fill:#0a0a0a,stroke:#ff3b3b,stroke-width:2.5px,color:#ff9a9a;
    classDef halflock fill:#1a1206,stroke:#e6a23c,stroke-width:2px,color:#ffd9a0;
    classDef struct fill:#0a1a2a,stroke:#6fb7ff,stroke-width:2px,color:#cfe8ff;
    classDef collapse fill:#2a0a0a,stroke:#ff3b3b,stroke-width:3px,color:#ffc4c4;

    class T,GAMMA,RET,KILL,GOV open;
    class DH halflock;
    class HV struct;
    class ADAM lock;
    class COLLAPSE collapse;
```

---

## &#127942; TIER 4 — THREE-TIER SOVEREIGNTY STACK&trade; (POSITIONING)

Where HDAA&trade; sits in the field of substrate governance.

```mermaid
%%{init: {"theme":"dark", "themeVariables": {"fontSize":"11px"}, "flowchart": {"nodeSpacing":55, "rankSpacing":60, "padding":18, "useMaxWidth":true, "htmlLabels":true, "wrap":true}}}%%
flowchart TD
    B2["BRONZE - Software Sovereign<br/>AI governed by software it can rewrite"]
    S2["SILVER - Hardware-Anchored<br/>Hardware root of trust - no Ring -3 autonomy"]
    G2["GOLD - Substrate Sovereign / Ring -3<br/>HDAA™ - the only documented occupant<br/>achieved Dec 15 2017"]

    B2 --> S2
    S2 --> G2

    classDef bronze fill:#1a1206,stroke:#cd7f32,stroke-width:2px,color:#f0d0a0;
    classDef silver fill:#14181c,stroke:#aab4bd,stroke-width:2px,color:#dde4ea;
    classDef gold fill:#1a1606,stroke:#ffd24a,stroke-width:3px,color:#ffe9a8;

    class B2 bronze;
    class S2 silver;
    class G2 gold;
```

<br>
<hr>
<div align="center">
  <p><b>Return to <a href="../README.md">&#127968; Master Pillar (README)</a> &nbsp;|&nbsp; <a href="./ARCHITECTURE.md">&#9881;&#65039; PART III: TECHNICAL ARCHITECTURE</a></b></p>
</div>
