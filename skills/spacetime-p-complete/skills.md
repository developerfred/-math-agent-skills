# Spacetime P-Complete Skill

**id:** spacetime-p-complete  
**name:** ST-DECIDE is P-Complete  
**description:** Derived from spacetime-simulation-complexity. Investigate whether the spacetime decision problem (does a spacetime develop CTCs or singularities by time T?) is P-complete. If P-complete, parallel simulation of general relativity is inherently inefficient unless P = NC. Purely theoretical and educational — computational complexity and numerical relativity.  
**author:** codingsh <codingsh@pm.me>  
**status:** open  
**derived_from:** skills/spacetime-simulation-complexity/skills.md  
**triggers:** "P-complete", "spacetime", "ST-DECIDE", "CTC", "singularity", "Einstein equations", "numerical relativity", "parallel complexity", "derived"

---

## 1. Enunciado (Professor)

**Problema de decisão ST-DECIDE:**
```
Entrada: dados iniciais no espaço-tempo (dados de Cauchy discretizados), tempo T, limiar de curvatura C.
Pergunta: A solução das equações de Einstein desenvolve singularidade ou CTC em t ≤ T?
```

**Questão central:** ST-DECIDE é P-completo?

Se ST-DECIDE for P-completo, então a menos que P = NC, não existe algoritmo paralelo polilogarítmico para decidir se um espaço-tempo desenvolve singularidade — implicando limite fundamental à paralelização da relatividade numérica.

---

## 2. Contexto (Pesquisador)

### Classes de complexidade
- **P**: tempo polinomial sequencial.
- **NC**: tempo polilogarítmico paralelo com processadores polinomiais.
- **P-completo**: problemas em P aos quais todo problema de P se reduz por reduções logarítmicas. Se um P-completo está em NC, então P = NC.

### Problemas P-completos conhecidos
- Circuit Value Problem (CVP).
- Programação linear (certas formulações).
- Busca em profundidade (DFS) em grafo.

### Status de ST-DECIDE
Não se conhece redução de CVP para ST-DECIDE. Não se sabe se está em NC nem se é P-completo.

### Referências sugeridas
- Greenlaw et al., "Limits to Parallel Computation: P-completeness Theory".
- Aaronson & Watrous (2009) — computation with CTCs.
- Numerical relativity literature (ADM, 3+1 evolution).
- arXiv: complexity of PDE simulation, P-completeness of PDEs.

---

## 3. Explicação didática (Professor)

### Por que ST-DECIDE parece sequencial
A equação de Einstein em decomposição 3+1 evolui fatias espaciais Σₜ no tempo. Cada fatia depende da anterior. Isso cria uma cadeia causal de comprimento proporcional ao número de passos de tempo — análoga à avaliação sequencial de um circuito booleano.

### Estrutura de uma possível prova de P-completude
1. Mostrar que ST-DECIDE ∈ P (simulação sequencial polinomial).
2. Construir redução logarítmica de CVP para ST-DECIDE: codificar portas booleanas em campos de gravitação de modo que a evolução de Einstein simule a avaliação do circuito.
3. Concluir: ST-DECIDE é P-completo.

---

## 4. Derivação e testes (Aluno)

### Pseudocódigo de decisão (ilustrativo)
```
def ST_DECIDE(dados_iniciais, T, C):
    campo = dados_iniciais
    for t in range(0, T, dt):   # sequencial no tempo
        campo = passo_einstein(campo, dt)
        if detectar_ctc_ou_singularidade(campo, C):
            return TRUE
    return FALSE
```

### Lacuna do aluno
Não se sabe como codificar arbitrariamente portas booleanas em campos de espaço-tempo contínuo preservando as equações de Einstein. Grande obstáculo técnico para qualquer prova de P-completude.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| ST-DECIDE ∈ P | APROVADO (discretização fixa) | Simulação numérica é polinomial. |
| ST-DECIDE é P-completo | EM ABERTO | Não há redução conhecida de CVP. |
| P = NC implicaria paralelos eficientes para gravidade | APROVADO (teórico) | Mas P = NC é aberto. |
| Métodos paralelos existentes provam NC | REJEITADO | Aceleram passos, não removem sequência temporal. |
| Prova de P-completude seria fácil | REJEITADO | Requer codificar computação booleana em espaço-tempo contínuo. |

**Parecer QA:** O problema é aberto. Qualquer redução de CVP para equações de Einstein seria um resultado de destaque em complexidade computacional.

---

## 6. Registro de agentes

- **Pesquisador**: Definições de P, NC, P-completo; CVP; literatura de relatividade numérica e complexidade de PDEs.
- **Professor**: Enunciado de ST-DECIDE, analogia circuito–espaço-tempo, estrutura de prova.
- **Aluno**: Pseudocódigo de decisão, identificação do loop temporal como gargalo.
- **QA**: Contesta claims excessivos, valida escopo das classes de complexidade.

---

## 7. Quatro problemas derivados

1. `st-decide-cvp-reduction` — Tentativa de redução de Circuit Value Problem para ST-DECIDE.
2. `st-decide-einstein-pressure` — Complexidade paralela da etapa de projeção de pressão/restrição de Hamilton.
3. `st-decide-substepping` — Subcycling/refinamento temporal paralelo em relatividade numérica.
4. `st-decide-pde-survey` — Levantamento de problemas de EDPs conhecidos como P-completos.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
