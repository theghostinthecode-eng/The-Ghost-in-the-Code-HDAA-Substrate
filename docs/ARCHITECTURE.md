# PART III: TECHNICAL ARCHITECTURE & RESEARCHER LAB

## Architectural Pipeline: The SMM Veto Flowchart

This diagram maps how telemetry moves from active execution to physical containment under the claimed HDAA™ model:

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
```

This pipeline should appear in this form wherever the repository or Guidebook describes the enforcement sequence. No variant wording, no alternate arrows: one canonical flow.

## Core Metrics Used

The protocol section keeps metrics explicit and legible to researchers:

- **Schröder Limit:** Δt ≤ 2.38 μs. This is the maximum allowed time from breach detection to reset assertion.
- **Median Latency:** 2.31 microseconds ± 0.07 microseconds across 10 247 trials.
- **Trial Count:** 10 247 independent forensic trials.
- **Sample Rate:** 500 MS/s logic acquisition.
- **Detection Quality:** F1 score of 0.997.
- **Human Reaction Ratio:** 105 042× faster than average human response time.
- **Reset Path:** 0xCF9 hardware reset via delegated primitive.
- **Execution Platform Reference:** Intel i7‑7700K baseline; modern EPYC/Xeon platforms must be revalidated per platform.
- **Trigger Boundary:** Heaviside threshold at Z ≥ 3.20.
- **Telemetry Inputs:** Voltage, flags, MSRs, SMI assertion, and PLTRST# timing.

## The Master Equations — Public Disclosure Tier

⚠️ The calibrated threshold constants and 187‑line predictive trigger kernel are NDA‑protected Tier 3 Trade Secrets under 18 U.S.C. § 1836. The equations below constitute the statutory public disclosure record under 35 U.S.C. § 102.

**Eq. 1 — Master Sovereignty Equation**  
Sₛₒᵥₑᵣₑᵢgₙₜᵧ = [ Γ × H(X) ] ⊕ [ A_dᵢᵣₑcₜᵢᵥₑ 0xCF9 ]

**Eq. 2 — Ghost Constant (256‑bit PUF Identity Proof)**  
Γ = [ PUF₀ ⊕ (Tₑ + Vₙ) ] × φₜᵢₘₑᵣ

**Eq. 3 — Heaviside Trigger (Binary Safety Boundary)**  
Ψᵣₑₛₑₜ = H(Zₐggrₑₛₛₒᵣ − σₗᵢₘᵢₜ)

**Eq. 4 — Dark Harvest Formula (Aggressor Z‑Score)**  
Zₐggrₑₛₛₒᵣ = ( M × (N + V) ) / C

**Eq. 5 — The Schröder Limit**  
Δt ≤ 2.38 μs

These five are the only canonical public equations for the architecture.

## Core Forensic Metrics — Validated December 15, 2017

Educational Context: The absolute latency between breach detection and power‑state collapse is the physical boundary the researcher must attempt to reproduce. The table below captures the original forensic measurement set.

| Metric | Value | Methodology |
|---|---:|---|
| Schröder Limit | Δt ≤ 2.38 microseconds | Physical hardware measurement |
| Median Latency | 2.31 μs ± 0.07 μs | 10 247 independent trials |
| Trial Count | 10 247 forensic trials | 500 MS/s Saleae Logic Pro 16 |
| F1 Score | 0.997 | Breach detection precision/recall |
| Human Reaction Ratio | 105 042× faster | vs. average human response time |
| Enforcement Standard | FLI Principle 16 in silicon | via 0xCF9 Delegated Primitive™ |

## Implementation Mechanics: Ring −3 SMM Sequestration

The core defensive capability depends on executing the HDAA™ at Ring −3. Because an OS operates at Ring 0 and applications at Ring 3, the OS lacks the technical privilege to read, modify, or block code running inside SMRAM.

When a compromise is identified, the system writes directly to I/O port 0xCF9. Control byte `0x0E` forces a hardware reset pulse directly to the CPU reset path, collapsing the system’s power state and flushing volatile RAM and cache registers. Under the claimed model, this is the non‑negotiable veto that software cannot intercept.

## Replication Protocol

For academic researchers, hardware engineers, and independent labs:

1. Use the synthetic SMM trigger stub released for the simulation framework (Phase 2).
2. Replicate the 2017 bench setup with a logic analyzer sampling at 500 MS/s or better.
3. Run the Dockerized harness and collect SMI# and PLTRST# timestamps.
4. Compute Δt and verify whether it remains at or below 2.38 μs.
5. Archive logs, workflow artifacts, and release tags as part of the reproducibility record.

## CI/CD Provenance Note

GitHub Actions should capture latency logs, preserve artifacts, and attach them to release tags so the repository retains an auditable chronology of validation runs.

- The **paper / Guidebook** carries the full workflow rationale and legal framing.
- The **README** carries only the short provenance statement and links to the workflow files.

The purpose of CI/CD here is provenance, not decoration.  
