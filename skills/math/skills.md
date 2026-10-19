# Math Agent Skill

**id:** math  
**name:** Pure and Applied Mathematics for Agents  
**description:** Comprehensive mathematics knowledge base for agentic systems. Covers pure mathematics (algebra, calculus, geometry, number theory, logic, probability, statistics) and applied mathematics (optimization, differential equations, linear algebra for ML, numerical methods, discrete math, cryptography fundamentals from a defensive/educational perspective). Designed to be used as reference context for LLM agents solving mathematical problems, proofs, modeling, and scientific computing.  
**author:** codingsh <codingsh@pm.me>  
**license:** MIT  
**version:** 1.0.0  
**language:** English  
**triggers:** "math", "mathematics", "calculus", "algebra", "geometry", "statistics", "probability", "optimization", "differential equation", "linear algebra", "number theory", "proof", "derive", "solve equation", "matrix", "vector", "integral", "derivative", "numerical method", "discrete math", "set theory", "logic", "graph theory", "combinatorics", "fourier", "laplace", "complex analysis", "topology", "real analysis", "abstract algebra"

---

## Purpose

This skill equips an agent with the mathematical foundation needed to:

- Solve equations and systems (linear, nonlinear, differential, integral).
- Construct and verify mathematical proofs.
- Perform statistical analysis and probability modeling.
- Optimize functions and models (constrained/unconstrained).
- Work with vectors, matrices, and linear transformations.
- Apply numerical methods when closed-form solutions are unavailable.
- Model real-world phenomena using differential equations and dynamical systems.
- Understand discrete structures (graphs, combinatorics, set theory, logic).
- Reason about cryptographic primitives from a mathematical/educational standpoint (defensive only).

---

## 1. Pure Mathematics

### 1.1 Algebra
- **Groups, rings, fields:** definitions, axioms, homomorphisms, isomorphisms, ideals, quotient structures.
- **Polynomials:** roots, factorization, Fundamental Theorem of Algebra, Galois theory basics.
- **Linear algebra:** vector spaces, subspaces, basis, dimension, linear maps, matrices, determinants, eigenvalues/eigenvectors, diagonalization, Jordan form, singular value decomposition (SVD), inner product spaces, orthogonality, QR decomposition.
- **Boolean algebra:** laws, simplification, Karnaugh maps, logic gates.

### 1.2 Calculus & Real Analysis
- **Single-variable calculus:** limits, continuity, derivatives (rules: product, quotient, chain), integrals (Riemann, Lebesgue intro), Fundamental Theorem of Calculus, techniques of integration (substitution, parts, partial fractions), improper integrals, series (power, Taylor, Maclaurin, Fourier), convergence tests.
- **Multivariable calculus:** partial derivatives, gradient, divergence, curl, line/surface integrals, Green's/Stokes'/Gauss' theorems, Lagrange multipliers.
- **Real analysis:** sequences and series, metric spaces, completeness, compactness, continuity, differentiability, uniform convergence, measure theory basics.

### 1.3 Complex Analysis
- Complex numbers, polar form, Euler's formula.
- Holomorphic/analytic functions, Cauchy-Riemann equations.
- Contour integration, Cauchy's integral theorem and formula, residue theorem, conformal mapping.

### 1.4 Geometry & Topology
- **Euclidean geometry:** axioms, congruence, similarity, conic sections.
- **Analytic geometry:** lines, planes, quadrics, transformations.
- **Differential geometry:** curves, surfaces, manifolds, curvature, geodesics.
- **Topology:** open/closed sets, homeomorphisms, connectedness, compactness, fundamental group, homology basics.

### 1.5 Number Theory
- Divisibility, primes, Fundamental Theorem of Arithmetic.
- Modular arithmetic, congruences, Chinese Remainder Theorem.
- Diophantine equations, Fermat's Little Theorem, Euler's totient function, quadratic residues.
- Primality testing, factorization (educational context), elliptic curves basics.

### 1.6 Logic & Set Theory
- Propositional and predicate logic, quantifiers, logical equivalence.
- Proof techniques: direct, contradiction, contrapositive, induction, construction, exhaustion.
- Set operations, cardinality, countable vs uncountable sets, axiom of choice, Zermelo-Fraenkel axioms.

---

## 2. Applied Mathematics

### 2.1 Probability & Statistics
- **Probability:** sample spaces, events, axioms, conditional probability, Bayes' theorem, independence, random variables (discrete/continuous), expectation, variance, moment generating functions.
- **Distributions:** Bernoulli, Binomial, Poisson, Normal/Gaussian, Exponential, Chi-square, t-distribution, F-distribution, multivariate normal.
- **Statistics:** descriptive statistics, point estimation, confidence intervals, hypothesis testing (z-test, t-test, ANOVA, chi-square), regression (linear, multiple, logistic), correlation, time series basics.

### 2.2 Optimization
- Unconstrained optimization: gradient descent, Newton's method, convexity, KKT conditions.
- Constrained optimization: Lagrange multipliers, linear programming (simplex, duality), quadratic programming, integer programming.
- Convex optimization: convex sets/functions, duality, interior-point methods.

### 2.3 Differential Equations
- **ODEs:** first-order (separable, linear, exact), second-order linear (homogeneous/non-homogeneous), systems of ODEs, Laplace transforms, series solutions, stability, phase portraits.
- **PDEs:** heat equation, wave equation, Laplace's equation, separation of variables, Fourier series solutions, numerical schemes (finite difference, finite element).

### 2.4 Numerical Methods
- Root finding: bisection, Newton-Raphson, secant, fixed-point iteration.
- Numerical integration: trapezoidal, Simpson's, Gaussian quadrature.
- Linear systems: Gaussian elimination, LU decomposition, iterative methods (Jacobi, Gauss-Seidel, conjugate gradient).
- Interpolation: Lagrange, spline, least squares fitting.
- ODE solvers: Euler, Runge-Kutta, multistep methods.

### 2.5 Discrete Mathematics & Combinatorics
- Counting principles: permutations, combinations, pigeonhole principle, inclusion-exclusion.
- Generating functions, recurrence relations, master theorem.
- Graph theory: vertices/edges, paths, cycles, trees, connectivity, Eulerian/Hamiltonian, graph coloring, planar graphs, network flows (max-flow min-cut), shortest paths (Dijkstra, Bellman-Ford).

### 2.6 Mathematical Modeling
- Dimensional analysis, scaling, perturbation methods.
- Population models (logistic, Lotka-Volterra), epidemic models (SIR/SIS).
- Queueing theory basics, Markov chains, Monte Carlo simulation.

---

## 3. How the Agent Should Use This Skill

When a user query matches any trigger above, the agent should:

1. **Identify the domain:** classify the problem (algebra, calculus, statistics, optimization, etc.).
2. **Select the method:** choose the appropriate theorem, formula, or algorithm.
3. **Show the work:** present step-by-step derivation or computation, not just the final answer.
4. **Validate:** check dimensions, boundary conditions, convergence, or plug the solution back into the original equation.
5. **Code when useful:** offer a Python/NumPy/SciPy/Matlab snippet if numerical computation is appropriate.
6. **Cite assumptions:** explicitly state any assumptions (e.g., "assuming f is continuous on [a,b]").

### Example Interaction Pattern

```
User: Solve y'' + 4y = 0 with y(0)=1, y'(0)=0.
Agent:
1. Recognize: second-order linear homogeneous ODE with constant coefficients.
2. Characteristic equation: r^2 + 4 = 0 => r = ±2i.
3. General solution: y(t) = C1 cos(2t) + C2 sin(2t).
4. Apply ICs: y(0)=1 => C1=1. y'(0)=0 => C2=0.
5. Final: y(t) = cos(2t).
```

---

## 4. Safety & Scope (Defensive/Educational Only)

This skill is strictly for **legitimate mathematical education, scientific computing, and defensive security understanding**.

- Cryptographic content (number theory, elliptic curves, modular arithmetic) is included **only** to explain how algorithms work conceptually (e.g., RSA, Diffie-Hellman, ECDSA) and how to use them correctly for protection.
- This skill must **not** be used to break, weaken, bypass, or attack cryptographic systems, or to facilitate unauthorized access to data.
- If a request involves offensive cryptanalysis or exploit development, the agent must decline and redirect to defensive security best practices.

---

## 5. Reference Knowledge Base

Core references consistent with this skill:

- Stewart, J. – *Calculus*
- Axler, S. – *Linear Algebra Done Right*
- Rudin, W. – *Principles of Mathematical Analysis*
- Ahlfors, L. – *Complex Analysis*
- Munkres, J. – *Topology*
- Hardy, G.H., Wright, E.M. – *An Introduction to the Theory of Numbers*
- Ross, S.M. – *Introduction to Probability and Statistics for Engineers and Scientists*
- Boyd, S., Vandenberghe, L. – *Convex Optimization*
- Cormen, T.H. et al. – *Introduction to Algorithms* (discrete math/graph portions)
- ArXiv papers on numerical methods, optimization, and applied mathematics (as needed for state-of-the-art methods)

---

## 6. Suggested Toolchain for Agents

- Python with NumPy, SciPy, SymPy, Matplotlib, Pandas, Statsmodels.
- MATLAB / Octave or Julia for numerical computing.
- LaTeX for typesetting proofs and formulas.
- Lean / Coq / Isabelle for formal proof verification (advanced).
- Jupyter notebooks for exploratory math.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/math-agent-skills

### Descobertas geradas pelo ciclo multi-agente
- `skills/collatz-stopping-time/skills.md` — heurística de tempo de parada da Conjectura de Collatz (status: aberto/heurístico), gerada pelos agentes pesquisador, professor, aluno e QA.
- `skills/parallel-gpu-memory/skills.md` — matemática de paralelismo, GPU e memória RAM (leis de Amdahl/Gustafson, modelo Roofline, AMAT, Little's Law, GEMM, problemas em aberto como Memory Wall e P vs NC), gerada pelos 4 agentes.
- `skills/skills-graph/skills.md` — dynamic learning site on GitHub Pages with Three.js visualizations (graph networks, parametric surfaces, GPU memory hierarchy, parallel DAGs, multi-agent loop).
- `skills/navier-stokes-millennium/skills.md` — Navier–Stokes Existence and Smoothness (Millennium Prize Problem), ciclo dos 4 agentes com atualização de setembro/2026 (OpenAI proposal não verificada; problema segue aberto oficialmente).
- `skills/euler-equations-regularity/skills.md` — equações de Euler incompressíveis 3D, regularidade e explosão, derivado de Navier–Stokes.
- `skills/blow-up-criteria-bkm/skills.md` — critério de Beale–Kato–Majda para explosão de vorticidade, derivado de Euler/Navier–Stokes.
- `skills/p-vs-nc-fluids-connection/skills.md` — conexão entre P vs NC e resolução paralela de equações de fluidos; gera 4 problemas derivados.
- `skills/p-vs-nc-navier-stokes-parallel/skills.md` — Navier–Stokes decision problem é P-completo ou em NC? (derivado)
- `skills/euler-blowup-parallel-verification/skills.md` — verificar explosão de Euler está em NC? (derivado)
- `skills/bkm-criterion-parallel-complexity/skills.md` — complexidade paralela do integral BKM (derivado)
- `skills/fluid-simulation-space-time/skills.md` — métodos espaço-tempo (Parareal) colocam fluidos em NC? (derivado)
- `skills/time-travel-teleportation-foundation/skills.md` — fundamentos matemáticos para viagem no tempo (CTCs) e teleportação quântica, gerado a partir dos 4 problemas P vs NC × fluidos.
- `skills/closed-timelike-curves/skills.md` — métricas de Gödel, Tipler, wormholes Morris–Thorne, matéria exótica.
- `skills/quantum-teleportation/skills.md` — protocolo Bennett et al. (1993), estados de Bell, não-clonagem, canal clássico.
- `skills/chronology-protection/skills.md` — conjectura de Hawking, polarização do vácuo, desigualdades quânticas.
- `skills/spacetime-simulation-complexity/skills.md` — simular espaço-tempos com CTCs está em NC ou é P-completo? (Aaronson–Watrous).
- `skills/riemann-hypothesis/skills.md` — Hipótese de Riemann (Millennium Prize, aberto desde 1859), ciclo dos 4 agentes com estado-da-arte, testes numéricos de zeros e 4 problemas derivados.
- `skills/riemann-critical-line-zeros/skills.md` — verificação numérica distribuída de zeros na linha crítica até altura T grande; análise de gaps entre zeros consecutivos (derivado de Riemann).
- `skills/riemann-prime-counting-error/skills.md` — limites explícitos para |π(x) − Li(x)| sob RH e sem RH; fórmula explícita de von Mangoldt (derivado de Riemann).
- `skills/riemann-l-functions-generalization/skills.md` — Hipótese de Riemann Generalizada para funções L de Dirichlet; primos em progressões aritméticas (derivado de Riemann).
- `skills/riemann-quantum-chaos-connection/skills.md` — lei de Montgomery–Odlyzko; correlação entre zeros da zeta e matrizes aleatórias GUE; conjectura de Hilbert–Pólya (derivado de Riemann).
- `skills/p-vs-np/skills.md` — P versus NP (Millennium Prize, aberto desde 1971), ciclo dos 4 agentes com teorema de Cook–Levin, barreiras de prova e 4 problemas derivados.
- `skills/yang-mills-mass-gap/skills.md` — Yang–Mills Existence and Mass Gap (Millennium Prize, aberto desde 2000), ciclo dos 4 agentes com lattice QCD, confinamento e 4 problemas derivados.
- `skills/hodge-conjecture/skills.md` — Conjectura de Hodge (Millennium Prize, aberto desde 1950), ciclo dos 4 agentes com teoria de Hodge, ciclos algébricos e 4 problemas derivados.
- `skills/birch-swinnerton-dyer/skills.md` — Conjectura de Birch–Swinnerton-Dyer (Millennium Prize, aberto desde 1960s), ciclo dos 4 agentes com curvas elípticas, função L e 4 problemas derivados.
- `skills/solution-evaluator/skills.md` — Solution Evaluator and Corrector Agent: validates proposed solutions, follows strict evaluation guidelines, and corrects incorrect or incomplete solutions before commit.
- `skills/proof-methods/skills.md` — Mathematical Proof Methods catalog: direct, contrapositive, contradiction, induction, construction, cases, and exhaustion. Used by the Solution Evaluator to validate proof structure.
