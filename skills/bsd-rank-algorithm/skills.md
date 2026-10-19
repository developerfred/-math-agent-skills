# BSD — Rank Algorithm Skill

**id:** bsd-rank-algorithm  
**name:** General Algorithm for Elliptic Curve Rank Computation  
**description:** Derived from bsd-elliptic-curve-rank. Investigate whether there is a general algorithm to compute the rank of any elliptic curve over Q. Related to BSD and the Birch–Swinnerton-Dyer conjecture. Purely theoretical — computational number theory.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (no known general algorithm)  
**derived_from:** skills/bsd-elliptic-curve-rank/skills.md  
**triggers:** "BSD", "rank algorithm", "elliptic curve", "descent", "compute rank", "general algorithm", "derived"

---

## 1. Enunciado (Professor)

Investigar se existe um algoritmo geral para calcular o posto de qualquer curva elíptica sobre ℚ. Métodos conhecidos (descent, pontos de Heegner) funcionam para casos específicos, mas não há algoritmo geral provado para posto ≥ 2.

---

## 2. Contexto (Pesquisador)

Métodos de descent (2-descent, n-descent) dão limite superior para o posto. Pontos de Heegner dão limite inferior. Para posto geral, não se conhece algoritmo que sempre termine com a resposta correta.

Referências: Cremona (tables), descent methods, Heegner points, BSD implications.

---

## 3. Explicação didática (Professor)

O posto r mede o número de geradores independentes de ordem infinita em E(ℚ). Calcular r é fundamental para BSD. Métodos atuais são parcial: descent prova que r ≤某 valor, Heegner prova que r ≥某 valor. Se coincidem, r é conhecido.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def calcular_posto_geral(E):
    limite_superior = descent(E)
    limite_inferior = pontos_heegner(E)
    if limite_superior == limite_inferior:
        return limite_superior
    else:
        return "desconhecido"
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Algoritmo geral conhecido | REJEITADO (não existe) |
| Descent + Heegner cobrem posto 0/1 | APROVADO |
| Posto ≥ 2 é o problema | APROVADO |

---

## 6. Registro de agentes

- Pesquisador: Métodos de descent, tabelas de Cremona, Heegner points.
- Professor: Posto, limites superior/inferior, algoritmo geral.
- Aluno: Pseudocódigo de cálculo de posto, exemplo.
- QA: Contesta que não há algoritmo geral.

---

## 7. Quatro problemas derivados (terceira geração)

1. `rank-algorithm-improved-descent` — Melhorar métodos de descent para limite superior mais apertado.
2. `rank-algorithm-heegner-general` — Generalizar pontos de Heegner para mais curvas.
3. `rank-algorithm-p-adic` — Usar métodos p-ádicos para cálculo de posto.
4. `rank-algorithm-complexity` — Complexidade computacional do cálculo de posto.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills