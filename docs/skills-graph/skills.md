# GitHub Pages Learning Site Skill

**id:** skills-graph  
**name:** Dynamic Learning Site (GitHub Pages + Three.js)  
**description:** Interactive 3D learning page served by GitHub Pages. Visualizes graph theory networks, parametric surfaces, GPU memory hierarchy (Roofline/AMAT/Little's Law), and parallel DAGs (work/span). Connected to the math agent skills repository.  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**triggers:** "github pages", "threejs", "visualization", "dynamic learning", "graphs", "gpu", "memory", "dag", "parallelism", "interactive"

---

## Purpose

This skill documents the **dynamic learning page** hosted at:

```
https://developerfred.github.io/-math-agent-skills/
```

It serves as a companion to the static `skills/` markdown files, providing interactive Three.js visualizations so agents (and humans) can explore mathematical concepts spatially instead of only textually.

## Views available

| View | File | Three.js content |
|------|------|------------------|
| Overview | `docs/index.html` #view-home | Stats, multi-agent loop description |
| Graph Theory | `docs/index.html` #view-graphs | Weighted 3D network of math concepts (nodes/edges, physics layout) |
| Surfaces | `docs/index.html` #view-surface | Parametric surfaces: sin(x)·cos(y), torus, Möbius strip, saddle |
| GPU & Memory | `docs/index.html` #view-gpu | Memory hierarchy (Registers → L1 → L2 → L3 → DRAM), Little's Law N = λ·R |
| Parallelism | `docs/index.html` #view-parallel | Work/span DAG, T₁, T∞, parallelism ratio |
| Multi-Agent | `docs/index.html` #view-agents | Rebuttal loop roles and commit flow |

## Three.js visualizations included

1. **Graph network** — 40 concept nodes (P vs NP, Riemann, Collatz, GPU, Memory, Roofline, etc.) with weighted edges; OrbitControls for inspection; optional physics layout toggle.
2. **Parametric surfaces** — sin(x)·cos(y), saddle z=x²−y², torus, Möbius strip with HSL color mapping by height.
3. **GPU memory hierarchy** — Orthographic stack of Registers/L1/L2/L3/DRAM with latency labels; interactive request-rate slider updates Little's Law outstanding requests N.
4. **Parallel DAG** — 6-layer task DAG with work T₁, span T∞, and parallelism ratio; regenerate on demand.

## How to enable GitHub Pages

1. In the GitHub repository `developerfred/-math-agent-skills`, go to **Settings → Pages**.
2. Set **Build and deployment → Source** to **Deploy from a branch**.
3. Select branch `main` and folder `/docs`.
4. Save. The site will be available at `https://developerfred.github.io/-math-agent-skills/`.

## Conventional commit for changes to the site

```
feat(docs): add threejs dynamic learning page with graph, surface, gpu, parallel views
```

## Safety

Visualization only. No offensive cryptanalysis, no exploit development, no proprietary GPU firmware reverse engineering.

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
