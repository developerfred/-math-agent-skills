# Riemann Interval Arithmetic Skill

**id:** riemann-interval-arithmetic  
**name:** Interval Arithmetic for Zeta Function Bounds  
**description:** Derived from riemann-critical-line-zeros-advanced. Develop rigorous interval arithmetic bounds for ζ(s) and its derivative to support zero-free region proofs and Turing certification. Purely theoretical — numerical analysis.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (numerical bounds)  
**derived_from:** skills/riemann-critical-line-zeros-advanced/skills.md  
**triggers:** "interval arithmetic", "zeta bounds", "rigorous numerics", "zero-free region", "Riemann-Siegel", "derived"

---

## 1. Enunciado (Professor)

Desenvolver bounds rigorosos de aritmética de intervalos para ζ(s) e ζ'(s) para suportar provas de regiões livres de zeros e certificação via método de Turing.

---

## 2. Contexto (Pesquisador)

Aritmética de intervalos representa números como intervalos [a, b] e propaga erros. Para ζ(s), pode-se calcular bounds rigorosos para |ζ(s)| em regiões do plano complexo, garantindo que não há zeros onde o bound é não-zero.

Referências: Tucker (validated numerics), interval arithmetic libraries, Riemann-Siegel formula with error bounds.

---

## 3. Explicação didática (Professor)

Se pudemos mostrar que |ζ(s)| ≥ ε > 0 em uma região R (fora da linha crítica), então não há zeros em R. Aritmética de intervalos fornece esse ε rigoroso, considerando erros de arredondamento e truncamento.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def bound_zeta_interval(s_intervalo):
    # Calcular bounds [inf, sup] para zeta(s) para todo s no intervalo
    # Usar fórmula de Riemann-Siegel com bounds de erro
    return bound_inferior, bound_superior

def certificar_sem_zeros(regiao):
    para cada subregião em região:
        inf, sup = bound_zeta_interval(subregião)
        if inf > 0:
            marcar_sem_zeros(subregião)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Aritmética de intervalos para zeta | APROVADO (técnica conhecida) |
| Região livre de zeros via bounds | APROVADO (se bound > 0) |
| Cobrir todo plano complexo | REJEITADO (infinito não coberto) |

---

## 6. Registro de agentes

- Pesquisador: Interval arithmetic, validated numerics, Riemann-Siegel bounds.
- Professor: Bounds para |ζ(s)|, região livre de zeros, propagação de erro.
- Aluno: Pseudocódigo de bounds de intervalo, exemplo numérico.
- QA: Contesta que bounds finitos não provam para todo o plano.

---

## 7. Quatro problemas derivados (terceira geração)

1. `interval-arithmetic-zeta-derivative` — Bounds para ζ'(s) (útil para zeros múltiplos).
2. `interval-arithmetic-high-precision` — Precisão arbitrária para bounds de intervalo.
3. `interval-arithmetic-other-L-functions` — Aplicar a outras funções L.
4. `interval-arithmetic-zero-free-regions` — Construir regiões livres de zeros cada vez maiores.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills