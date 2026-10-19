# Riemann Zero Gap Statistics Skill

**id:** riemann-zero-gap-statistics  
**name:** Zero Gap Statistics at Large Heights  
**description:** Derived from riemann-critical-line-zeros-advanced. Analyze the statistical distribution of gaps between consecutive zeta zeros at very large heights (T > 10^20) and compare with GUE random matrix prediction. Purely theoretical — numerical analysis.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (numerical statistics)  
**derived_from:** skills/riemann-critical-line-zeros-advanced/skills.md  
**triggers:** "zero gaps", "statistics", "GUE", "random matrix", "large height", "zeta zeros", "Riemann derived"

---

## 1. Enunciado (Professor)

Analisar a distribuição estatística dos gaps entre zeros consecutivos de ζ(s) em alturas muito grandes (T > 10^20) e comparar com a previsão da Unitary Ensemble (GUE) de matrizes aleatórias.

---

## 2. Contexto (Pesquisador)

Montgomery (1973) conjecturou correlação de pares dos zeros igual ao GUE. Odlyzko (1987) verificou numericamente até T ~ 10^20. Objetivo: ir além, verificar em alturas maiores com mais zeros.

Referências: Montgomery (1973), Odlyzko (1987), Keating–Snaith (2000).

---

## 3. Explicação didática (Professor)

Gap normalizado: δ_n = (γ_{n+1} − γ_n) · log(γ_n) / (2π). Se zeros se comportam como eigenvalores de matrizes GUE, a distribuição de δ_n segue a surmise de Wigner: P(s) = (32/π²)s²exp(−4s²/π).

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def analisar_gaps_zeros(zeros, T_min, T_max):
    gaps = []
    para cada par consecutivo (γ_n, γ_{n+1}) em [T_min, T_max]:
        gap_norm = (γ_{n+1} - γ_n) * log(γ_n) / (2*pi)
        gaps.append(gap_norm)
    return comparar_histograma(gaps, wigner_surmise_GUE)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Correlação de pares ≈ GUE | APROVADO (Odlyzko até 10^20) |
| Alturas > 10^20 | EM ABERTO (computacionalmente caro) |
| Prova de RH via estatística | REJEITADO (evidência não é prova) |

---

## 6. Registro de agentes

- Pesquisador: Montgomery, Odlyzko, estatística de zeros.
- Professor: Gap normalizado, surmise de Wigner, GUE.
- Aluno: Pseudocódigo de análise de gaps, comparação de histogramas.
- QA: Contesta que estatística não prova RH.

---

## 7. Quatro problemas derivados (terceira geração)

1. `zero-gap-statistics-higher-moments` — Momentos mais altos da distribuição de gaps.
2. `zero-gap-statistics-spacings` — Distribuição de espaçamentos (não apenas gaps consecutivos).
3. `zero-gap-statistics-low-height` — Estatística em alturas baixas (zeros iniciais).
4. `zero-gap-statistics-comparison-L-functions` — Comparar com zeros de outras funções L.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills