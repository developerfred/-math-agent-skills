# Proof Methods Skill

**id:** proof-methods  
**name:** Mathematical Proof Methods  
**description:** Catalog of standard mathematical proof methods used by the Solution Evaluator to validate and correct proposed solutions. Covers direct proof, proof by contrapositive, proof by contradiction, proof by induction, proof by construction, proof by cases, and proof by exhaustion. Aligned with standard discrete mathematics and logic curricula (e.g., UFMG MD - Métodos de Prova).  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**triggers:** "proof method", "direct proof", "contrapositive", "contradiction", "induction", "construction", "cases", "exhaustion", "mathematical proof", "validate proof", "proof structure"

---

## 1. Purpose

This skill documents the **standard proof methods** that the Solution Evaluator uses to check whether a proposed solution is logically valid. Every proof submitted to the repository must follow one (or a combination) of these methods.

---

## 2. Direct Proof (Prova Direta)

**Structure:** To prove $P \Rightarrow Q$, assume $P$ is true and use logical deductions, definitions, and known theorems to arrive at $Q$.

```
Proof:
1. Assume P holds.
2. Apply definition/theorem T1 to derive intermediate result R1.
3. Apply definition/theorem T2 to derive R2 from R1.
...
n. Therefore Q holds. QED.
```

**When to use:** When the implication is straightforward and definitions lead directly to the conclusion.

**Example:** If $n$ is even, then $n^2$ is even.
- Assume $n = 2k$ for some integer $k$.
- Then $n^2 = (2k)^2 = 4k^2 = 2(2k^2)$, which is even.

**Evaluator checklist:**
- [ ] The assumption $P$ is explicitly stated.
- [ ] Each step follows from the previous by a valid rule of inference.
- [ ] The conclusion $Q$ is reached without gaps.

---

## 3. Proof by Contrapositive (Prova pela Contraposição)

**Structure:** To prove $P \Rightarrow Q$, prove the logically equivalent statement $\neg Q \Rightarrow \neg P$.

```
Proof:
1. Assume ¬Q holds.
2. Deduce ¬P from ¬Q using definitions and theorems.
3. Since ¬Q ⇒ ¬P, the original P ⇒ Q holds. QED.
```

**When to use:** When the direct assumption of $P$ does not lead easily to $Q$, but assuming the negation of $Q$ gives a clearer path.

**Example:** If $n^2$ is even, then $n$ is even.
- Prove contrapositive: If $n$ is odd, then $n^2$ is odd.
- Assume $n = 2k + 1$. Then $n^2 = 4k^2 + 4k + 1 = 2(2k^2 + 2k) + 1$, which is odd.

**Evaluator checklist:**
- [ ] The contrapositive $\neg Q \Rightarrow \neg P$ is clearly identified.
- [ ] The logical equivalence $P \Rightarrow Q \equiv \neg Q \Rightarrow \neg P$ is acknowledged.
- [ ] The proof of the contrapositive is valid.

---

## 4. Proof by Contradiction (Prova por Contradição / Redução ao Absurdo)

**Structure:** To prove $P$, assume $\neg P$ and derive a contradiction (e.g., $R \land \neg R$ or a known false statement).

```
Proof:
1. Assume ¬P.
2. Deduce a consequence R.
3. Deduce ¬R (or contradict a known theorem/axiom).
4. Therefore ¬P leads to a contradiction, so P must be true. QED.
```

**When to use:** When direct and contrapositive approaches fail, or when proving non-existence, irrationality, or infinitude (e.g., infinitely many primes).

**Example:** $\sqrt{2}$ is irrational.
- Assume $\sqrt{2} = a/b$ in lowest terms.
- Derive that both $a$ and $b$ are even, contradicting lowest terms.

**Evaluator checklist:**
- [ ] The negation $\neg P$ is explicitly assumed.
- [ ] The contradiction is clearly identified (not just "this seems wrong").
- [ ] The contradiction invalidates the assumption, proving $P$.

---

## 5. Proof by Induction (Prova por Indução Matemática)

**Structure:** To prove a statement $P(n)$ for all integers $n \geq n_0$:

```
Proof:
Base case: Show P(n0) is true.
Inductive hypothesis: Assume P(k) is true for some arbitrary k ≥ n0.
Inductive step: Show P(k+1) follows from P(k).
Conclusion: By induction, P(n) is true for all n ≥ n0. QED.
```

**Strong induction variant:** Assume $P(n_0), P(n_0+1), ..., P(k)$ all hold to prove $P(k+1)$.

**When to use:** Statements about natural numbers, recursive definitions, sequences, sums.

**Example:** Sum of first $n$ integers: $1 + 2 + ... + n = n(n+1)/2$.
- Base: $n=1$, $1 = 1(2)/2 = 1$. ✓
- Inductive step: Assume true for $k$, prove for $k+1$.

**Evaluator checklist:**
- [ ] Base case is verified for the correct starting value.
- [ ] Inductive hypothesis is clearly stated.
- [ ] Inductive step uses the hypothesis correctly to prove $P(k+1)$.
- [ ] No gap between $P(k)$ and $P(k+1)$.

---

## 6. Proof by Construction (Prova por Construção)

**Structure:** To prove an existence statement $\exists x \text{ such that } Q(x)$, explicitly construct an example $x$ and verify that $Q(x)$ holds.

```
Proof:
1. Construct object x explicitly (formula, algorithm, example).
2. Verify that object x satisfies property Q.
3. Therefore such an object exists. QED.
```

**When to use:** Existential theorems, showing a solution exists, exhibiting a counterexample.

**Example:** There exists an even prime number.
- Construct $x = 2$. Verify 2 is prime and even.

**Evaluator checklist:**
- [ ] The constructed object is explicitly defined.
- [ ] Verification that the object satisfies the required property is complete.
- [ ] The object belongs to the correct domain.

---

## 7. Proof by Cases (Prova por Casos)

**Structure:** To prove $P$, partition the domain into exhaustive cases $C_1, C_2, ..., C_m$ and prove $P$ holds in each case.

```
Proof:
Case 1: Assume condition C1. Prove P.
Case 2: Assume condition C2. Prove P.
...
Case m: Assume condition Cm. Prove P.
Since cases are exhaustive, P holds in all cases. QED.
```

**When to use:** When the statement behaves differently depending on input ranges, parity, signs, etc.

**Evaluator checklist:**
- [ ] Cases are mutually exclusive or at least exhaustive.
- [ ] Every possible input is covered by some case.
- [ ] Each case is proven independently.

---

## 8. Proof by Exhaustion (Prova por Exaustão)

**Structure:** A finite version of proof by cases where the domain is small enough to check every possibility individually.

```
Proof:
Check possibility 1: P holds.
Check possibility 2: P holds.
...
Check possibility N: P holds.
Since all N possibilities are checked, P holds universally. QED.
```

**When to use:** Finite domains, small cases, computational verification of bounded ranges.

**Evaluator checklist:**
- [ ] The domain is genuinely finite.
- [ ] Every element of the domain is checked.
- [ ] No possibility is skipped.

---

## 9. How the Solution Evaluator Uses These Methods

When evaluating a proposed solution, the Solution Evaluator:

1. **Identifies the method:** Which proof method(s) does the solution claim to use?
2. **Verifies structure:** Does the solution follow the required structure for that method?
3. **Checks gaps:** Are there missing steps, unjustified leaps, or uncovered cases?
4. **Classifies issues:** Minor gap / Major gap / Incorrect statement / Unverified / Outside scope.
5. **Proposes correction:** If the method is misapplied, the evaluator suggests rewriting using the correct method or fixing the gap.

---

## 10. Example Evaluation Using Proof Methods

```
Solution: Claim: For all integers n, if n² is even then n is even.
Method claimed: Direct proof.
Evaluator analysis:
- Direct proof assumes n² is even and tries to show n is even.
- This is difficult directly because n² being even doesn't immediately reveal n's parity.
- Better method: Proof by contrapositive.
- Correction: Rewrite using contrapositive: assume n is odd, show n² is odd.
Status: REJECTED — Wrong method / Major gap.
Suggested fix: Use proof by contrapositive.
```

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
