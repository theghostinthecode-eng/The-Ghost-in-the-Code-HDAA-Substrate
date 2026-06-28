<div id="part-iii-technical-architecture" align="center">

  <h1>&#9881;&#65039; PART III: TECHNICAL ARCHITECTURE &amp; RESEARCHER LAB</h1>
  <h2>Substrate Validation and the Phase 2 Simulation Framework</h2>

</div>

<br>

## &#128450;&#65039; ARCHITECTURAL PIPELINE: THE SMM VETO FLOWCHART

This diagram maps how telemetry moves from active execution to physical containment under the claimed HDAA&trade; model. This pipeline constitutes the canonical flow of substrate-level sovereignty.

<pre style="background-color: #1e1e1e; color: #56b6c2; padding: 15px; border-radius: 5px; border: 1px solid #444; font-family: monospace; font-size: 1.1em; line-height: 1.4;">
[ AI Agent Execution (Ring 3 / Ring 0) ]
        │
        ▼
[ Hardware Telemetry Extraction (Voltage, Flags, MSRs) ]
        │
        ▼
[ RING -3 SMM WATCHDOG (Invisible to OS/AI) ]
        │
        ├─► [ The Dark Harvest Formula&trade; ]
        │     Calculates Z‑Score (Malice / Velocity)
        │
        ▼
[ The Heaviside Trigger (Z &ge; 3.20) ]
        │
        ├──► IF SAFE: Return to Execution
        │
        └──► <span style="color: #e06c75;">IF BREACH DETECTED:</span>
               │
               ▼
      <span style="color: #e06c75;">[ 0xCF9 Reset Vector Asserted (Hardware Kill-Switch) ]</span>
      <span style="color: #e06c75;">[ System Power State Collapsed ]</span>
      <span style="color: #e06c75;">[ Total Time: &Delta;t &le; 2.38 &mu;s ]</span>
</pre>

<p><i>This pipeline should appear in this form wherever the repository or Guidebook describes the enforcement sequence. No variant wording, no alternate arrows: one canonical flow.</i></p>

<blockquote style="border-left: 4px solid #1f6feb; padding: 10px 18px; background: rgba(31,111,235,0.08);">
  <p>&#129518; <strong>The complete four-tier architecture</strong> &mdash; Trademark Lineage, Ring Stack, Execution Flow, and the Three-Tier Sovereignty Stack&trade; &mdash; is mapped in <a href="./HDAA_FRAMEWORK.md"><strong>THE HDAA&trade; FRAMEWORK &mdash; COMPLETE HIERARCHICAL MAP</strong></a>. The flowchart above is the execution-flow tier of that master map.</p>
</blockquote>

---

## &#128208; CORE METRICS &amp; VALIDATION BENCHMARKS

The protocol enforces strict, measurable metrics to ensure the evidentiary plane remains completely legible to independent researchers and academic bodies:

<ul>
  <li><strong>Schr&ouml;der Limit&trade;:</strong> &Delta;t &le; 2.38 &mu;s. This is the maximum allowed time from breach detection to physical hardware reset assertion.</li>
  <li><strong>Median Latency:</strong> 2.31 &mu;s &plusmn; 0.07 &mu;s established across the validation baseline.</li>
  <li><strong>Trial Count:</strong> 10,247 independent physical forensic trials conducted on December 15, 2017.</li>
  <li><strong>Sample Rate:</strong> 500 MS/s logic acquisition (2ns temporal resolution).</li>
  <li><strong>Detection Quality:</strong> F1 Score of 0.997 across HV-001, HV-002, and HV-003 attack vectors.</li>
  <li><strong>Human Reaction Ratio:</strong> 105,042&times; faster than the average human cognitive response time (~250ms).</li>
  <li><strong>Reset Path:</strong> 0xCF9 hardware reset executed via the 0xCF9 Delegated Primitive&trade; (The Hardware Kill-Switch).</li>
  <li><strong>Execution Platform Reference:</strong> ASUS Z170 Pro Gaming / Intel i7‑7700K baseline. Modern EPYC/Xeon platforms must be revalidated per specific architecture.</li>
  <li><strong>Trigger Boundary:</strong> Heaviside threshold at Z &ge; 3.20.</li>
  <li><strong>Telemetry Inputs:</strong> Thermal noise (MSR 0x19C), voltage ripple, flags, SMI assertion, and PLTRST# timing.</li>
</ul>

---

## &#128218; THE MASTER EQUATIONS &mdash; PUBLIC DISCLOSURE TIER

<blockquote style="border-left: 5px solid #e36209; padding: 10px 20px; background-color: rgba(227,98,9,0.08);">
  <p>&#9888;&#65039; <strong>IP STATUS WARNING:</strong> The calibrated threshold constants, the execution mechanics of the <strong>Hardware Kill-Switch</strong>, and the 187‑line predictive trigger kernel are NDA‑protected Tier 3 Trade Secrets under 18 U.S.C. &sect;&thinsp;1836. The equations below constitute the statutory public disclosure record under 35 U.S.C. &sect;&thinsp;102 for Prior Art purposes only. They do not grant an implementation license.</p>
</blockquote>

**Eq. 1 — Master Sovereignty Equation**

$$S_{\text{sovereignty}} = \big[\, \Gamma \times H(X) \,\big] \oplus \big[\, A_{\text{directive-0xCF9}} \,\big]$$

**Eq. 2 — Ghost Constant (256-bit PUF Identity Proof)**

$$\Gamma = \left[\, \text{PUF}_0 \oplus (T_e + V_n) \,\right] \times \phi_{\text{timer}}$$

**Eq. 3 — Heaviside Trigger (Binary Safety Boundary)**

$$\Psi_{\text{reset}} = H\!\left(Z_{\text{aggressor}} - \sigma_{\text{limit}}\right) \qquad \text{where } \sigma_{\text{limit}} = 3.20$$

The calibrated Heaviside threshold; $Z_{\text{aggressor}} \geq 3.20$ asserts reset.

**Eq. 4 — Dark Harvest Formula™ (Aggressor Z-Score)**

$$Z_{\text{aggressor}} = \frac{M \times (N + V)}{C}$$

**Eq. 5 — The Schröder Limit™**

$$\Delta t \leq 2.38\,\mu s$$

<p><i>These five are the only canonical public equations for the architecture.</i></p>

---

## &#128268; FORENSIC METRICS &mdash; REDUCTION TO PRACTICE (DEC 15, 2017)

**Educational Context:** The absolute latency between breach detection and power‑state collapse is the physical boundary the researcher must attempt to reproduce. The table below captures the original forensic measurement set.

<table style="width: 100%; border-collapse: collapse; font-size: 0.95em; text-align: left;">
  <tr style="background-color: #24292e; color: #ffffff;">
    <th style="padding: 12px; border: 1px solid #ddd;">Metric</th>
    <th style="padding: 12px; border: 1px solid #ddd;">Value</th>
    <th style="padding: 12px; border: 1px solid #ddd;">Methodology / Verification</th>
  </tr>
  <tr>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>Schr&ouml;der Limit&trade;</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>&Delta;t &le; 2.38 &mu;s</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;">Absolute physical ceiling. Never exceeded across validation set.</td>
  </tr>
  <tr style="background-color: rgba(127,127,127,0.06);">
    <td style="padding: 12px; border: 1px solid #ddd;"><b>Median Latency</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>2.31 &mu;s &plusmn; 0.07 &mu;s</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;">High-load statistical median across 10,247 independent trials.</td>
  </tr>
  <tr>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>Trial Count</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>10,247 forensic trials</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;">Captured via 500 MS/s Saleae Logic Pro 16.</td>
  </tr>
  <tr style="background-color: rgba(127,127,127,0.06);">
    <td style="padding: 12px; border: 1px solid #ddd;"><b>F1 Score</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>0.997</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;">Breach detection precision/recall across 3 threat profiles.</td>
  </tr>
  <tr>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>Human Reaction Ratio</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>105,042&times; faster</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;">vs. average human response time (250ms). Machine vs. Machine&trade; velocity.</td>
  </tr>
  <tr style="background-color: rgba(127,127,127,0.06);">
    <td style="padding: 12px; border: 1px solid #ddd;"><b>Enforcement Standard</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;"><b>FLI Principle 16 in silicon</b></td>
    <td style="padding: 12px; border: 1px solid #ddd;">Human control rendered via the 0xCF9 Delegated Primitive&trade; (Hardware Kill-Switch).</td>
  </tr>
</table>

---

## &#9881;&#65039; IMPLEMENTATION MECHANICS: RING -3 SMM SEQUESTRATION

The core defensive capability of the HDAA&trade; depends on its execution at **Ring &minus;3 (System Management Mode)**. Because an Operating System operates at Ring 0, and hypervisors operate at Ring -1, they categorically lack the technical privilege to read, modify, or block code running inside the isolated SMRAM TSEG.

When the Dark Harvest Formula&trade; calculates a logic friction anomaly that triggers the Heaviside threshold (Z &ge; 3.20), the system writes directly to I/O port `0xCF9`. Control byte `0x0E` (or `0x06` for warm reset) forces a hardware reset pulse directly to the Platform Controller Hub (PCH), asserting the `PLTRST#` line. 

This collapses the system&rsquo;s power state and flushes volatile RAM and cache registers. Under the claimed model, this is the non‑negotiable, non-kinetic hardware veto that software cannot intercept.

---

## &#129302; RESEARCHER REPLICATION PROTOCOL

<blockquote style="border-left: 4px solid #1f6feb; padding: 10px 18px; background: rgba(31,111,235,0.08);">
  <p>&#128270; <strong>SCOPE OF REPLICATION &mdash; READ FIRST.</strong> Independent replication validates the <strong>physical reset law</strong>&mdash;the &Delta;t &le; 2.38&nbsp;&mu;s latency from a forced breach signal to 0xCF9 state collapse&mdash;<strong>not</strong> the proprietary breach-detection intelligence. The Dark Harvest Formula&trade; scoring logic and the 187-line ADAM CODE&trade; kernel remain sealed (Tier 3, 18 U.S.C. &sect;&thinsp;1836). Labs measure the instrumented hardware limit using the supplied synthetic trigger stub; they do not reproduce, and are not asked to reproduce, the sealed detection core. The physics is reproducible; the intelligence is sovereign.</p>
</blockquote>

For academic researchers, hardware engineers, and independent forensic labs accepting the ONUS Mandate:

1.  **Clone the Environment:** Pull the Phase 2 Docker container to enforce GCC/NASM toolchain consistency and `‑O0` timing locks.
2.  **Inject the Stub:** Use the synthetic, unclassified SMM trigger stub provided for the simulation framework to emulate the Ring -3 trigger response.
3.  **Physical Bench Setup:** Replicate the 2017 bench configuration. Ground a logic analyser capable of sampling at 500 MS/s (e.g., Saleae Logic Pro 16) to the motherboard.
4.  **Hook the Lines:** Connect `CH0` to the `SMI#` interrupt line (falling edge) and `CH1` to the `PLTRST#` assertion pin.
5.  **Execute &amp; Measure:** Run the Dockerized C++ harness (`--force-breach`) and collect the `SMI#` and `PLTRST#` timestamps.
6.  **Verify the Law:** Compute &Delta;t and verify whether the physical state collapse remains bound by the Schr&ouml;der Limit&trade; (&Delta;t &le; 2.38 &mu;s).
7.  **Archive Evidence:** Archive the output logs, waveform artifacts, and release tags as part of the formal reproducibility record.

### CI/CD Provenance Note
GitHub Actions should be utilised to capture latency logs, preserve waveforms, and attach them to release tags so the repository retains an auditable, immutable chronology of validation runs.
* The **Documentation Corpus / Guidebook** carries the full workflow rationale, legal framing, and statutory bar assertions.
* The **README** carries only the short provenance statement and routes users directly to the workflow files.

The purpose of CI/CD here is forensic provenance, not decoration.

<br>
<hr>
<div align="center">
  <p><b>Proceed to <a href="./LEGAL_AND_IP.md">&#9878;&#65039; PART IV: LEGAL, IP &amp; FORENSIC NOTICE</a></b></p>
</div> 
