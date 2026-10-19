# Multi-Agent Execution Matrix — All Problems

**id:** execution-matrix  
**name:** 4-Agent Cycle Execution Log for Every Problem  
**description:** Consolidated log of the Researcher → Teacher → Student → QA cycle executed over every problem/skill in the repository. Each entry records what each agent delivered, the QA verdict, and four new derived problems proposed to keep the loop expanding.  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**triggers:** "execution matrix", "all problems", "4-agent cycle", "agent log", "derived problems", "loop"

---

## Purpose

This document is the single source of truth showing that the four agents (**Pesquisador, Professor, Aluno, QA**) have worked over **all problems** currently in the repository. It also seeds the next generation: for every problem, four derived problems are proposed so the discovery loop continues exponentially.

---

## How to read

Each section below corresponds to one skill/problem. For each:

- **Pesquisador**: literature/arXiv/context delivered.
- **Teacher**: didactic structure, proofs, formulas.
- **Student**: derivations, numeric examples, gaps identified.
- **QA**: rebuttals, counterexamples, edge cases, verdict (APROVADO / RESSALVA / REPROVADO / EM ABERTO).
- **4 Derived Problems**: new skill seeds generated from this problem.

---

## 1. Collatz Stopping-Time Heuristic
**File:** `skills/collatz-stopping-time/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | State of the art: verified up to ~2^60, Terras density, Kontorovich stochastic map, arXiv references. |
| **Teacher** | Intuition: average factor √(3/4) < 1; heuristic σ(n) = O(log n); step-by-step model. |
| **Aluno** | σ(7)=16, σ(27)=111, σ(2^k)=k; identified power-of-2 as best case, not average. |
| **QA** | 50-50 parity is asymptotic heuristic, not exact; n=1 and n=2^k approved; complex/negative out of scope. **Verdict: APROVADO COM RESSALVA** (heurística, não prova). |

**4 Derived Problems:**
1. `collatz-statistical-sampling` — empirical σ(n) distribution for n ∈ [1, 10^6] vs log n model.
2. `collatz-cycle-detection` — search for non-trivial cycles beyond 4→2→1→4.
3. `collatz-generalized-3x+k` — generalization to 3n+k for odd k; which k converge?
4. `collatz-parallel-verification` — can Collatz verification up to N be parallelized in NC?

---

## 2. Parallel, GPU and Memory Mathematics
**File:** `skills/parallel-gpu-memory/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Amdahl, Gustafson, Roofline, AMAT, Little's Law references; GPU occupancy and coalescing literature. |
| **Teacher** | Formulas: S(N), E(N), Brent's theorem, Roofline ridge point, AMAT multilevel, GEMM tiling example. |
| **Aluno** | GEMM 1024×1024 numeric example: naive I=0.25 → 125 GFLOP/s memory-bound vs 10 TFLOP/s peak. |
| **QA** | Verified units, byte counts (A+B reads + C write), ridge point I=20 FLOP/Byte; challenged perfect coalescing assumption. **Verdict: APROVADO** (modelo de desempenho educacional). |

**4 Derived Problems:**
1. `gpu-arithmetic-intensity-sweep` — sweep I from 0.1 to 100 on Roofline; map memory/compute bound transitions.
2. `parallel-spmv-load-balance` — sparse matrix-vector multiplication load imbalance on irregular graphs.
3. `memory-wall-scaling` — DRAM latency vs compute gap scaling law; can arithmetic intensity outpace it?
4. `p-nc-gemm-tiling` — is optimal GEMM tile-size selection P-complete or in NC?

---

## 3. Navier–Stokes Millennium Prize
**File:** `skills/navier-stokes-millennium/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Clay Math Institute status; September 2026 OpenAI proposal (Lean formalization, not claiming prize); Clay Institute ≥2-year review rule; problem officially OPEN. |
| **Teacher** | Incompressible NS equations; local existence (Leray/Hopf, Kato); a priori estimates; continuation principle; structure of proof (A) or counterexample (B). |
| **Aluno** | Heat equation vs NS analogy; pseudo-code time-stepping; identified numerical blow-up ≠ proof. |
| **QA** | OpenAI proposal NOT accepted as official proof; 2D/global small-data cases approved; general 3D large-data OPEN. **Verdict: EM ABERTO** (Millennium Prize problem). |

**4 Derived Problems:**
1. `ns-small-data-global-existence` — formalize the small-data global smoothness proof.
2. `ns-leray-hopf-weak-solutions` — properties of Leray–Hopf weak solutions (existence, non-uniqueness).
3. `ns-openai-2026-review` — track independent verification of the September 2026 OpenAI proposal.
4. `ns-energy-equality` — prove or disprove energy equality for weak solutions.

---

## 4. Euler Equations Regularity
**File:** `skills/euler-equations-regularity/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Inviscid case (ν=0); Cauchy–Lagrange local existence; Beale–Kato–Majda reference; OpenAI 2026 mention of Euler regularity. |
| **Teacher** | Vorticity equation ∂ω/∂t + (u·∇)ω = (ω·∇)u; vortex stretching intuition; local existence H^s, s > 5/2. |
| **Aluno** | Vortex-pair stretching thought experiment; pseudo-code Euler step; numerical growth ≠ finite-time blow-up proof. |
| **QA** | BKM criterion approved; global existence OPEN; finite-time blow-up OPEN; Euler blow-up does not imply NS blow-up. **Verdict: EM ABERTO**. |

**4 Derived Problems:**
1. `euler-vortex-stretching-numeric` — numerical study of vortex stretching amplitude growth.
2. `euler-hs-sobolev-threshold` — sharpness of s > 5/2 for local well-posedness.
3. `euler-axisymmetric-swirl` — regularity for axisymmetric Euler with/without swirl.
4. `euler-ns-viscosity-limit` — vanishing viscosity limit ν → 0 and singularity formation.

---

## 5. Beale–Kato–Majda Blow-up Criterion
**File:** `skills/blow-up-criteria-bkm/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Beale–Kato–Majda (1984), CMP; applies to Euler and Navier–Stokes; Millennium relevance. |
| **Teacher** | Statement: ∫₀^T* ||ω||∞ dt = ∞ iff blow-up; contrapositive; Gronwall sketch; Sobolev/Biot–Savart control. |
| **Aluno** | Growth rate (T*−t)^−α examples: α<1 integrable, α≥1 non-integrable; pseudo-code verification. |
| **QA** | BKM theorem approved; does NOT prove blow-up or global smoothness alone; conditional necessary condition only. **Verdict: APROVADO** (theorem), applied to OPEN problem. |

**4 Derived Problems:**
1. `bkm-besov-extensions` — BKM in Besov spaces (Kozono–Taniuchi type criteria).
2. `bkm-serrin-navier-stokes` — Serrin-type regularity criteria for Navier–Stokes.
3. `bkm-numeric-vorticity-infinity` — numerical estimation of ||ω||∞ near singularity; grid sensitivity.
4. `bkm-littlewood-paley` — Littlewood–Paley decomposition for vorticity control.

---

## 6. P vs NC × Fluids Connection
**File:** `skills/p-vs-nc-fluids-connection/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | P, NC, P-complete definitions; Greenlaw/Hoover/Ruzzo; DDP parallelism literature; no known P-completeness for NS. |
| **Teacher** | NS-DECIDE problem statement; circuit-value analogy; sequential time-stepping difficulty; proof structure (P-completeness reduction). |
| **Aluno** | Heat equation parallel FFT per step but sequential time loop; pseudo-code decision problem; identified loop bottleneck. |
| **QA** | NS-DECIDE ∈ P (fixed discretization); P-complete OPEN; P=NC does not imply P=NP. **Verdict: EM ABERTO** (conjectural connection). |

**4 Derived Problems:**
1. `ns-decide-p-complete-reduction` — attempt Circuit Value Problem → NS-DECIDE reduction.
2. `euler-blowup-nc-verification` — is Euler blow-up verification in NC? (see skill #7).
3. `bkm-integral-parallel` — parallel complexity of ∫||ω||∞ dt (see skill #8).
4. `fluid-space-time-parareal` — Parareal/space-time methods for fluids in NC? (see skill #9).

---

## 7. Navier–Stokes Parallel Decision Problem
**File:** `skills/p-vs-nc-navier-stokes-parallel/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | CVP canonical P-complete; parallel PDE solvers (multigrid, domain decomposition, Krylov); parareal literature. |
| **Teacher** | NS-DECIDE formal statement; circuit-to-fluid encoding challenge; P-complete proof structure. |
| **Aluno** | Linear advection is parallelizable; NS nonlinear (u·∇)u couples all points; pseudo-code reduction attempt. |
| **QA** | NS-DECIDE ∈ P (fixed grid); P-complete OPEN; no known CVP reduction; parallel methods accelerate steps, not remove time sequence. **Verdict: EM ABERTO**. |

**4 Derived Problems:**
1. `cvp-to-ns-encoding` — boolean gate encoding in incompressible flow fields.
2. `ns-pressure-projection-complexity` — parallel complexity of the pressure projection step.
3. `ns-time-substepping-parallel` — subcycling/time-refinement parallel complexity.
4. `p-vs-nc-fluid-survey` — survey of known P-complete PDE problems.

---

## 8. Euler Blow-up Parallel Verification
**File:** `skills/euler-blowup-parallel-verification/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | BKM criterion; Hou et al. numerical blow-up evidence; parareal/temporal parallel integration literature. |
| **Teacher** | EULER-BLOWUP decision problem; temporal dependency chain; closed-form absence; NC vs P-complete structure. |
| **Aluno** | Pseudo-code verification loop; max(|ω|) growth; identified per-step parallel but time-sequential bottleneck. |
| **QA** | EULER-BLOWUP ∈ P (fixed discretization); in NC OPEN; P-complete OPEN; BKM is analytic criterion not parallel algorithm. **Verdict: EM ABERTO**. |

**4 Derived Problems:**
1. `euler-blowup-kerr-simulation` — Kerr 1993-type simulation reproducibility study.
2. `euler-hou-li-luo-scenario` — Hou–Li–Luo singularity scenario analysis.
3. `euler-parareal-convergence` — Parareal iteration count for Euler near blow-up.
4. `euler-vorticity-infinity-parallel` — parallel max(|ω|) reduction per time step.

---

## 9. BKM Criterion Parallel Complexity
**File:** `skills/bkm-criterion-parallel-complexity/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | BKM 1984; per-step curl and ||·||∞ parallel reduction; temporal integration bottleneck; parareal references. |
| **Teacher** | BKM-DECIDE problem; space vs time parallelizability; static vs simulated integrand analogy. |
| **Aluno** | Pseudo-code: per-step ||ω||∞ is parallel (reduction), but u(t+dt)=F(u(t)) is sequential; identified time-loop bottleneck. |
| **QA** | ||ω||∞ per step in NC (log-reduction); time integration sequential OPEN; Parareal does not guarantee polylog time. **Verdict: EM ABERTO**. |

**4 Derived Problems:**
1. `bkm-parareal-applicability` — can Parareal accelerate BKM integral evaluation?
2. `bkm-space-time-fem` — space-time finite elements for vorticity integral.
3. `bkm-adaptive-timestepping` — adaptive dt near singularity; parallel complexity impact.
4. `bkm-vorticity-norm-approximation` — approximate ||ω||∞ with parallel probabilistic methods.

---

## 10. Fluid Simulation Space-Time (Parareal)
**File:** `skills/fluid-simulation-space-time/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Lions–Maday–Turinici (2001) Parareal; space-time FEM; multirate methods; no NC proof for fluids. |
| **Teacher** | Parareal intuition: coarse propagator + fine propagator + correction iterations; space-time mesh. |
| **Aluno** | Parareal pseudo-code; identified convergence issues for stiff nonlinear PDEs (Navier–Stokes). |
| **QA** | Parareal accelerates empirically; not NC proof; space-time FEM solves huge system; P-complete/NC both OPEN. **Verdict: EM ABERTO**. |

**4 Derived Problems:**
1. `parareal-ns-stiffness` — Parareal stability for stiff Navier–Stokes regimes.
2. `space-time-fem-ns` — space-time finite element formulation for incompressible NS.
3. `multirate-ns` — multirate time stepping for advection-diffusion-reaction splitting.
4. `p-nc-parareal-bound` — prove or disprove O(log^k T) Parareal iterations for NS.

---

## 11. Time Travel & Teleportation Foundation
**File:** `skills/time-travel-teleportation-foundation/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | CTCs, wormholes, quantum teleportation (Bennett 1993), chronology protection, complexity with CTCs (Aaronson–Watrous). |
| **Teacher** | Lorentzian geometry, Einstein equations, Bell states, quantum channel capacity, CTC computation models. |
| **Aluno** | Gödel metric components; Bell teleportation pseudo-code; identified classical communication necessity. |
| **QA** | Distinguished quantum teleportation (information) from sci-fi matter teleportation; no FTL signaling. **Verdict: APROVADO** (theoretical framework). |

**4 Derived Problems:**
1. `closed-timelike-curves` — Gödel, Tipler, Morris–Thorne (see skill #12).
2. `quantum-teleportation` — Bell states, no-cloning, classical channel (see skill #13).
3. `chronology-protection` — Hawking conjecture, vacuum polarization (see skill #14).
4. `spacetime-simulation-complexity` — CTC spacetime simulation NC vs P-complete (see skill #15).

---

## 12. Closed Timelike Curves
**File:** `skills/closed-timelike-curves/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Gödel (1949), Tipler cylinder, Morris–Thorne (1988), exotic matter/energy condition literature. |
| **Teacher** | Gödel metric, Tipler metric, Morris–Thorne wormhole metric, flare-out condition b'(b₀)<1, NEC violation. |
| **Aluno** | Gödel g_φφ<0 regions; flare-out derivation; pseudo-code CTC check; identified metric≠physical evidence gap. |
| **QA** | Gödel/Tipler/wormhole metrics approved mathematically; exotic matter macroscopic existence unknown; time travel physical realization speculative. **Verdict: APROVADO** (math), ESPECULATIVO (physics). |

**4 Derived Problems:**
1. `ctc-cauchy-horizon` — Cauchy horizon formation in CTC spacetimes.
2. `wormhole-stability` — linear stability analysis of Morris–Thorne wormholes.
3. `exotic-matter-quantum-inequalities` — Ford–Roman bounds on negative energy density.
4. `ctc-grandfather-paradox` — logical consistency models (Novikov self-consistency).

---

## 13. Quantum Teleportation
**File:** `skills/quantum-teleportation/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Bennett–Brassard–Crépeau–Jozsa–Peres–Wootters (1993); Bell states; no-cloning; experimental verification. |
| **Teacher** | Full protocol: Bell basis, CNOT+Hadamard, 2 classical bits, Pauli corrections (I, X, Z, ZX). |
| **Aluno** | 3-qubit state derivation; pseudo-code protocol; identified classical 2-bit channel as mandatory. |
| **QA** | Approved for quantum information; rejects matter/energy teleportation; rejects FTL; no-cloning respected. **Verdict: APROVADO** (established protocol). |

**4 Derived Problems:**
1. `teleportation-continuous-variables` — CV quantum teleportation (squeezed states).
2. `entanglement-swapping` — entanglement swapping and quantum repeaters.
3. `quantum-channel-capacity` — Holevo bound and teleportation capacity.
4. `teleportation-fidelity-noise` — teleportation fidelity under depolarizing/dephasing noise.

---

## 14. Chronology Protection
**File:** `skills/chronology-protection/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Hawking (1992) chronology protection conjecture; Ford–Roman quantum inequalities; Cauchy horizon divergence. |
| **Teacher** | Vacuum polarization divergence at Cauchy horizon; ⟨Tμν⟩ → ∞; Einstein equation singularity before CTCs. |
| **Aluno** | Blueshift accumulation near Cauchy horizon; pseudo-code vacuum polarization; identified quantum gravity gap. |
| **QA** | Conjecture NOT theorem; semiclassical evidence only; quantum inequalities limit exotic matter; CTC physical impossibility unproven. **Verdict: EM ABERTO** (conjecture). |

**4 Derived Problems:**
1. `ctc-complexity-aaronson-watrous` — P = PSPACE with CTCs (computation model, not physics).
2. `semiclassical-gravity-ctc` — semiclassical gravity backreaction on CTC formation.
3. `quantum-inequality-wormhole` — quantum inequality constraints on traversable wormholes.
4. `chronology-protection-proof-status` — current status of proofs/counterexamples to Hawking's conjecture.

---

## 15. Spacetime Simulation Complexity
**File:** `skills/spacetime-simulation-complexity/skills.md`

| Agent | Delivery |
|-------|----------|
| **Pesquisador** | Numerical relativity 3+1 ADM; Aaronson–Watrous (CTC computation P=PSPEC); Greenlaw P-completeness. |
| **Teacher** | ST-DECIDE problem; sequential time-slice dependency; CTC computation model vs physical reality distinction. |
| **Aluno** | Pseudo-code Einstein evolution; identified 3+1 time-step sequential bottleneck; parareal connection. |
| **QA** | ST-DECIDE ∈ P (fixed discretization); P-complete OPEN; Aaronson–Watrous is theoretical computing model, not physical claim. **Verdict: EM ABERTO**. |

**4 Derived Problems:**
1. `einstein-3p1-parallel` — parallelism in ADM evolution equations.
2. `binary-black-hole-nc` — parallel complexity of binary black hole merger simulations.
3. `ctc-circuit-model` — circuit model with CTCs; complexity class implications.
4. `spacetime-parareal-einstein` — Parareal for Einstein equations; convergence for nonlinear gravity.

---

## Summary of Agent Coverage

| # | Problem/Skill | Pesquisador | Professor | Aluno | QA | Status |
|---|---------------|-------------|-----------|-------|-----|--------|
| 1 | Collatz stopping-time | ✅ | ✅ | ✅ | ✅ | Aprovado com ressalva |
| 2 | Parallel GPU Memory | ✅ | ✅ | ✅ | ✅ | Aprovado |
| 3 | Navier–Stokes Millennium | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 4 | Euler Regularity | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 5 | BKM Blow-up Criteria | ✅ | ✅ | ✅ | ✅ | Aprovado (teorema) |
| 6 | P vs NC × Fluids | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 7 | NS Parallel Decision | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 8 | Euler Blow-up NC | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 9 | BKM Parallel Complexity | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 10 | Fluid Space-Time/Parareal | ✅ | ✅ | ✅ | ✅ | Em aberto |
| 11 | Time Travel/Teleport Foundation | ✅ | ✅ | ✅ | ✅ | Aprovado (framework) |
| 12 | Closed Timelike Curves | ✅ | ✅ | ✅ | ✅ | Aprovado (math) |
| 13 | Quantum Teleportation | ✅ | ✅ | ✅ | ✅ | Aprovado (protocol) |
| 14 | Chronology Protection | ✅ | ✅ | ✅ | ✅ | Em aberto (conjecture) |
| 15 | Spacetime Simulation Complexity | ✅ | ✅ | ✅ | ✅ | Em aberto |

**Total:** 15 problems × 4 agents = **60 agent deliveries completed.**  
**Derived problems seeded:** 15 × 4 = **60 new skill candidates** (many already created as skills #3–15 above).

---

## Next Cycle

To keep the loop expanding, pick any derived problem above, create its skill file, and run the same 4-agent cycle:

```
feat(domain): new derived problem from <parent-skill>
```

Then push:
```bash
git push
```

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
