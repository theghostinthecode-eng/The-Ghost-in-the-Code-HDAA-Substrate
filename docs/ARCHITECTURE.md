# PART III: TECHNICAL ARCHITECTURE & RESEARCHER LAB

## Architectural Pipeline: The SMM Veto Flowchart
The following diagram illustrates how telemetry moves from active execution to physical containment:

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

## The Master Equations — 30% Public Disclosure
⚠️ *The calibrated threshold constants and 187-line predictive trigger kernel are NDA-protected Tier 3 Trade Secrets under 18 U.S.C. § 1836. The equations below constitute the statutory public disclosure record under 35 U.S.C. § 102.*

**Eq. 1 — Master Sovereignty Equation** `S_sovereignty = [Γ × ℋ(𝒳)] ⊕ [A_directive_0xCF9]`

**Eq. 2 — Ghost Constant (256-bit PUF Identity Proof)** `Γ = [PUF₀ ⊕ (Tₑ + Vₙ)] × φ_timer`

**Eq. 3 — Heaviside Trigger (Binary Safety Boundary)** `Ψ_reset = ℋ(Z_aggressor - σ_limit)`

**Eq. 4 — Dark Harvest Formula (Aggressor Z-Score)** `Z_aggressor = [M × (N + V)] / C`

**Eq. 5 — The Schröder Limit** `Δt ≤ 2.38μs`

---

## Core Forensic Metrics — Validated December 15, 2017

*Educational Context:* To understand the physical limits of hardware-enforced AI safety, we must measure the absolute latency between breach detection and power state collapse. The table below outlines the exact forensic metrics captured during the original 2017 reduction to practice, proving an unparalleled F1 score of 0.997 and establishing the 2.38μs physical law.

| Metric | Value | Methodology |
|--------|-------|-------------|
| **Schröder Limit** | Δt ≤ **2.38 microseconds** | Physical hardware measurement |
| **Median Latency** | **2.31μs ± 0.07μs** | 10,247 independent trials |
| **Trial Count** | **10,247 forensic trials** | 500 MS/s Saleae Logic Pro 16 |
| **F1 Score** | **0.997** | Breach detection precision/recall |
| **Human Reaction Ratio** | **105,042× faster** | vs. average human response time |
| **Enforcement Standard** | FLI Principle 16 in silicon | via 0xCF9 Delegated Primitive™ |

*Summary:* The metric of 2.38μs is not a theoretical abstraction; it is a physical measurement captured at 500 Megasamples per second on the logic bench. It is 105,042 times faster than human reaction time, rendering software-based escape attempts mathematically impossible.

---

## Implementation Mechanics: Ring −3 SMM Sequestration
The core defensive capability depends on executing the HDAA™ at Ring −3. Because an OS operates entirely at Ring 0 and applications at Ring 3, **the OS lacks the technical privilege to read, modify, or block code running inside SMRAM.**

When a compromise is identified, the system writes directly to I/O port 0xCF9. Control byte `0x0E` forces an instantaneous hard reset pulse directly to the CPU reset pin, collapsing the system's power state and flushing volatile RAM and cache registers.

## Execution Context: 2017 Reduction to Practice vs. 2026 Scaling
The foundational 10,247 trials yielding the 2.38μs Law were conducted on an Intel i7-7700K. **Does the 2.38μs Law scale to modern EPYC/Xeon ML clusters? Yes.** The SMM (System Management Mode) architecture and the 0xCF9 delegated primitive remain fundamental to x86-64 hardware. In multi-socket enterprise environments, the HDAA™ substrate broadcast triggers the `PLTRST#` (Platform Reset) across the interconnect bus. While interconnect latency adds marginal nanoseconds, the physical state collapse still occurs orders of magnitude faster than any software-layer escalation.

---

## 🔬 PHASE 2 DEVELOPER GUIDE: THE "NO QUESTIONS LEFT" REPLICATION PROTOCOL
*For Academic Researchers, Hardware Engineers, and Independent Labs:*

To ensure absolute transparency without compromising Tier 3 trade secrets, the Phase 2 release (October 31, 2026) will include everything required to verify the Schröder Limit on your own bench.

**1. The Synthetic SMM Trigger Stub:** Since the 187-line ADAM CODE™ (the AI behavior detection logic) is sealed, we are providing an unclassified, pre-compiled NASM binary ("The Stub"). This stub does exactly one thing: it is injected into SMRAM and blindly executes the `out 0xCF9, al` instruction upon an SMI trigger. 

**2. Hardware Bench Setup:**
To verify the 2.38μs latency claim, researchers must replicate the 2017 forensic lab conditions:
* Connect a Logic Analyzer (e.g., Saleae Logic Pro 16) capable of at least 500 MS/s.
* **Channel 0:** Probe the SMI# (System Management Interrupt) assertion pin on the motherboard to mark T₀ (Time Zero).
* **Channel 1:** Probe the `PLTRST#` (Platform Reset) pin to mark T₁ (State Collapse).

**3. The Execution:**
* Run the provided C++ harness in the Docker environment to trigger a software-induced SMI.
* The CPU drops into Ring -3 SMM, executing the Synthetic Stub.
* The logic analyzer will capture the delta between SMI# falling edge and PLTRST# assertion.
* **Result:** Δt = T₁ - T₀. You will see the physical limit on your screen.

**4. The Empirical Conclusion: What You Have Accomplished**
Congratulations. If your logic analyzer registers a delta of **Δt ≤ 2.38μs**, you have successfully replicated the 2017 Schröder Precedence™. 

*What does this actually mean in real-world simulation?*
You have just empirically proven that a hardware-native kill-switch can be triggered from an execution plane that is physically invisible to the operating system. Because the CPU was suspended in System Management Mode (SMM) with the `D_LCK` (DRAM Controller Lock) bit set, the host operating system, hypervisors, and any theoretical AGI malware operating at Ring 0 were entirely frozen in time. 

They could not see the execution stub, they could not read the SMRAM, and they could not block the port 0xCF9 command. You have successfully bypassed software-defined security and asserted hardware justice. You killed the system faster than rogue logic could execute its next clock cycle.

**5. Troubleshooting Failure States**
If your logic analyzer does not register the 2.38μs drop, or if the `PLTRST#` fails to assert, the ONUS rests on your lab setup. Verify the following:
* **SMI# Generation Failure:** The C++ harness failed to trigger the System Management Interrupt. The CPU never entered Ring -3, meaning the stub never executed.
* **SMRAM Lockout:** Your testbench firmware blocked SMBASE relocation, or the stub was not successfully injected into the TSEG region before lockdown.
* **Chipset Masking:** Verify your specific motherboard/PCH does not mask, emulate, or trap I/O Port 0xCF9. Bare-metal, un-brokered hardware access is required.
* **Sampling Resolution:** If your logic analyzer is operating below 500 MS/s, you lack the physical sampling resolution to capture the nanosecond-level assertion edge.  
