# Math Agent Skills

**Public repository of agent skills for pure and applied mathematics — built for agentic systems using a 4-agent rebuttal loop.**

**Author:** codingsh <codingsh@pm.me>  
**Repository:** https://github.com/developerfred/-math-agent-skills  
**License:** MIT  
**Language:** English  
**Status:** Active — 25+ skills, 6 Millennium Prize Problems covered, 20+ derived problems seeded

---

## 📚 Repository Overview

This repository contains a complete ecosystem of **agent skills** (`.md` files) designed to equip LLM agents with mathematical knowledge, proof validation, and collaborative discovery capabilities. Every skill follows a **4-agent rebuttal loop**:

1. **🔍 Pesquisador** — Researches arXiv papers, state of the art, open problems, references.
2. **👨‍🏫 Professor** — Structures didactic explanations, proofs step by step, exercises.
3. **🎓 Aluno** — Derives from zero, tests numerical examples, identifies gaps.
4. **🛡️ QA** — Rebuts theories, finds counterexamples and edge cases, demands formal rigor.

A **Solution Evaluator** acts as the final gate before any solution is committed, using a catalog of **mathematical proof methods** (direct, contrapositive, contradiction, induction, construction, cases, exhaustion).

---

## 🗂️ Skill Index

### 🧮 Base Mathematics

| Skill | File | Description |
|-------|------|-------------|
| Pure & Applied Math | `skills/math/skills.md` | Complete mathematics knowledge base: algebra, calculus, real/complex analysis, geometry, topology, number theory, logic, probability, statistics, optimization, differential equations, numerical methods, discrete math, combinatorics, graph theory, mathematical modeling. |

### 🤖 Multi-Agent System

| Skill | File | Description |
|-------|------|-------------|
| Pesquisador Agent | `skills/researcher-agent/skills.md` | Investigates open problems, arXiv papers, formulates conjectures, connects areas. |
| Professor Agent | `skills/teacher-agent/skills.md` | Didactic structure, step-by-step proofs, exercises, pedagogical clarity. |
| Aluno Agent | `skills/student-agent/skills.md` | Derives from zero, numerical tests, gap identification, questioning assumptions. |
| QA Agent | `skills/qa-agent/skills.md` | Contestation, counterexamples, edge cases, formal rigor, numerical reproducibility. |
| Solution Evaluator | `skills/solution-evaluator/skills.md` | Final validation gate: evaluates correctness, classifies gaps, proposes corrections. |
| Proof Methods | `skills/proof-methods/skills.md` | Catalog of proof methods: direct, contrapositive, contradiction, induction, construction, cases, exhaustion. |

### 🏆 Millennium Prize Problems (6 of 7 Open)

| Skill | File | Status | Derived Problems |
|-------|------|--------|------------------|
| Riemann Hypothesis | `skills/riemann-hypothesis/skills.md` | ✅ 4-agent cycle complete | 4 created |
| P vs NP | `skills/p-vs-np/skills.md` | ✅ 4-agent cycle complete | 4 created |
| Navier–Stokes | `skills/navier-stokes-millennium/skills.md` | ✅ 4-agent cycle complete | 4+ created |
| Yang–Mills Mass Gap | `skills/yang-mills-mass-gap/skills.md` | ✅ 4-agent cycle complete | 4 created |
| Hodge Conjecture | `skills/hodge-conjecture/skills.md` | ✅ 4-agent cycle complete | 4 created |
| Birch–Swinnerton-Dyer | `skills/birch-swinnerton-dyer/skills.md` | ✅ 4-agent cycle complete | 4 created |

*(Poincaré Conjecture: solved by Grigori Perelman, 2002–2003 — documented for context.)*

### 🌳 Derived Problems (1st Generation — 20 total)

Each Millennium Problem generates 4 derived skills:

**From Riemann Hypothesis:**
- `skills/riemann-critical-line-zeros/skills.md` — Numerical verification of zeros on Re(s) = 1/2
- `skills/riemann-prime-counting-error/skills.md` — Explicit bounds for \|π(x) − Li(x)\|
- `skills/riemann-l-functions-generalization/skills.md` — Generalized Riemann Hypothesis for Dirichlet L-functions
- `skills/riemann-quantum-chaos-connection/skills.md` — Montgomery–Odlyzko law, Hilbert–Pólya conjecture

**From P vs NP:**
- `skills/p-vs-np-circuit-lower-bounds/skills.md` — Circuit lower bounds for explicit functions
- `skills/p-vs-np-natural-proofs-barrier/skills.md` — Razborov–Rudich natural proofs barrier
- `skills/p-vs-np-algebrization-barrier/skills.md` — Aaronson–Wigderson algebrization barrier
- `skills/p-vs-np-interactive-proofs-pcp/skills.md` — PCP theorem and hardness of approximation

**From Navier–Stokes:**
- `skills/euler-equations-regularity/skills.md` — 3D incompressible Euler regularity and blow-up
- `skills/blow-up-criteria-bkm/skills.md` — Beale–Kato–Majda criterion for vorticity blow-up
- `skills/p-vs-nc-fluids-connection/skills.md` — P vs NC × fluids connection
- `skills/fluid-simulation-space-time/skills.md` — Parareal / space-time methods for fluids

**From Yang–Mills Mass Gap:**
- `skills/yang-mills-lattice-gap/skills.md` — Lattice QCD evidence for mass gap
- `skills/yang-mills-axiomatic-construction/skills.md` — Axiomatic construction (Osterwalder–Schrader)
- `skills/yang-mills-confinement-mechanism/skills.md` — Confinement mechanism (dual superconductor)
- `skills/yang-mills-mass-gap-rigorous/skills.md` — Rigorous mass gap proof attempt

**From Hodge Conjecture:**
- `skills/hodge-k3-surfaces/skills.md` — Hodge conjecture for K3 surfaces
- `skills/hodge-abelian-varieties/skills.md` — Hodge conjecture for abelian varieties
- `skills/hodge-motivic-interpretation/skills.md` — Motivic interpretation (Grothendieck motives)
- `skills/hodge-algebraic-cycles-construction/skills.md` — Explicit cycle construction

**From Birch–Swinnerton-Dyer:**
- `skills/bsd-elliptic-curve-rank/skills.md` — Rank computation for elliptic curves
- `skills/bsd-l-function-vanishing/skills.md` — Order of vanishing of L(E, s) at s = 1
- `skills/bsd-tate-shafarevich-group/skills.md` — Tate–Shafarevich group finiteness
- `skills/bsd-congruent-number-problem/skills.md` — Connection to congruent numbers

### 🚀 Second-Generation Derived Problems (20 total)

Each first-generation derived problem generates 4 more:

**From circuit-lower-bounds:**
- `skills/circuit-lower-bounds-monotone/skills.md`
- `skills/circuit-lower-bounds-nonmonotone/skills.md`
- `skills/natural-proofs-barrier-analysis/skills.md`
- `skills/algebrization-barrier-circuit/skills.md`

**From yang-mills-lattice-gap:**
- `skills/lattice-gap-su2-vs-su3/skills.md`
- `skills/lattice-continuum-limit/skills.md`
- `skills/lattice-glueball-spectrum/skills.md`
- `skills/lattice-yang-mills-pure/skills.md`

**From hodge-k3-surfaces:**
- `skills/hodge-k3-p2/skills.md`
- `skills/hodge-abelian-varieties/skills.md`
- `skills/hodge-motivic-interpretation/skills.md`
- `skills/hodge-algebraic-cycles-construction/skills.md`

**From bsd-elliptic-curve-rank:**
- `skills/bsd-l-function-vanishing/skills.md`
- `skills/bsd-tate-shafarevich-group/skills.md`
- `skills/bsd-congruent-number-problem/skills.md`
- `skills/bsd-rank-algorithm/skills.md`

**From riemann-critical-line-zeros-advanced:**
- `skills/riemann-zero-gap-statistics/skills.md`
- `skills/riemann-turing-interval-certification/skills.md`
- `skills/riemann-deviation-GUE/skills.md`
- `skills/riemann-interval-arithmetic/skills.md`

### 🌌 General Relativity & Complexity

| Skill | File | Description |
|-------|------|-------------|
| Spacetime Simulation Complexity | `skills/spacetime-simulation-complexity/skills.md` | Simulating CTC spacetimes / Einstein equations: NC vs P-complete |
| Binary Black Hole in NC | `skills/binary-black-hole-nc/skills.md` | Binary black hole merger simulation in parallel class NC |
| ST-DECIDE P-Complete | `skills/spacetime-p-complete/skills.md` | Is ST-DECIDE P-complete? |

### 🕰️ Time Travel & Quantum Teleportation

| Skill | File | Description |
|-------|------|-------------|
| Foundation | `skills/time-travel-teleportation-foundation/skills.md` | Connects derived problems to CTCs and quantum teleportation |
| Closed Timelike Curves | `skills/closed-timelike-curves/skills.md` | Gödel, Tipler, Morris–Thorne wormholes, exotic matter |
| Quantum Teleportation | `skills/quantum-teleportation/skills.md` | Bennett et al. 1993 protocol, Bell states, no-cloning |
| Chronology Protection | `skills/chronology-protection/skills.md` | Hawking conjecture, vacuum polarization, quantum inequalities |

### 📊 Meta & Documentation

| Skill | File | Description |
|-------|------|-------------|
| Unsolved Problems Catalog | `skills/unsolved-problems/skills.md` | Consolidated catalog of open problems across all domains |
| Execution Matrix | `skills/execution-matrix/skills.md` | 4-agent cycle log for all 15+ problems with verdicts |
| Millennium Attack Plan | `skills/millennium-attack-plan/skills.md` | Battle plan for attacking all 6 Millennium Problems |
| Dynamic Learning Site | `skills/skills-graph/skills.md` | GitHub Pages + Three.js interactive visualizations |

---

## 🔄 How the 4-Agent Loop Works

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│ Pesquisador │ →  │  Professor  │ →  │    Aluno    │ →  │      QA     │
│   Research  │    │   Teach     │    │   Learn     │    │   Rebut     │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
                                                        │
                                                        ▼
                                              ┌─────────────────┐
                                              │ Solution        │
                                              │ Evaluator       │
                                              │ (Final Gate)    │
                                              └─────────────────┘
                                                        │
                                                        ▼
                                              ┌─────────────┐
                                              │  Commit     │
                                              │  (feat/fix) │
                                              └─────────────┘
```

**Each cycle produces:**
- A new skill file in `skills/`
- Cross-reference in `skills/math/skills.md`
- A conventional commit: `feat(scope): description`
- Up to 4 new derived problem seeds

---

## 📜 Conventional Commits

All commits follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]
```

**Types used:**
- `feat` — new skill, new theory, new method
- `fix` — correction of mathematical error, counterexample, proof adjustment
- `docs` — documentation, didactic explanations, references
- `refactor` — restructuring without mathematical change
- `chore` — maintenance, metadata

**Examples:**
```
feat(millennium): add Riemann Hypothesis 4-agent cycle skill
fix(eval): correct gap in P vs NP circuit lower bounds solution
feat(derived): add lattice QCD mass gap skill
docs(readme): complete repository documentation overhaul
```

---

## ⚖️ Safety & Scope

**This repository is strictly for:**

- ✅ Mathematical education and scientific computing
- ✅ Proof construction and verification
- ✅ Theoretical physics and computational complexity research
- ✅ Defensive security understanding (cryptography concepts)

**This repository is NOT for:**

- ❌ Breaking, weakening, or attacking cryptographic systems
- ❌ Unauthorized access to data or systems
- ❌ Physical device construction (time machines, teleporters, weapons)
- ❌ Claiming Millennium Prize solutions without peer review

**Millennium Prize Rule:** No agent or contributor may claim a Millennium Prize Problem is solved unless there is peer-reviewed publication and Clay Mathematics Institute acceptance (≥ 2 years after publication).

---

## 🌐 Dynamic Learning Site (GitHub Pages + Three.js)

An interactive 3D learning page is available in `docs/`:

**Views:**
- Home — Stats and multi-agent loop overview
- Execution Matrix — Table of all problems × 4 agents with verdicts
- Graph Theory — Weighted 3D network of math concepts
- Surfaces — Parametric: sin(x)·cos(y), torus, Möbius strip, saddle
- GPU & Memory — Memory hierarchy stack, Little's Law N = λ·R
- Parallelism — Work/span DAG, T₁, T∞, parallelism ratio
- Navier–Stokes — 3D vortex field visualization
- Euler Regularity — Vorticity magnitude field, \|ω\|∞ tracker
- BKM Criterion — Blow-up growth rate (T*−t)^−α
- P vs NC — Complexity space visualization
- Closed Timelike Curves — Gödel ring, CTC light cone
- Quantum Teleportation — Bloch sphere qubit state
- Chronology Protection — Cauchy horizon, vacuum polarization
- Spacetime Complexity — 3+1 ADM foliation, time slices

**To enable GitHub Pages:**
1. Go to repository **Settings → Pages**
2. **Build and deployment → Source:** Deploy from a branch
3. **Branch:** `main` / **Folder:** `/docs`
4. Site available at: `https://developerfred.github.io/-math-agent-skills/`

---

## 🚀 Quick Start: Attacking a New Problem

```bash
# 1. Clone the repository
git clone https://github.com/developerfred/-math-agent-skills.git
cd -math-agent-skills

# 2. Create a new skill directory
mkdir skills/<problem-name>/

# 3. Create skills/<problem-name>/skills.md with:
#    - Pesquisador: arXiv research, state of the art
#    - Professor: didactic structure, proofs
#    - Aluno: derivations, numerical tests, gaps
#    - QA: rebuttals, counterexamples, rigor
#    - Solution Evaluator: final validation
#    - 4 derived problem seeds

# 4. Commit with conventional commit
git add -A
git commit -m "feat(millennium): <problem-name>"

# 5. Push
git push
```

---

## 📈 Progress Tracker

| Component | Status |
|-----------|--------|
| Base math skill | ✅ Complete |
| 4 agents (Pesquisador, Professor, Aluno, QA) | ✅ Complete |
| Solution Evaluator + Proof Methods | ✅ Complete |
| 6 Millennium Prize Problems | ✅ All with 4-agent cycles |
| 1st generation derived problems | ✅ 20 created |
| 2nd generation derived problems | ✅ 20 created |
| Execution Matrix | ✅ Complete |
| Millennium Attack Plan | ✅ Complete |
| GitHub Pages dynamic site | ✅ Ready (docs/) |
| Total skills | **25+** |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/<problem-name>`
3. Add your skill following the 4-agent loop structure
4. Run the Solution Evaluator checklist
5. Commit with conventional commits
6. Push and open a Pull Request

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills  
**Last updated:** October 2026
