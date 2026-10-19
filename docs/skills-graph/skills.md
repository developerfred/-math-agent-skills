# GitHub Pages Learning Site Skill

**id:** skills-graph  
**name:** Dynamic Learning Site (GitHub Pages + Three.js)  
**description:** Interactive 3D learning page served by GitHub Pages. Visualizes graph theory networks, parametric surfaces, GPU memory hierarchy (Roofline/AMAT/Little's Law), parallel DAGs (work/span), Navier–Stokes vortex fields, Euler vorticity, BKM blow-up, P vs NC complexity, CTC light cones, quantum teleportation Bloch sphere, chronology protection vacuum polarization, and spacetime 3+1 foliation. Connected to the math agent skills repository.  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**triggers:** "github pages", "threejs", "visualization", "dynamic learning", "graphs", "gpu", "memory", "dag", "parallelism", "interactive", "ctc", "teleportation", "spacetime"

---

## Purpose

This skill documents the **dynamic learning page** hosted at:

```
https://developerfred.github.io/-math-agent-skills/
```

It serves as a companion to the static `skills/` markdown files, providing interactive Three.js visualizations so agents (and humans) can explore mathematical concepts spatially instead of only textually.

## Views available (14)

| View | Three.js content |
|------|------------------|
| Home | Stats, 4-agent loop description, skill families |
| Execution Matrix | Table of 15 problems × 4 agents with verdicts |
| Graph Theory | Weighted 3D network of math concepts |
| Surfaces | Parametric: sin(x)·cos(y), torus, Möbius strip, saddle |
| GPU & Memory | Memory hierarchy stack, Little's Law N = λ·R slider |
| Parallelism | Work/span DAG, T₁, T∞, parallelism ratio |
| Navier–Stokes | 3D vortex field, viscosity/turbulence controls |
| Euler Regularity | Vorticity magnitude field, ||ω||∞ tracker |
| BKM Criterion | Blow-up growth rate (T*−t)^−α |
| P vs NC × Fluids | Complexity space visualization |
| Closed Timelike Curves | Gödel ring, CTC light cone |
| Quantum Teleportation | Bloch sphere qubit state |
| Chronology Protection | Cauchy horizon, vacuum polarization |
| Spacetime Complexity | 3+1 ADM foliation, time slices |

## Three.js visualizations included

1. **Graph network** — 44 concept nodes with weighted edges; OrbitControls; optional physics layout.
2. **Parametric surfaces** — sin(x)·cos(y), saddle z=x²−y², torus, Möbius strip with HSL color mapping.
3. **GPU memory hierarchy** — Orthographic stack of Registers/L1/L2/L3/DRAM with latency labels; Little's Law slider.
4. **Parallel DAG** — 6-layer task DAG with work T₁, span T∞, parallelism ratio; regenerate on demand.
5. **Navier–Stokes** — 3D particle vortex field.
6. **Euler Regularity** — Vorticity magnitude point cloud.
7. **BKM Criterion** — Blow-up growth rate visualization.
8. **P vs NC** — Complexity space point cloud.
9. **Closed Timelike Curves** — Gödel torus ring with light cone.
10. **Quantum Teleportation** — Bloch sphere with state vector arrow.
11. **Chronology Protection** — Cauchy horizon torus with vacuum polarization field.
12. **Spacetime Complexity** — 3+1 ADM time-slice foliation.

## How to enable GitHub Pages

1. In the GitHub repository `developerfred/-math-agent-skills`, go to **Settings → Pages**.
2. Set **Build and deployment → Source** to **Deploy from a branch**.
3. Select branch `main` and folder `/docs`.
4. Save. The site will be available at `https://developerfred.github.io/-math-agent-skills/`.

## Conventional commit for changes to the site

```
feat(docs): update threejs dynamic learning page with all 15 skills
```

## Safety

Visualization only. No offensive cryptanalysis, no exploit development, no proprietary GPU firmware reverse engineering, no physical time machine or teleporter construction instructions.

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
