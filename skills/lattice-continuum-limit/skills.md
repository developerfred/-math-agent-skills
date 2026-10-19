# Lattice Continuum Limit Skill

**id:** lattice-continuum-limit  
**name:** Continuum Limit Analysis for Lattice QCD  
**description:** Derived from yang-mills-lattice-gap. Analyze systematic errors in extrapolating lattice QCD results to the continuum limit (lattice spacing → 0). Purely theoretical — numerical analysis.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (systematic error analysis)  
**derived_from:** skills/yang-mills-lattice-gap/skills.md  
**triggers:** "continuum limit", "lattice spacing", "extrapolation", "systematic error", "lattice QCD", "Yang-Mills derived"

---

## 1. Enunciado (Professor)

Analisar erros sistemáticos na extrapolação de resultados de lattice QCD para o limite contínuo (espaçamento da rede a → 0). O mass gap medido em rede finita deve ser corrigido para obter o valor físico contínuo.

---

## 2. Contexto (Pesquisador)

Simulações usam espaçamento finito a. Resultados dependem de a: M(a) = M_cont + c₁·a + c₂·a² + ... Precisa de extrapolação para a = 0. Erros de discretização são a principal fonte de incerteza sistemática.

Referências: Lüscher (1985), Symanzik (1983), reviews de lattice QCD.

---

## 3. Explicação didática (Professor)

Ação de Wilson tem erros O(a) (ou O(a²) com ação melhorada). Para obter massa física, simular em vários a e extrapolar linear ou quadraticamente.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo de extrapolação:
```
def extrapola_continuum(massas, espacamentos):
    # Ajustar M(a) = M0 + c1*a + c2*a^2
    # Retornar M0 (massa no limite contínuo)
    return ajuste_polinomial(massas, espacamentos, grau=2)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Erro de discretização existe | APROVADO |
| Extrapolação padrão usada | APROVADO |
| Prova de convergência rigorosa | EM ABERTO |

---

## 6. Registro de agentes

- Pesquisador: Lüscher, Symanzik, erros sistemáticos.
- Professor: Ação de Wilson, extrapolação, espaçamento da rede.
- Aluno: Pseudocódigo de extrapolação polinomial.
- QA: Contesta falta de prova rigorosa de convergência.

---

## 7. Quatro problemas derivados (terceira geração)

1. `lattice-continuum-improved-action` — Usar ação melhorada para reduzir erros O(a).
2. `lattice-continuum-multiple-spacings` — Simular em muitos espaçamentos para melhor extrapolação.
3. `lattice-continuum-error-bars` — Estimar barras de erro da extrapolação.
4. `lattice-continuum-volume-limit` — Combinar limite contínuo com volume infinito.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills