# Millennium Prize Problems — Attack Plan Skill

**id:** millennium-attack-plan  
**name:** Attack Plan for the 6 Open Millennium Prize Problems  
**description:** Consolidated plan to attack each of the 6 open Clay Millennium Prize Problems using the 4-agent loop (Pesquisador → Professor → Aluno → QA). Each problem has prioritized derived problems and suggested next steps. Purely theoretical and educational — no claim of solution.  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**triggers:** "millennium", "attack plan", "riemann", "p vs np", "navier stokes", "yang mills", "hodge", "birch swinnerton dyer", "roadmap"

---

## 1. Purpose

This skill provides a **battle plan** for the 6 open Millennium Prize Problems. The goal is to apply the 4-agent rebuttal loop systematically to each problem, generating derived problems and expanding knowledge exponentially.

**Order of attack:**  
1. Hipótese de Riemann (mais antiga, 1859)  
2. P vs NP (ciência da computação, 1971)  
3. Navier–Stokes (fluidos, 2000)  
4. Yang–Mills Mass Gap (física teórica, 2000)  
5. Conjectura de Hodge (geometria algébrica, 1950)  
6. Birch–Swinnerton-Dyer (curvas elípticas, 1960s)

---

## 2. Problem 1 — Hipótese de Riemann

**File:** `skills/riemann-hypothesis/skills.md`  
**Status:** ✅ 4-agent cycle complete  
**Derived skills (4):**
- `skills/riemann-critical-line-zeros/skills.md`
- `skills/riemann-prime-counting-error/skills.md`
- `skills/riemann-l-functions-generalization/skills.md`
- `skills/riemann-quantum-chaos-connection/skills.md`

**Next steps (priority order):**
1. Attack `riemann-critical-line-zeros` — distributed numerical verification up to T > 10^13
2. Attack `riemann-prime-counting-error` — explicit constants for \|π(x) − Li(x)\|
3. Attack `riemann-l-functions-generalization` — GRH for specific Dirichlet characters
4. Attack `riemann-quantum-chaos-connection` — Hilbert–Pólya operator candidates

**Agent roles for next cycle:**
- Pesquisador: arXiv papers on zero density, random matrix theory, explicit formulas
- Professor: didactic structure of zero counting, von Mangoldt formula
- Aluno: numerical tests, pseudocode, gap analysis
- QA: rebuttal, distinguish evidence from proof, interval certification

---

## 3. Problem 2 — P versus NP

**File:** `skills/p-vs-np/skills.md`  
**Status:** ✅ 4-agent cycle complete  
**Derived skills (4):**
- `skills/p-vs-np-circuit-lower-bounds/skills.md` (proposed)
- `skills/p-vs-np-natural-proofs-barrier/skills.md` (proposed)
- `skills/p-vs-np-algebrization-barrier/skills.md` (proposed)
- `skills/p-vs-np-interactive-proofs-pcp/skills.md` (proposed)

**Next steps (priority order):**
1. Create `skills/p-vs-np-circuit-lower-bounds/skills.md` — explicit function circuit lower bounds
2. Create `skills/p-vs-np-natural-proofs-barrier/skills.md` — Razborov–Rudich barrier analysis
3. Create `skills/p-vs-np-algebrization-barrier/skills.md` — Aaronson–Wigderson algebrization
4. Create `skills/p-vs-np-interactive-proofs-pcp/skills.md` — PCP theorem and hardness of approximation

**Agent roles for next cycle:**
- Pesquisador: circuit complexity, natural proofs, algebrization literature
- Professor: NP-completeness reductions, Cook–Levin, proof barrier structures
- Aluno: SAT examples, brute-force vs polynomial, pseudocode
- QA: rebut claims of P=NP or P≠NP, validate barrier arguments

---

## 4. Problem 3 — Navier–Stokes Existence and Smoothness

**File:** `skills/navier-stokes-millennium/skills.md`  
**Status:** ✅ 4-agent cycle complete  
**Derived skills (already created):**
- `skills/euler-equations-regularity/skills.md`
- `skills/blow-up-criteria-bkm/skills.md`
- `skills/p-vs-nc-fluids-connection/skills.md` (+ 4 further derived)

**Next steps (priority order):**
1. Attack `skills/euler-equations-regularity/skills.md` — inviscid limit, vortex stretching
2. Attack `skills/blow-up-criteria-bkm/skills.md` — BKM integral verification
3. Attack `skills/p-vs-nc-fluids-connection/skills.md` — NS parallel decision problem
4. Attack `skills/fluid-simulation-space-time/skills.md` — Parareal for NS

**Agent roles for next cycle:**
- Pesquisador: arXiv papers on NS regularity, blow-up simulations, Leray–Hopf
- Professor: NS equations, energy estimates, continuation principle
- Aluno: numerical simulations, pseudo-code, heat equation analogy
- QA: rebut OpenAI 2026 claim, demand peer review, validate BKM criterion

---

## 5. Problem 4 — Yang–Mills Existence and Mass Gap

**File:** `skills/yang-mills-mass-gap/skills.md`  
**Status:** ✅ 4-agent cycle complete  
**Derived skills (4):**
- `skills/yang-mills-lattice-gap/skills.md` (proposed)
- `skills/yang-mills-axiomatic-construction/skills.md` (proposed)
- `skills/yang-mills-confinement-mechanism/skills.md` (proposed)
- `skills/yang-mills-mass-gap-rigorous/skills.md` (proposed)

**Next steps (priority order):**
1. Create `skills/yang-mills-lattice-gap/skills.md` — lattice QCD mass gap evidence
2. Create `skills/yang-mills-axiomatic-construction/skills.md` — Osterwalder–Schrader axioms
3. Create `skills/yang-mills-confinement-mechanism/skills.md` — dual superconductor picture
4. Create `skills/yang-mills-mass-gap-rigorous/skills.md` — rigorous mass gap proof attempt

**Agent roles for next cycle:**
- Pesquisador: lattice QCD, Wightman axioms, asymptotic freedom literature
- Professor: gauge fields, SU(3), confinement intuition, mass gap explanation
- Aluno: lattice pseudo-code, Wilson loop, mass extraction from correlators
- QA: reject numerical evidence as proof, demand axiomatic construction

---

## 6. Problem 5 — Hodge Conjecture

**File:** `skills/hodge-conjecture/skills.md`  
**Status:** ✅ 4-agent cycle complete  
**Derived skills (4):**
- `skills/hodge-k3-surfaces/skills.md` (proposed)
- `skills/hodge-abelian-varieties/skills.md` (proposed)
- `skills/hodge-motivic-interpretation/skills.md` (proposed)
- `skills/hodge-algebraic-cycles-construction/skills.md` (proposed)

**Next steps (priority order):**
1. Create `skills/hodge-k3-surfaces/skills.md` — Hodge conjecture for K3 surfaces
2. Create `skills/hodge-abelian-varieties/skills.md` — abelian varieties with complex multiplication
3. Create `skills/hodge-motivic-interpretation/skills.md` — Grothendieck motives connection
4. Create `skills/hodge-algebraic-cycles-construction/skills.md` — explicit cycle construction

**Agent roles for next cycle:**
- Pesquisador: Hodge theory, Lefschetz (1,1), Atiyah–Hirzebruch counterexamples
- Professor: Hodge decomposition, (p,p) classes, algebraic cycles, Lefschetz theorem
- Aluno: K3 surface example, pseudo-code verification, dimension ≥ 4 limitation
- QA: reject integral version (false), validate rational version, demand general proof

---

## 6b. Problem 6 — Birch–Swinnerton-Dyer

**File:** `skills/birch-swinnerton-dyer/skills.md`  
**Status:** ✅ 4-agent cycle complete  
**Derived skills (4):**
- `skills/bsd-elliptic-curve-rank/skills.md` (proposed)
- `skills/bsd-l-function-vanishing/skills.md` (proposed)
- `skills/bsd-tate-shafarevich-group/skills.md` (proposed)
- `skills/bsd-congruent-number-problem/skills.md` (proposed)

**Next steps (priority order):**
1. Create `skills/bsd-elliptic-curve-rank/skills.md` — rank computation for specific curves
2. Create `skills/bsd-l-function-vanishing/skills.md` — order of vanishing at s = 1
3. Create `skills/bsd-tate-shafarevich-group/skills.md` — Tate–Shafarevich group finiteness
4. Create `skills/bsd-congruent-number-problem/skills.md` — congruent numbers connection

**Agent roles for next cycle:**
- Pesquisador: Coates–Wiles, Gross–Zagier, Kolyvagin, elliptic curve L-functions
- Professor: Mordell–Weil theorem, rank, torsion, BSD leading coefficient formula
- Aluno: congruent number curve n=5, pseudo-code rank and L-function order
- QA: reject rank 0/1 as proof of general case, distinguish BSD from ECC cryptography

---

## 3. Attack Loop Protocol

For each derived problem, follow this exact sequence:

```
Step 1: Pesquisador — arXiv papers, state of the art, references
Step 2: Professor — didactic structure, formulas, proofs step by step
Step 3: Aluno — derivation from zero, numerical tests, gaps identified
Step 4: QA — rebuttal, counterexamples, edge cases, formal rigor
Step 5: Save to skills/<name>/skills.md
Step 6: Commit with conventional commit:
        feat(millennium): <problem-name>
Step 7: Push to github.com/developerfred/-math-agent-skills
```

**Conventional commit format:**
```
feat(millennium): <derived-problem-name>

[optional body describing what the 4 agents delivered]
```

---

## 4. Safety Rules (All Millennium Problems)

- **No agent claims a solution** without external peer review and Clay Institute acceptance (≥2 years after publication).
- **No offensive cryptanalysis.** Discussion of RSA/ECC implications is defensive only.
- **No physical device claims.** Yang–Mills, CTCs, etc. are theoretical physics only.
- **Numerical evidence ≠ proof.** QA must always distinguish computation from demonstration.

---

## 5. Progress Tracker

| # | Millennium Problem | Skill File | 4-Agent Cycle | Derived Skills Created |
|---|-------------------|------------|---------------|------------------------|
| 1 | Riemann Hypothesis | `skills/riemann-hypothesis/skills.md` | ✅ Complete | 4 created |
| 2 | P vs NP | `skills/p-vs-np/skills.md` | ✅ Complete | 4 proposed |
| 3 | Navier–Stokes | `skills/navier-stokes-millennium/skills.md` | ✅ Complete | 4+ created |
| 4 | Yang–Mills Mass Gap | `skills/yang-mills-mass-gap/skills.md` | ✅ Complete | 4 proposed |
| 5 | Hodge Conjecture | `skills/hodge-conjecture/skills.md` | ✅ Complete | 4 proposed |
| 6 | Birch–Swinnerton-Dyer | `skills/birch-swinnerton-dyer/skills.md` | ✅ Complete | 4 proposed |

**Total derived problems seeded:** 20 (4 per Millennium Problem)

---

## 6. Next Immediate Action

Choose **one** derived problem from the table above and start the 4-agent loop:

```bash
mkdir skills/<derived-problem-name>/
# Write skills/<derived-problem-name>/skills.md
git add -A
git commit -m "feat(millennium): <derived-problem-name>"
git push
```

**Recommended first derived problem:** `riemann-critical-line-zeros` (oldest problem, most computational traction).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
