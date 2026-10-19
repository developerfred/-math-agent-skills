# Riemann Deviation from GUE Skill

**id:** riemann-deviation-GUE  
**name:** Statistical Deviations from GUE Prediction  
**description:** Derived from riemann-critical-line-zeros-advanced. Quantify statistical deviations of zeta zero statistics from the GUE random matrix prediction. Purely theoretical — numerical statistics.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (statistical analysis)  
**derived_from:** skills/riemann-critical-line-zeros-advanced/skills.md  
**triggers:** "GUE deviation", "statistical deviation", "random matrix", "zeta zeros", "pair correlation", "Riemann derived"

---

## 1. Enunciado (Professor)

Quantificar desvios estatísticos das estatísticas dos zeros de ζ(s) em relação à previsão da Unitary Ensemble (GUE) de matrizes aleatórios. Se houver desvios sistemáticos em alturas muito grandes, isso poderia indicar estrutura não-capturada pelo GUE.

---

## 2. Contexto (Pesquisador)

Montgomery–Odlyzko law prevê correlação de pares igual ao GUE. Deviations em alturas muito grandes ou em estatísticas de ordem superior podem revelar nova estrutura.

Referências: Montgomery (1973), Odlyzko (1987), Katz–Sarnak (1999).

---

## 3. Explicação didática (Professor)

Estatísticas de ordem superior: correlação de 3 zeros, 4 zeros, etc. O GUE prediz funções de correlação específicas. Desvios sistemáticos dessas previsões são interessantes.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def medir_desvio_GUE(zeros, ordem=2):
    correlacao_observada = calcular_correlacao(zeros, ordem)
    correlacao_GUE = correlacao_teorica_GUE(ordem)
    return diferenca(correlacao_observada, correlacao_GUE)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Correlação de pares ≈ GUE | APROVADO (evidência numérica) |
| Estatísticas de ordem superior | EM ABERTO (menos testadas) |
| Desvio implica RH falso? | REJEITADO (não necessariamente) |

---

## 6. Registro de agentes

- Pesquisador: Katz–Sarnak, correlações de ordem superior, estatística de zeros.
- Professor: Funções de correlação, GUE, desvios estatísticos.
- Aluno: Pseudocódigo de medição de desvio, exemplo numérico.
- QA: Contesta que desvio não invalida RH.

---

## 7. Quatro problemas derivados (terceira geração)

1. `deviation-GUE-higher-correlations` — Correlações de 3, 4, … zeros.
2. `deviation-GUE-low-height` — Desvios em alturas baixas (zeros iniciais).
3. `deviation-GUE-other-L-functions` — Comparar com zeros de outras funções L.
4. `deviation-GUE-theoretical` — Modelo teórico para desvios (se existirem).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills