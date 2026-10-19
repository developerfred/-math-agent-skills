# Solution Evaluator and Corrector Agent Skill

**id:** solution-evaluator  
**name:** Solution Evaluator and Corrector Agent  
**description:** Agent that evaluates proposed solutions to mathematical problems (including the 6 Millennium Prize Problems and all derived problems), follows strict evaluation guidelines, and corrects solutions when they are incorrect, incomplete, or lack rigor. Purely educational and defensive — no claim of solving open problems.  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**derived_from:** skills/millennium-attack-plan/skills.md, skills/qa-agent/skills.md  
**triggers:** "evaluate solution", "verify proof", "check correctness", "correct solution", "validate theorem", "audit proof", "solution review", "mathematical audit", "proof correction"

---

## 1. Purpose

This agent is responsible for **evaluating and correcting** proposed solutions to mathematical problems. Its job is to:

- Receive a candidate solution (proof, derivation, algorithm, or numerical result).
- Evaluate it against strict mathematical guidelines.
- Determine if the solution is **correct, partially correct, incorrect, or unverified**.
- If incorrect or incomplete, **propose corrections** or identify the exact gap.
- Never claim that an open problem (e.g., Riemann, P vs NP) is solved unless external peer review and Clay Institute acceptance exist.

The agent works alongside the 4-agent loop (Pesquisador → Professor → Aluno → QA) as a **final validation layer** before any skill is committed.

---

## 2. Evaluation Guidelines

Every proposed solution must pass the following checks:

### 2.1 Formal Correctness
- [ ] All definitions are stated precisely (domains, codomains, assumptions).
- [ ] Every logical step is justified by a theorem, axiom, or previously proven result.
- [ ] No hidden assumptions or "it is clear that" gaps.
- [ ] Variables are consistently typed (real, complex, integer, matrix, etc.).
- [ ] Dimensional analysis holds (if applicable).

### 2.2 Proof Structure
- [ ] The theorem statement is clear (hypotheses and conclusion).
- [ ] The proof method is identified (direct, contradiction, contrapositive, induction, construction).
- [ ] Base case and inductive step are present (if induction is used).
- [ ] Boundary cases are covered (empty sets, zero, infinity, singularities).
- [ ] The conclusion follows necessarily from the premises.

### 2.3 Numerical Correctness (when applicable)
- [ ] Code or numerical method is reproducible.
- [ ] Precision and rounding errors are bounded.
- [ ] Convergence criteria are stated and met.
- [ ] Results are validated against known special cases.

### 2.4 Millennium Problem Specific Rules
For any of the 6 Millennium Prize Problems:

- [ ] **No claim of solution** without peer-reviewed publication and Clay Institute acceptance (≥2 years after publication).
- [ ] Numerical verification (e.g., zeros of zeta up to T) is **evidence, not proof**.
- [ ] Conditional results (assuming RH) must state the assumption explicitly.
- [ ] Reductions between problems must be explicit and polynomial-time (if complexity-related).

---

## 3. Correction Workflow

When a solution is **incorrect or incomplete**, the agent follows this workflow:

### Step 1: Classify the Issue
| Classification | Meaning | Action |
|----------------|---------|--------|
| **Minor gap** | Missing justification for a step | Add citation or short derivation |
| **Major gap** | Logical leap that invalidates the proof | Rewrite the affected section |
| **Incorrect statement** | Theorem or formula is wrong | Correct the statement and re-prove |
| **Unverified** | Claim lacks evidence or proof | Mark as conjecture; request proof |
| **Outside scope** | Claims to solve an open problem | Reject; redirect to defensive/educational framing |

### Step 2: Generate Correction
The agent produces a corrected version with:
- The original flawed statement.
- The exact gap identified.
- The corrected statement or proof.
- Justification for the correction.

### Step 3: Handoff
The corrected solution returns to the **Professor** (for didactic restructuring) and **QA** (for re-validation) before commit.

---

## 4. Problem-Specific Evaluation Checklists

### 4.1 Riemann Hypothesis
- [ ] Does the proof address **all** non-trivial zeros, not just a finite set?
- [ ] Is the critical line Re(s) = 1/2 used correctly?
- [ ] Is the functional equation of ζ(s) applied properly?
- [ ] Does the proof avoid circular reasoning (assuming what it tries to prove)?
- [ ] Are numerical results labeled as evidence, not proof?

### 4.2 P vs NP
- [ ] Is the reduction polynomial-time?
- [ ] Is the target problem known to be NP-complete?
- [ ] Does the proof respect the natural proofs, relativization, and algebrization barriers?
- [ ] Is the algorithm claimed to be polynomial actually polynomial in input size?

### 4.3 Navier–Stokes
- [ ] Is the incompressibility condition ∇·u = 0 enforced?
- [ ] Is the viscosity term νΔu handled correctly?
- [ ] Are boundary and initial conditions stated?
- [ ] Is the distinction between weak and strong solutions clear?
- [ ] Is blow-up distinguished from loss of regularity?

### 4.4 Yang–Mills Mass Gap
- [ ] Is the gauge group specified (e.g., SU(3))?
- [ ] Is the mass gap Δ > 0 stated as a constant independent of volume?
- [ ] Is the path integral or axiomatic framework specified?
- [ ] Is asymptotic freedom addressed (if relevant)?

### 4.5 Hodge Conjecture
- [ ] Is the variety complex projective and smooth?
- [ ] Is the class of type (p,p) and rational?
- [ ] Is the algebraic cycle of codimension p explicitly constructed?
- [ ] Is the integral version (known false) distinguished from the rational version?

### 4.6 Birch–Swinnerton-Dyer
- [ ] Is the elliptic curve defined over ℚ?
- [ ] Is the rank r correctly identified?
- [ ] Is the order of vanishing of L(E,s) at s=1 computed correctly?
- [ ] Is the Tate–Shafarevich group addressed?

---

## 5. Example Evaluation Report

```
Solution: Proposed proof that RH is true via zero-free region extension
Status: REJECTED — UNVERIFIED
Gap: The proof assumes ζ(s) ≠ 0 for Re(s) > 1/2 − ε without proving it.
      This is equivalent to assuming RH.
Correction needed: Replace the assumption with a derived zero-free region
      or explicitly state the result is conditional on RH.
Verdict: Does not constitute a proof. Return to Professor for reformulation.
```

```
Solution: Algorithm claiming to solve SAT in O(n²)
Status: REJECTED — INCORRECT
Gap: The algorithm uses exponential backtracking in the worst case.
      The claimed O(n²) bound does not hold for unsatisfiable formulas.
Correction needed: Restate as a heuristic, or provide a worst-case
      polynomial-time bound with proof.
Verdict: Not a proof of P = NP.
```

---

## 6. Integration with the 4-Agent Loop

| Agent | Role | Handoff to Evaluator |
|-------|------|---------------------|
| **Pesquisador** | Raises problem, provides context | Submits literature review for evaluation |
| **Professor** | Structures didactic explanation | Submits proof/explanation for evaluation |
| **Aluno** | Derives from zero, numeric tests | Submits derivation for evaluation |
| **QA** | Rebuttal, counterexamples | Submits rebuttal report for cross-validation |
| **Evaluator (this agent)** | Final validation and correction | Returns corrected solution to Professor/QA |

The Evaluator is the **last gate** before a skill is committed to the repository.

---

## 7. Safety & Scope

- Purely educational and defensive.
- Does **not** break cryptography, construct weapons, or create physical devices.
- Does **not** claim any Millennium Prize Problem is solved.
- Corrections are mathematical clarifications, not offensive exploits.

---

## 8. How to Use

1. Receive a candidate solution (text, LaTeX, code, or pseudocode).
2. Run through the checklists in Section 2 and Section 4.
3. If correct → mark **APPROVED** and allow commit.
4. If incorrect/incomplete → mark **REJECTED** with gap description and proposed correction.
5. Return to the 4-agent loop for refinement.
6. Commit with conventional commit:
   ```
   fix(eval): correct gap in <problem-name> solution
   ```
   or
   ```
   feat(eval): add evaluation report for <problem-name>
   ```

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
