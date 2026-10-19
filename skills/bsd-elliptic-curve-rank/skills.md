# Birch–Swinnerton-Dyer — Elliptic Curve Rank Skill

**id:** bsd-elliptic-curve-rank  
**name:** Rank Computation for Elliptic Curves  
**description:** Derived from Birch–Swinnerton-Dyer. Compute the rank of rational points on specific elliptic curves and verify BSD numerically for rank 0 and rank 1 cases. Purely theoretical and educational.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (rank ≥ 2 generally open)  
**derived_from:** skills/birch-swinnerton-dyer/skills.md  
**triggers:** "BSD", "elliptic curve", "rank", "rational points", "L-function", "Heegner point", "descent", "congruent number"

---

## 1. Enunciado (Professor)

**Problema:** Para uma curva elíptica E: y² = x³ + ax + b sobre ℚ, calcular o posto r do grupo E(ℚ) e verificar que a ordem de anulação de L(E, s) em s = 1 é igual a r (conjectura de BSD).

**Métodos:**
- **Descent:** Limite superior para o posto.
- **Pontos de Heegner:** Construir pontos de ordem infinita (baixo limite para o posto).
- **Função L:** Calcular ordem de anulação numericamente.

---

## 2. Contexto (Pesquisador)

### Resultados conhecidos
- **Coates–Wiles (1977):** Se L(E, 1) ≠ 0, então posto = 0.
- **Gross–Zagier (1986) + Kolyvagin (1990):** Se L(E, s) tem zero simples em s = 1, então posto = 1 e X(E) é finito.
- **Casos conhecidos:** Posto 0 e 1 são bem entendidos. Posto ≥ 2 é aberto.

### Referências
- Birch & Swinnerton-Dyer (1960s).
- Coates & Wiles (1977).
- Gross & Zagier (1986).
- arXiv: computação de posto de curvas elípticas.

---

## 3. Explicação didática (Professor)

### Grupo de pontos racionais
Por Mordell–Weil:
```
E(ℚ) ≅ ℤ^r ⊕ E(ℚ)_tors
```
Onde r é o posto (número de geradores independentes de ordem infinita).

### Função L da curva
```
L(E, s) = ∏_p (1 − a_p p^{−s} + p^{1−2s})^{−1}
```

### BSD
```
ord_{s=1} L(E, s) = rank(E(ℚ))
```

---

## 4. Derivação e testes (Aluno)

### Exemplo: curva congruente n = 5
Curva: y² = x³ − 25x. Tem ponto (−4, 6) de ordem infinita → posto ≥ 1. L(E, s) tem zero simples em s = 1 → posto = 1. BSD verificado.

### Pseudocódigo (ilustrativo)
```
def verifica_bsd_curva(E):
    r = calcular_posto(E)  # descent ou Heegner
    k = ordem_anulacao_L(E, s=1)
    return r == k
```

### Lacuna
Para posto ≥ 2, não se conhece algoritmo geral confiável nem prova de BSD.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Coates–Wiles posto 0 | APROVADO | Resultado clássico. |
| Gross–Zagier–Kolyvagin posto 1 | APROVADO | Resultado profundo. |
| Posto ≥ 2 | EM ABERTO | Amplamente aberto. |
| Verificação numérica prova BSD? | REJEITADO | Evidência para curvas específicas, não prova geral. |

**Parecer QA:** Posto 0 e 1 estão bem entendidos; posto ≥ 2 é o desafio.

---

## 6. Registro de agentes

- **Pesquisador**: Coates–Wiles, Gross–Zagier, Kolyvagin, referências.
- **Professor**: Mordell–Weil, posto, função L, fórmula de BSD.
- **Aluno**: Curva n = 5, pseudocódigo, identificação da lacuna posto ≥ 2.
- **QA**: Contesta que casos específicos não provam geral.

---

## 7. Quatro problemas derivados

1. `bsd-l-function-vanishing` — Ordem de anulação de L(E, s) para famílias de curvas.
2. `bsd-tate-shafarevich-group` — Finitude e tamanho do grupo X(E).
3. `bsd-congruent-number-problem` — Conexão com números congruentes.
4. `bsd-rank-algorithm` — Algoritmo para computar posto em geral.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
