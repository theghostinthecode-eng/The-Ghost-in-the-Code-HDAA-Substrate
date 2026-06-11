<div id="part-iii-technical-architecture">
  <h2>PART III: TECHNICAL ARCHITECTURE &amp; RESEARCHER LAB</h2>

  <h3>Architectural Pipeline: The SMM Veto Flowchart</h3>
  <p>This diagram maps how telemetry moves from active execution to physical containment under the claimed HDAA&trade; model:</p>

  <pre><code>
[ AI Agent Execution (Ring 3 / Ring 0) ]
        │
        ▼
[ Hardware Telemetry Extraction (Voltage, Flags, MSRs) ]
        │
        ▼
[ RING -3 SMM WATCHDOG (Invisible to OS/AI) ]
        │
        ├─► [ The Dark Harvest Formula ]
        │     Calculates Z‑Score (Malice / Velocity)
        │
        ▼
[ The Heaviside Trigger (Z ≥ 3.20) ]
        │
        ├──► IF SAFE: Return to Execution
        │
        └──► IF BREACH DETECTED:
               │
               ▼
      [ 0xCF9 Reset Vector Asserted ]
      [ System Power State Collapsed ]
      [ Total Time: Δt ≤ 2.38 μs ]
  </code></pre>

  <p>This pipeline should appear in this form wherever the repository or Guidebook describes the enforcement sequence. No variant wording, no alternate arrows: one canonical flow.</p>

  <h3>Core Metrics Used</h3>
  <p>The protocol section keeps metrics explicit and legible to researchers:</p>
  <ul>
    <li><strong>Schröder Limit:</strong> $$ \Delta t \le 2.38 \mu s $$. This is the maximum allowed time from breach detection to reset assertion.</li>
    <li><strong>Median Latency:</strong> 2.31 microseconds &plusmn; 0.07 microseconds across 10,247 trials.</li>
    <li><strong>Trial Count:</strong> 10,247 independent forensic trials.</li>
    <li><strong>Sample Rate:</strong> 500 MS/s logic acquisition.</li>
    <li><strong>Detection Quality:</strong> F1 score of 0.997.</li>
    <li><strong>Human Reaction Ratio:</strong> 105,042&times; faster than average human response time.</li>
    <li><strong>Reset Path:</strong> 0xCF9 hardware reset via delegated primitive.</li>
    <li><strong>Execution Platform Reference:</strong> Intel i7‑7700K baseline; modern EPYC/Xeon platforms must be revalidated per platform.</li>
    <li><strong>Trigger Boundary:</strong> Heaviside threshold at Z &ge; 3.20.</li>
    <li><strong>Telemetry Inputs:</strong> Voltage, flags, MSRs, SMI assertion, and PLTRST# timing.</li>
  </ul>

  <h3>The Master Equations &mdash; Public Disclosure Tier</h3>
  <p>&#9888; The calibrated threshold constants and 187‑line predictive trigger kernel are NDA‑protected Tier 3 Trade Secrets under 18 U.S.C. &sect;&thinsp;1836. The equations below constitute the statutory public disclosure record under 35 U.S.C. &sect;&thinsp;102.</p>

  <p><strong>Eq. 1 &mdash; Master Sovereignty Equation</strong><br>
  $$S_{sovereignty} = [\Gamma \times H(X)] \oplus [A_{directive\_0xCF9}]$$</p>

  <p><strong>Eq. 2 &mdash; Ghost Constant (256‑bit PUF Identity Proof)</strong><br>
  $$\Gamma = [PUF_0 \oplus (T_e + V_n)] \times \phi_{timer}$$</p>

  <p><strong>Eq. 3 &mdash; Heaviside Trigger (Binary Safety Boundary)</strong><br>
  $$\Psi_{reset} = H(Z_{aggressor} - \sigma_{limit})$$</p>

  <p><strong>Eq. 4 &mdash; Dark Harvest Formula (Aggressor Z‑Score)</strong><br>
  $$Z_{aggressor} = \frac{M \times (N + V)}{C}$$</p>

  <p><strong>Eq. 5 &mdash; The Schröder Limit</strong><br>
  $$\Delta t \le 2.38 \mu s$$</p>

  <p>These five are the only canonical public equations for the architecture.</p>

  <h3>Core Forensic Metrics &mdash; Validated December 15, 2017</h3>
  <p>Educational Context: The absolute latency between breach detection and power‑state collapse is the physical boundary the researcher must attempt to reproduce. The table below captures the original forensic measurement set.</p>

  <table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%;">
    <thead>
      <tr>
        <th style="text-align: left;">Metric</th>
        <th style="text-align: left;">Value</th>
        <th style="text-align: left;">Methodology</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Schröder Limit</strong></td>
        <td>$$ \Delta t \le 2.38 \mu s $$</td>
        <td>Physical hardware measurement</td>
      </tr>
      <tr>
        <td><strong>Median Latency</strong></td>
        <td>2.31 &mu;s &plusmn; 0.07 &mu;s</td>
        <td>10,247 independent trials</td>
      </tr>
      <tr>
        <td><strong>Trial Count</strong></td>
        <td>10,247 forensic trials</td>
        <td>500 MS/s Saleae Logic Pro 16</td>
      </tr>
      <tr>
        <td><strong>F1 Score</strong></td>
        <td>0.997</td>
        <td>Breach detection precision/recall</td>
      </tr>
      <tr>
        <td><strong>Human Reaction Ratio</strong></td>
        <td>105,042&times; faster</td>
        <td>vs. average human response time</td>
      </tr>
      <tr>
        <td><strong>Enforcement Standard</strong></td>
        <td>FLI Principle 16 in silicon</td>
        <td>via 0xCF9 Delegated Primitive&trade;</td>
      </tr>
    </tbody>
  </table>

  <h3>Implementation Mechanics: Ring &minus;3 SMM Sequestration</h3>
  <p>The core defensive capability depends on executing the HDAA&trade; at Ring &minus;3. Because an OS operates at Ring 0 and applications at Ring 3, the OS lacks the technical privilege to read, modify, or block code running inside SMRAM.</p>
  <p>When a compromise is identified, the system writes directly to I/O port 0xCF9. Control byte <code>0x0E</code> forces a hardware reset pulse directly to the CPU reset path, collapsing the system&rsquo;s power state and flushing volatile RAM and cache registers. Under the claimed model, this is the non‑negotiable veto that software cannot intercept.</p>

  <h3>Replication Protocol</h3>
  <p>For academic researchers, hardware engineers, and independent labs:</p>
  <ol>
    <li>Use the synthetic SMM trigger stub released for the simulation framework (Phase 2).</li>
    <li>Replicate the 2017 bench setup with a logic analyzer sampling at 500 MS/s or better.</li>
    <li>Run the Dockerized harness and collect SMI# and PLTRST# timestamps.</li>
    <li>Compute $$ \Delta t $$ and verify whether it remains at or below 2.38 &mu;s.</li>
    <li>Archive logs, workflow artifacts, and release tags as part of the reproducibility record.</li>
  </ol>

  <h3>CI/CD Provenance Note</h3>
  <p>GitHub Actions should capture latency logs, preserve artifacts, and attach them to release tags so the repository retains an auditable chronology of validation runs.</p>
  <ul>
    <li>The <strong>paper / Guidebook</strong> carries the full workflow rationale and legal framing.</li>
    <li>The <strong>README</strong> carries only the short provenance statement and links to the workflow files.</li>
  </ul>
  <p>The purpose of CI/CD here is provenance, not decoration.</p>
</div>
