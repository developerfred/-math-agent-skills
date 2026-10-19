# Circuit Lower Bounds — Monotone Circuits Skill

**id:** circuit-lower-bounds-monotone  
**name:** Monotone Circuit Lower Bounds for Explicit Functions  
**description:** Derived from circuit-lower-bounds. Investigate exponential lower bounds for monotone circuits (no NOT gates) computing explicit functions like clique and matching. Purely theoretical.  
**author:** codingsh <codingsh@pm.me>  
**status:** open  
**derived_from:** skills/p-vs-np-circuit-lower-bounds/skills.md  
**triggers:** "monotone circuit", "lower bound", "clique", "matching", "Razborov", "exponential", "P vs NP derived"

---

## 1. Enunciado (Professor)

Provar limites inferiores exponenciais para circuitos monotônicos computando funções explícitas como CLIQUE e MATCHING. Circuitos monotônicos usam apenas portas AND e OR (sem NOT).

---

## 2. Contexto (Pesquisador)

Razborov (1985) mostrou limite inferior exponencial para CLIQUE em circuitos monotônicos. Depois, Andreev e outros estenderam para outras funções. Limites para circuitos monotônicos são conhecidos, mas não se estendem para circuitos gerais.

Referências: Razborov (1985), Andreev (1985), Alon & Boppana (1987).

---

## 3. Explicação didática (Professor)

Circuito monotônico: DAG com portas AND e OR apenas. Funções monótonas (se mudar 0 para 1 na entrada, saída não diminui). CLIQUE é monótona: adicionar arestas não remove cliques.

---

## 4. Derivação e testes (Aluno)

Exemplo: função CLIQUE_k(n) = 1 se grafo com n vértices tem clique de tamanho k. Razborov mostrou que qualquer circuito monotônico para CLIQUE_k tem tamanho exp(Ω(n^{1/4})) para k = n^{1/4}.

Pseudocódigo:
```
def limite_monotono_clique(n, k):
    # Retornar limite inferior exp(Omega(n^(1/4)))
    return exp(n**(1/4) / constante)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Limite exponencial monotônio CLIQUE | APROVADO (Razborov 1985) |
| Estende para circuitos gerais | REJEITADO (NOT gates quebram monotonicidade) |
| Implica P ≠ NP | INDIRETO (só para circuitos monotônicos) |

---

## 6. Registro de agentes

- Pesquisador: Razborov, Andreev, limites monotônicos.
- Professor: Circuitos monotônicos, função CLIQUE, limite exponencial.
- Aluno: Exemplo CLIQUE_k, pseudocódigo de limite.
- QA: Contesta extensão para circuitos gerais.

---

## 7. Quatro problemas derivados (terceira geração)

1. `monotone-circuit-matching` — Limite inferior para MATCHING em circuitos monotônicos.
2. `monotone-circuit-flow` — Limite inferior para fluxo máximo em circuitos monotônicos.
3. `monotone-vs-nonmonotone-gap` — Gap exponencial entre monotônico e geral para alguma função.
4. `monotone-formula-size` — Tamanho de fórmulas monotônicas (não apenas circuitos).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills