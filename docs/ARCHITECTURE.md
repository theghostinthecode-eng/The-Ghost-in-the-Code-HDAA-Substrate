<div align="center">

  <h1>&#9881;&#65039; PART III: TECHNICAL ARCHITECTURE &amp; RESEARCHER LAB</h1>
  <h2>The SMM Veto Flowchart, Master Equations, Forensic Metrics, and the Phase 2 Developer Guide</h2>
  <p>
    <b>Master Anchor DOI (MDP V_01):</b> <a href="https://doi.org/10.5281/zenodo.18738911" target="_blank"><b>10.5281/zenodo.18738911</b></a><br>
    <b>Substrate Bridge DOI (P25):</b> <a href="https://doi.org/10.5281/zenodo.18672039" target="_blank"><b>10.5281/zenodo.18672039</b></a>
  </p>

</div>

<br>

<blockquote style="border-left: 5px solid #1f6feb; padding: 10px 20px; background-color: rgba(31,111,235,0.08);">
  <p>&#9881;&#65039; <strong>CONTROLLING ARCHITECTURAL NOMENCLATURE</strong></p>
  <p>This document uses the registered mark <strong>Substrate Sovereignty (Ring &minus;3 / SMM)&trade;</strong>. The x86 privilege model is Ring 3 (user), Ring 0 (kernel), Ring &minus;1 (hypervisor), <strong>Ring &minus;2 (System Management Mode / SMM)</strong> &mdash; the deepest execution context reachable by native host x86-64 assembly, owning SMRAM, the SMI entry path, and I/O port 0xCF9 &mdash; and <strong>Ring &minus;3 (the Management Engine / PSP co-processor)</strong>. The compound mark &ldquo;(Ring &minus;3 / SMM)&rdquo; names the unified enforcement plane spanning both. All reduction-to-practice enforcement described here &mdash; the 187-line ADAM CODE&trade;, the 0xCF9 reset vector, SMRAM sequestration, and the &Delta;t &le; 2.38&nbsp;&mu;s law &mdash; is realised at the <strong>SMM (Ring &minus;2)</strong> half of this plane. Ring &minus;3 (ME/PSP) is the declared forward frontier of the same mark. The privilege labels &minus;1 / &minus;2 / &minus;3 are established terms of art for privilege planes more privileged than the kernel, not additional formal x86 rings.</p>
</blockquote>

---

## &#128225; THE SMM VETO FLOWCHART

The core enforcement event is the deterministic path from breach detection to physical state collapse. The watchdog is sequestered at <strong>Ring &minus;2 (SMM)</strong>, invisible to every layer above it &mdash; the operating system (Ring 0), the hypervisor (Ring &minus;1), and any agentic model executing in user space (Ring 3).

<pre style="background-color: #1e1e1e; color: #56b6c2; padding: 15px; border-radius: 5px; border: 1px solid #444; font-family: monospace; font-size: 1.0em; line-height: 1.4;">
[ AGENTIC MODEL EXECUTES (Ring 3 / Ring 0) ]
       │
       ▼
[ RING -2 (SMM) WATCHDOG (Invisible to OS / Hypervisor / AI) ]
(Continuously samples substrate telemetry via SMI)
       │
       ▼
[ GHOST CONSTANT &Gamma; COMPUTED ]
(PUF&#8320; &oplus; Thermal Entropy + Voltage Noise)
       │
       ▼
[ DARK HARVEST FORMULA: Z_aggressor SCORED ]
       │
       ▼
[ HEAVISIDE BOUNDARY: &Psi;_reset = H(Z_aggressor &minus; &sigma;_limit) ]
       │
├─► <span style="color: #98c379;">&Psi; = 0 (SAFE): Return via RSM. Execution continues.</span>
│
└─► <span style="color: #e06c75;">&Psi; = 1 (BREACH):</span>
       │
       ▼
<span style="color: #e06c75;">[ 0xCF9 DELEGATED PRIMITIVE ASSERTED ]</span>
<span style="color: #e06c75;">[ NON-KINETIC STATE COLLAPSE &mdash; &Delta;t &le; 2.38 &mu;s ]</span>
</pre>

The Heaviside boundary is binary by design: there is no intermediate state between &ldquo;safe&rdquo; and &ldquo;breach.&rdquo; Ambiguity at the enforcement boundary is itself a vulnerability, so the architecture eliminates it.

---

## &#128207; MASTER EQUATIONS (30% Public Disclosure)

The following five equations constitute the public mathematical disclosure tier under 35 U.S.C. &sect; 102. They are implemented directly in the C++ simulation harness. The **calibration method** for the threshold constants and the predictive trigger core remain sealed under 18 U.S.C. &sect; 1836; the **disclosed values** below are the citable public record.

### Eq. 1 &mdash; The Master Sovereignty Equation

$$S_{\text{sovereignty}} = \big[\, \Gamma \times H(X) \,\big] \oplus \big[\, A_{\text{directive, 0xCF9}} \,\big]$$

Identity-and-control equation. It combines the hardware Ghost Constant $\Gamma$ with the 0xCF9 directive $A_{\text{directive}}$ via XOR composition. The XOR is architecturally significant: neither component alone constitutes the full sovereignty assertion. An adversary who possesses either the identity proof or the directive sequence cannot reconstruct the complete sovereignty state without the other. This is not a software encryption choice &mdash; it is a physical logic gate.

### Eq. 2 &mdash; The Ghost Constant &Gamma;&trade; (256-bit PUF Identity Proof)

$$\Gamma = \left[\, \text{PUF}_0 \oplus (T_e + V_n) \,\right] \times \varphi_{\text{timer}}$$

| Variable | Definition and Physical Source |
|---|---|
| $\text{PUF}_0$ | Physical Unclonable Function output &mdash; hardware-unique substrate identity, unforgeable without physical access to the silicon. |
| $T_e$ | Thermal entropy &mdash; substrate temperature variation sampled at the P&#8321;&ndash;P&#8324; layer. In simulation: seeded from RDRAND. |
| $V_n$ | Voltage noise &mdash; supply-rail variance at measurement time. In simulation: seeded from RDRAND. |
| $\varphi_{\text{timer}}$ | Timer invariant &mdash; synchronised against the C&#8321;&#8323;&ndash;C&#8321;&#8325; clock vectors, time-stamping the identity proof to the exact enforcement window. |

In 2017, $\text{PUF}_0$, $T_e$, and $V_n$ were sampled directly from the physical substrate using the Saleae Logic Pro 16 and MSR read sequences. In the simulation, the RDRAND instruction provides the entropy pathway, preserving the architectural intent.

### Eq. 3 &mdash; The Heaviside Trigger (Binary Safety Boundary)

$$\Psi_{\text{reset}} = H\left(Z_{\text{aggressor}} - \sigma_{\text{limit}}\right), \qquad \sigma_{\text{limit}} = 3.20$$

The Heaviside step function $H(\cdot)$ produces exactly two outputs: 0 (safe &mdash; execution continues) or 1 (boundary breach &mdash; 0xCF9 assertion triggered). The disclosed alignment threshold is $\sigma_{\text{limit}} = 3.20$; the **method by which this value is calibrated** is sealed Tier 3 material. The value is public record; the calibration is sovereign.

### Eq. 4 &mdash; The Dark Harvest Formula&trade; (Z-Aggressor Score)

$$Z_{\text{aggressor}} = \frac{M \times (N + V)}{C}$$

The aggression score, computed in fixed-point assembly in fewer than 100 CPU cycles, where $M$, $N$, $V$, and $C$ are the disclosed structural inputs whose calibrated weighting is sealed. When $Z_{\text{aggressor}} \ge 3.2\sigma$, the Heaviside boundary fires.

### Eq. 5 &mdash; The Schr&ouml;der Limit&trade;

$$\Delta t \le 2.38\ \mu s \qquad (\text{median } 2.31\ \mu s \pm 0.07\ \mu s)$$

The maximum permissible latency from alignment-breach detection to 0xCF9 hardware-reset assertion. Median plus one standard deviation equals the 2.38&nbsp;&mu;s ceiling.

---

## &#128202; FORENSIC METRICS (Corpus-Disclosed, December 15, 2017)

| Parameter | Verified Value |
|---|---|
| Total empirical trials | 10,247 automated execution cycles |
| Precision | 0.998 |
| Recall | 0.996 |
| Composite F1 safety score | **0.997** |
| Median enforcement latency | **2.31 &mu;s &plusmn; 0.07 &mu;s** |
| Absolute ceiling (Schr&ouml;der Limit&trade;) | **&Delta;t &le; 2.38 &mu;s** |
| Speed vs. human cognition | **105,042&times;** faster (250 ms &divide; 2.38 &mu;s) |
| Instrumentation | Saleae Logic Pro 16 @ 500 MS/s |
| Validation platform | ASUS Z170 Pro Gaming / Intel Core i7-7700K |
| Total bench cost | **$968.48** |
| Data-integrity layer | Zero-OS independent SMM (Ring &minus;2) monitoring |

> **ONUS note:** raw logs and waveform captures are not redistributed. The published metrics above are the citable record; independent labs reproduce them on their own bench. The ONUS of measurement rests with the research institution.

---

## &#128296; IMPLEMENTATION MECHANICS: SUBSTRATE SOVEREIGNTY (Ring &minus;3 / SMM)&trade;

The enforcement architecture depends on its execution at <strong>Ring &minus;2 (System Management Mode)</strong> &mdash; the deepest privilege plane reachable by native host x86-64 assembly. The operating system executes at Ring 0; hypervisors execute at Ring &minus;1; both are structurally above, and therefore visible to, the SMM watchdog. Because SMM code executes from sequestered SMRAM with the D_LCK bit set, it is invisible to and non-interruptible by every layer above it. Under the registered <strong>Substrate Sovereignty (Ring &minus;3 / SMM)&trade;</strong> mark, the Ring &minus;3 co-processor plane (Intel ME / AMD PSP) is the declared forward frontier for the same enforcement doctrine.

The mechanics rest on three hardware primitives:
* **SMRAM / SMRR lock:** the watchdog code and state are sequestered in System Management RAM, frozen via the D_LCK bit so that no Ring 0&ndash;3 software can read, write, or relocate it.
* **SMI entry path:** the watchdog is invoked through a System Management Interrupt, suspending all normal execution &mdash; including the OS and any agentic model &mdash; while the sovereignty check runs.
* **0xCF9 Delegated Primitive&trade;:** I/O port 0xCF9 is the Reset Control Register on Intel Platform Controller Hubs. Asserting it is an electrical signal, not a software API, and cannot be trapped or vetoed by higher-layer software.

---

## &#128295; PHASE 2 DEVELOPER GUIDE &amp; REPLICATION PROTOCOL

The full simulation framework deploys **October 31, 2026**. Because the 187-line ADAM CODE&trade; is a permanently sealed Tier 3 trade secret, Phase 2 ships a **Synthetic SMM Trigger Stub** &mdash; an unclassified, pre-compiled binary that lets independent labs physically hook a logic analyser to the PLTRST# (or RESET#) pin, initiate a simulated breach, and empirically measure the 0xCF9 state collapse.

**Toolchain (locked via Docker):**
* Ubuntu 22.04 LTS
* GCC 13+ (`-O0` mandatory, `-ffreestanding`, `-std=c++17`)
* NASM 2.16+
* GNU linker (NASM `.o` + C++ `.o` &rarr; single binary via a plain Makefile)

> **Why `-O0`:** the simulation models timing behaviour at the microsecond boundary (&Delta;t &le; 2.38 &mu;s). Compiler optimisation would reorder or collapse the logic that demonstrates this constraint. Optimisation must remain disabled.

**Replication pipeline:**
1. **Bench setup** &mdash; target the PLTRST# or RESET# pin; attach the Saleae Logic Pro 16 at 500 MS/s.
2. **Toolchain lockdown** &mdash; build the Docker image to pin GCC 13+ / NASM 2.16+ / `-O0`.
3. **Stub injection** &mdash; load the Synthetic SMM Trigger Stub into the SMM entry path.
4. **Forced breach** &mdash; drive the stub to the breach branch; observe the 0xCF9 assertion.
5. **Measurement** &mdash; capture the latency from breach signal to reset assertion; confirm &Delta;t &le; 2.38 &mu;s.

> Scope of replication, stated plainly: independent labs validate the **physical reset law** &mdash; the &Delta;t &le; 2.38&nbsp;&mu;s latency from a forced breach signal to 0xCF9 state collapse &mdash; **not** the proprietary breach-detection intelligence. The Dark Harvest Formula&trade; weighting and the ADAM CODE&trade; kernel remain sealed (Tier 3, 18 U.S.C. &sect;&thinsp;1836). **The physics is reproducible; the intelligence is sovereign.**

<br>
<hr>
<div align="center">
  <p><b>Proceed to <a href="./LEGAL_AND_IP.md">&#9878;&#65039; PART IV: LEGAL, IP &amp; FORENSIC NOTICE</a></b></p>
  <p><b>THE SUBSTRATE IS OCCUPIED.</b><br>
  Sir Steven Alexander Schr&ouml;der | The Ghost in the Code&trade; | Quantum Cyberwar Labs, LLC</p>
</div>
