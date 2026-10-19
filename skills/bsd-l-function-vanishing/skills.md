# BSD — L-Function Vanishing Order Skill

**id:** bsd-l-function-vanishing  
**name:** Order of Vanishing of Elliptic Curve L-Functions at s=1  
**description:** Derived from bsd-elliptic-curve-rank. Study the order of vanishing of L(E, s) at s = 1 for families of elliptic curves and verify BSD numerically. Purely theoretical — computational number theory.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (families and higher ranks)  
**derived_from:** skills/bsd-elliptic-curve-rank/skills.md  
**triggers:** "BSD", "L-function", "vanishing order", "s=1", "elliptic curve families", "derived"

---

## 1. Enunciado (Professor)

Estudar a ordem de anulação de L(E, s) em s = 1 para famílias de curvas elípticas e verificar numericamente a conjectura de BSD: ord_{s=1} L(E, s) = rank(E(ℚ)).

---

## 2. Contexto (Pesquisador)

Para curvas de posto 0: L(E, 1) ≠ 0 (ordem 0). Para posto 1: L(E, s) tem zero simples (ordem 1). Para posto ≥ 2: ordem ≥ 2, mas não se conhece prova geral.

Referências: Coates–Wiles, Gross–Zagier, Kolyvagin, computações numéricas de L(E, s).

---

## 3. Explicação didática (Professor)

A ordem de anulação mede quão rápido L(E, s) se aproxima de zero em s = 1. BSD diz que isso é exatamente o posto do grupo de pontos racionais.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def ordem_anulacao_L(E, s0=1, precisao=100):
    # Expandir L(E, s) em série de Taylor em s0
    # Retornar o primeiro k tal que coeficiente de (s-s0)^k é não-nulo
    return k
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Ordem 0 ↔ posto 0 | APROVADO (Coates–Wiles) |
| Ordem 1 ↔ posto 1 | APROVADO (Gross–Zagier–Kolyvagin) |
| Ordem ≥ 2 ↔ posto ≥ 2 | EM ABERTO |

---

## 6. Registro de agentes

- Pesquisador: Ordens de anulação, computações numéricas de L(E, s).
- Professor: Função L de curva elíptica, expansão de Taylor, BSD.
- Aluno: Pseudocódigo de ordem de anulação, exemplos numéricos.
- QA: Contesta que evidência numérica não prova para posto ≥ 2.

---

## 7. Quatro problemas derivados (terceira geração)

1. `l-function-vanishing-families` — Famílias paramétricas de curvas elípticas.
2. `l-function-vanishing-rank-2` — Casos específicos de posto 2.
3. `l-function-vanishing-derivatives` — Derivadas de L(E, s) em s = 1.
4. `l-function-vanishing-numerical` — Verificação numérica de grande escala.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills