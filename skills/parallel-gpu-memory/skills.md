# Parallel, GPU and Memory Mathematics Skill

**id:** parallel-gpu-memory  
**name:** Mathematics of Parallelism, GPU and Memory Hierarchy  
**description:** Mathematical foundations for parallel computing, GPU architectures and memory subsystems. Covers speedup laws (Amdahl, Gustafson), work/span parallelism, Roofline model, arithmetic intensity, AMAT, Little's Law, coalesced access, occupancy, tiling/blocking for cache, sparse matrix operations and GEMM. Educational and performance-modeling scope only.  
**author:** codingsh <codingsh@pm.me>  
**status:** active  
**triggers:** "parallel", "parallelism", "GPU", "CUDA", "OpenCL", "memory", "RAM", "cache", "bandwidth", "roofline", "Amdahl", "Gustafson", "work span", "arithmetic intensity", "occupancy", "coalesced", "tiling", "blocking", "GEMM", "sparse matrix", "SpMV", "Little's law", "AMAT", "speedup", "multicore", "SIMD", "warp", "thread block"

---

## 1. Purpose

This skill equips agents with the mathematical tools to:

- Model and predict parallel speedup and efficiency.
- Analyze GPU kernels using the Roofline model and arithmetic intensity.
- Estimate memory hierarchy performance (AMAT, hit/miss rates, bandwidth).
- Reason about work, span, and parallelism in task graphs.
- Optimize data layout (tiling, blocking, coalesced access) for cache and GPU shared memory.
- Evaluate sparse linear algebra and dense GEMM from a parallel complexity standpoint.

All content is **educational and performance-modeling only**. No cryptographic breaking, no exploit development, no offensive use.

---

## 2. Mathematics of Parallelism

### 2.1 Amdahl's Law

For a program with parallel fraction $P$ and serial fraction $(1-P)$, running on $N$ processors:

$$
S(N) = \frac{1}{(1-P) + \frac{P}{N}}
$$

$$
E(N) = \frac{S(N)}{N} = \frac{1}{N(1-P) + P}
$$

**Limit:** As $N \to \infty$, $S(N) \to \frac{1}{1-P}$. The serial portion bounds maximum speedup.

### 2.2 Gustafson's Law (Scaled Speedup)

For a problem that scales with $N$, where serial work is $s$ and parallel work is $(1-s)N$:

$$
S(N) = N - (N-1)s = s + N(1-s)
$$

Interpretation: With fixed time, larger problems can use more processors efficiently.

### 2.3 Work, Span, and Parallelism (DAG Model)

For a computation represented as a directed acyclic graph:

- **Work** $T_1$: total operations on 1 processor.
- **Span** $T_\infty$: critical path length (time with infinite processors).
- **Parallelism**: $\frac{T_1}{T_\infty}$

**Brent's Theorem (work-span):** The computation can be scheduled on $P$ processors in:

$$
T_P \le \frac{T_1}{P} + T_\infty
$$

Speedup bound: $S(P) \le \min\left(P, \frac{T_1}{T_\infty}\right)$.

### 2.4 Efficiency and Isoefficiency

- **Efficiency**: $E = \frac{S}{P} = \frac{T_1}{P \cdot T_P}$
- **Overhead**: $T_o = P \cdot T_P - T_1$
- **Isoefficiency function**: relates problem size $W$ to processors $P$ to maintain fixed efficiency.

---

## 3. Mathematics of GPU Architectures

### 3.1 Roofline Model

Performance (FLOP/s) is bounded by:

$$
\text{Performance} = \min\left(\text{Peak Compute},\ \text{Memory Bandwidth} \times \text{Arithmetic Intensity}\right)
$$

- **Arithmetic Intensity** $I = \frac{\text{FLOPs}}{\text{Bytes accessed from memory}}$
- **Ridge point**: $I_{\text{ridge}} = \frac{\text{Peak Compute}}{\text{Peak Bandwidth}}$
- Below ridge: memory-bound. Above ridge: compute-bound.

### 3.2 GPU Occupancy

$$
\text{Occupancy} = \frac{\text{Active Warps per SM}}{\text{Maximum Warps per SM}}
$$

Limiting factors: registers per thread, shared memory per block, threads per block, block limit per SM.

### 3.3 Memory Access Patterns

- **Coalesced access**: adjacent threads access adjacent memory addresses $\to$ single memory transaction.
- **Bank conflicts**: in shared memory, multiple threads accessing same bank $\to$ serialized accesses.
- **Memory throughput**: $\text{Throughput} = \frac{\text{Bytes transferred}}{\text{Elapsed cycles}}$

### 3.4 Warp Scheduling

- Warp = 32 threads (NVIDIA) executing in lockstep (SIMT).
- Divergence within a warp serializes the divergent paths.

---

## 4. Mathematics of Memory Hierarchy (RAM / Cache)

### 4.1 Average Memory Access Time (AMAT)

$$
\text{AMAT} = \text{Hit Time} + \text{Miss Rate} \times \text{Miss Penalty}
$$

For multi-level caches:

$$
\text{AMAT} = \text{Hit}_{L1} + \text{MR}_{L1} \times \left(\text{Hit}_{L2} + \text{MR}_{L2} \times \text{Miss Penalty}_{L2}\right)
$$

### 4.2 Little's Law Applied to Memory

$$
N = \lambda \times R
$$

Where:
- $N$ = average number of outstanding memory requests
- $\lambda$ = request arrival rate (reqs/cycle)
- $R$ = average response time (latency, cycles)

Used to estimate memory-level parallelism (MLP) needed to hide latency.

### 4.3 Bandwidth and Latency

- **Peak bandwidth**: $\text{Bytes/cycle} \times \text{Clock frequency}$
- **Effective bandwidth**: $\frac{\text{Useful bytes transferred}}{\text{Elapsed time}}$
- **Latency hiding**: requires enough independent requests in flight ($N$ from Little's Law) to cover $R$.

### 4.4 Cache Blocking / Tiling

For matrix operations (e.g., GEMM $C = A \times B$):

- Tile size chosen so that a tile of $A$, a tile of $B$, and a tile of $C$ fit in cache/shared memory.
- Arithmetic intensity increases from $O(1)$ (naive) to $O(\sqrt{M})$ (blocked), moving toward compute-bound Roofline region.

---

## 5. Open Problems in Parallel / GPU / Memory Mathematics

1. **Memory Wall**: Can arithmetic intensity grow fast enough to outpace the latency gap between CPU/GPU compute and DRAM? (No closed-form bound; architectural co-design problem.)
2. **Optimal tile size**: For arbitrary cache hierarchies and tensor shapes, finding the globally optimal blocking factors is NP-hard in general; heuristics dominate.
3. **Irregular parallelism**: Graph algorithms (BFS, PageRank, SpMV) have load imbalance; theoretical bounds on work-efficient parallel graph traversal remain open for many classes.
4. **GPU register pressure vs occupancy**: Analytical model for optimal register allocation under occupancy constraints is an open optimization problem.
5. **Little's Law tightness for memory MLP**: Bounds on the minimum outstanding requests to saturate modern DDR/HBM channels under non-uniform access patterns.
6. **P vs NC**: Whether every problem efficiently solvable in parallel (NC) equals P — foundational parallel complexity question (related to P vs NP).

---

## 6. Example: GEMM Performance Estimation (Professor + Aluno)

**Problem**: Estimate performance of $C = A \times B$ for $1024 \times 1024$ matrices on a GPU with:
- Peak compute: 10 TFLOP/s
- Memory bandwidth: 500 GB/s
- Naive implementation: arithmetic intensity $I \approx 0.25$ FLOP/Byte

**Solution**:

1. Arithmetic intensity naive: each element of $C$ needs $1024$ mults + $1023$ adds $\approx 2048$ FLOPs; reads $2 \times 1024 \times 4$ bytes $\approx 8$ KB.
2. $I = \frac{2048}{8192} = 0.25$ FLOP/Byte.
3. Roofline: memory-bound performance $= 500 \times 10^9 \times 0.25 = 125$ GFLOP/s.
4. Compute-bound ceiling: 10 TFLOP/s.
5. Result: naive kernel is memory-bound at ~125 GFLOP/s, far below 10 TFLOP/s peak.
6. With tiling (blocking), intensity can rise to $O(\sqrt{M})$, potentially reaching compute-bound region.

**QA review**: Verify units (GFLOP/s vs TFLOP/s), check that bytes count includes both read of A and B and write of C, confirm ridge point $I_{\text{ridge}} = 10/0.5 = 20$ FLOP/Byte.

---

## 7. Agents' Roles in This Domain

| Agent | Responsibility |
|-------|----------------|
| **Pesquisador** | Find arXiv papers on GPU performance modeling, cache-oblivious algorithms, parallel complexity (NC vs P), memory wall studies. |
| **Professor** | Derive Amdahl/Gustafson, Roofline, AMAT step-by-step; create GEMM tiling exercises. |
| **Aluno** | Compute numeric examples (like section 6), test small matrices, identify where formulas break (e.g., nonzero hit time). |
| **QA** | Challenge assumptions: perfect coalescing? no bank conflicts? constant bandwidth? Validate numeric results with code (Python/NumPy/Cupy). |

---

## 8. Safety & Scope

- Purely educational performance modeling.
- Do not use to reverse engineer proprietary GPU firmware, bypass DRM, or break encryption via GPU acceleration.
- Mathematical models here are approximations; real hardware requires empirical validation.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
