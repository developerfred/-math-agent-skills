# Binary Black Hole Simulation in NC Skill

**id:** binary-black-hole-nc  
**name:** Binary Black Hole Simulation in Parallel Class NC  
**description:** Derived from spacetime-simulation-complexity. Investigate whether simulating binary black hole mergers (numerical relativity, 3+1 ADM evolution) can be parallelized efficiently — i.e., whether the problem is in NC (polylogarithmic time with polynomially many processors). Purely theoretical and educational — numerical relativity, no physical device construction.  
**author:** codingsh <codingsh@pm.me>  
**status:** open  
**derived_from:** skills/spacetime-simulation-complexity/skills.md  
**triggers:** "binary black hole", "numerical relativity", "NC", "parallel class", "ADM", "3+1 decomposition", "gravitational waves", "merger", "spacetime simulation derived", "P vs NC"

---

## 1. Enunciado (Professor)

**Problema:** A simulação numérica da fusão de buracos negros binários (evolução das equações de Einstein em decomposição 3+1 ADM) pode ser paralelizada de forma eficiente? Formalmente: o problema de decisão ST-BBH (dados iniciais de buracos negros binários, tempo T, limiar de forma de onda h) está na classe NC?

```
ST-BBH:
Entrada: dados de Cauchy iniciais (métrica g_ij e curvatura extrínseca K_ij) para dois buracos negros, tempo T, limiar C.
Pergunta: A forma de onda gravitacional h(t) excede C em algum t ∈ [0, T]?
```

Se ST-BBH ∈ NC, então com processadores paralelamente ilimitados podemos simular fusões em tempo polilogarítmico. Se for P-completo, a paralelização eficiente é improvável (a menos que P = NC).

---

## 2. Contexto (Pesquisador)

### Relatividade numérica (NumRel)
- Decomposição 3+1 (ADM): divide espaço-tempo em fatias espaciais Σₜ.
- Equações de evolução: ∂ₜg_ij = ... , ∂ₜK_ij = ... (dependem da fatia anterior).
- Cada passo de tempo é sequencial: Σₜ₊₁ depende de Σₜ.
- Simulações de buracos negros binários usam malhas adaptativas, refinamento, subdomínios.

### Classe NC
- NC = problemas solúveis em tempo O(log^k n) com n^O(1) processadores em paralelo.
- NC ⊆ P. Se P = NC, então problemas aparentemente sequenciais podem ser paralelizados eficientemente.
- Não se sabe se P = NC (aberto, relacionado a P vs NP).

### Referências sugeridas
- Baumgarte & Shapiro, "Numerical Relativity".
- Kidder et al., binary black hole evolution.
- Aaronson & Watrous (2009) — CTCs and complexity classes.
- arXiv: numerical relativity parallelization, ADM evolution parallelism.

---

## 3. Explicação didática (Professor)

### Por que é sequencial
A evolução de Einstein em 3+1 é uma equação diferencial parcial hiperbólica. Cada passo de tempo depende do estado anterior (condição de Cauchy). Isso cria uma cadeia de dependências de comprimento T/dt — linear no número de passos.

### O que seria necessário para estar em NC
1. Um método que "pule" no tempo sem perder precisão (ex: Parareal, espaço-tempo unificado).
2. Prova de que o número de iterações é polilogarítmico em T.
3. Cada iteração paralelizável em NC no espaço.

### Analogia com fluidos
É análogo ao problema de simulação de Navier–Stokes em NC: a dependência causal no tempo é o gargalo.

---

## 4. Derivação e testes (Aluno)

### Pseudocódigo de evolução ADM (ilustrativo)
```
def evoluir_adm_3plus1(g_inicial, K_inicial, T, dt):
    g = g_inicial
    K = K_inicial
    for t in range(0, T, dt):          # SEQUENCIAL no tempo
        g, K = passo_adm(g, K, dt)     # depende de g, K anteriores
        h = calcular_forma_onda(g)     # extrair onda gravitacional
        if max(abs(h)) > limiar:
            return True
    return False
```

### Lacuna identificada
O loop temporal é inerentemente sequencial na formulação 3+1. Sem um método de salto temporal com garantia de convergência polilogarítmica, não há prova de pertencimento a NC.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Evolução 3+1 é sequencial | APROVADADO | Cada fatia depende da anterior. |
| ST-BBH ∈ P | APROVADO (discretização fixa) | Evolução numérica é polinomial. |
| ST-BBH ∈ NC | EM ABERTO | Não há algoritmo paralelo polilogarítmico conhecido. |
| ST-BBH é P-completo? | EM ABERTO | Não há redução conhecida. |
| Parareal resolve? | RESSALVA | Acelera empiricamente, não garante complexidade polilogarítmica. |

**Parecer QA:** O problema parece sequencialmente difícil, mas não há prova de P-completude nem algoritmo em NC.

---

## 6. Registro de agentes

- **Pesquisador**: Relatividade numérica, ADM, fusão de buracos negros, literatura de paralelismo em NumRel.
- **Professor**: Decomposição 3+1, cadeia de dependência temporal, estrutura do problema de decisão.
- **Aluno**: Pseudocódigo de evolução, identificação do loop temporal como gargalo.
- **QA**: Contesta claims de paralelização, valida escopo das classes de complexidade.

---

## 7. Quatro problemas derivados

1. `bbh-parareal-convergence` — Convergência do Parareal para equações de Einstein.
2. `bbh-space-time-fem` — Elementos finitos espaço-tempo para relatividade numérica.
3. `bbh-mesh-refinement-parallel` — Paralelismo de malha adaptativa em buracos negros binários.
4. `bbh-p-complete-reduction` — Tentativa de redução de problema P-completo para ST-BBH.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
