## PART III: TECHNICAL ARCHITECTURE & RESEARCHER LAB

## Architectural Pipeline: The SMM Veto Flowchart

This diagram maps how telemetry moves from active execution to physical containment.

```text
[ AI Agent Execution (Ring 3 / Ring 0) ]
        │
        ▼
[ Hardware Telemetry Extraction (Voltage, Flags, MSRs) ]
        │
        ▼
[ RING -3 SMM WATCHDOG (Invisible to OS/AI) ]
        │
        ├─► [ The Dark Harvest Formula ]
        │     Calculates Z-Score (Malice/Velocity)
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
      [ Total Time: Δt ≤ 2.38μs ]
```

## The Master Equations — Public Disclosure Tier

⚠️ The calibrated threshold constants and 187-line predictive trigger kernel are NDA-protected Tier 3 Trade Secrets under 18 U.S.C. § 1836. The equations below constitute the statutory public disclosure record under 35 U.S.C. § 102.

**Eq. 1 — Master Sovereignty Equation**  
\(S_{sovereignty} = [\Gamma \times \mathcal{H}(\mathcal{X})] \oplus [\mathcal{A}_{directive\_0xCF9}]\)

**Eq. 2 — Ghost Constant (256-bit PUF Identity Proof)**  
\(\Gamma = [PUF_0 \oplus (T_e + V_n)] \times \phi_{timer}\)

**Eq. 3 — Heaviside Trigger (Binary Safety Boundary)**  
\(\Psi_{reset} = \mathcal{H}(Z_{aggressor} - \sigma_{limit})\)

**Eq. 4 — Dark Harvest Formula (Aggressor Z-Score)**  
\(Z_{aggressor} = [M \times (N + V)] / C\)

**Eq. 5 — The Schröder Limit**  
\(\Delta t \leq 2.38\mu s\)

## Core Forensic Metrics — Validated December 15, 2017

Educational Context: the absolute latency between breach detection and power-state collapse is the physical boundary the researcher must reproduce. The table below captures the original forensic measurement set.

| Metric | Value | Methodology |
|---|---:|---|
| Schröder Limit | Δt ≤ 2.38 microseconds | Physical hardware measurement |
| Median Latency | 2.31μs ± 0.07μs | 10,247 independent trials |
| Trial Count | 10,247 forensic trials | 500 MS/s Saleae Logic Pro 16 |
| F1 Score | 0.997 | Breach detection precision/recall |
| Human Reaction Ratio | 105,042× faster | vs. average human response time |
| Enforcement Standard | FLI Principle 16 in silicon | via 0xCF9 Delegated Primitive™ |

## Implementation Mechanics: Ring -3 SMM Sequestration

The core defensive capability depends on executing the HDAA™ at Ring -3. Because an OS operates at Ring 0 and applications at Ring 3, the OS lacks the technical privilege to read, modify, or block code running inside SMRAM.

When a compromise is identified, the system writes directly to I/O port 0xCF9. Control byte 0x0E forces a hardware reset pulse directly to the CPU reset path, collapsing the system’s power state and flushing volatile RAM and cache registers.

## Execution Context: 2017 Reduction to Practice vs. 2026 Scaling

The foundational 10,247 trials yielding the 2.38μs Law were conducted on an Intel i7-7700K. The scaling question for 2026 EPYC/Xeon-class environments is whether the same reset path remains observable and measurable under modern enterprise hardware.

The answer to that question must be demonstrated by instrumentation, not by assumption. The SMM architecture and the 0xCF9 delegated primitive remain fundamental to x86-64 hardware, but the replication environment must be explicitly documented per platform.

## Phase 2 Developer Guide: The “No Questions Left” Replication Protocol

For academic researchers, hardware engineers, and independent labs:

1. The Synthetic SMM Trigger Stub. Since the 187-line ADAM CODE™ remains sealed, the release will include an unclassified, pre-compiled NASM binary that executes the 0xCF9 reset sequence on SMI trigger.
2. Hardware Bench Setup. Researchers must replicate the 2017 forensic lab conditions using a logic analyzer capable of at least 500 MS/s.
3. Execution. Run the supplied C++ harness in Docker, trigger the software-induced SMI, and record the delta between SMI# assertion and PLTRST# assertion.
4. Empirical Conclusion. If the logic analyzer registers Δt ≤ 2.38μs, the replication has succeeded.
5. Troubleshooting. If the result does not appear, verify SMI generation, SMRAM lock behavior, chipset handling of 0xCF9, and sample-rate resolution.
 
