# Circuit Lower Bounds — Non-Monotone Circuits Skill

**id:** circuit-lower-bounds-nonmonotone  
**name:** Non-Monotone Circuit Lower Bounds  
**description:** Derived from circuit-lower-bounds. Investigate super-polynomial lower bounds for general Boolean circuits (with NOT gates). This is the main barrier to proving P ≠ NP via circuit complexity. Purely theoretical.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (major barrier)  
**derived_from:** skills/p-vs-np-circuit-lower-bounds/skills.md  
**triggers:** "non-monotone circuit", "NOT gate", "super-polynomial", "explicit function", "circuit complexity barrier", "P vs NP derived"

---

## 1. Enunciado (Professor)

Provar limite inferior super-polinomial para circuitos booleanos gerais (com AND, OR, NOT) computando alguma função explícita em NP. Este é o principal obstáculo para provar P ≠ NP via complexidade de circuitos.

---

## 2. Contexto (Pesquisador)

Melhores limites conhecidos para circuitos gerais de funções explícitas são lineares (~3n) ou quase-lineares. Não se conhece limite super-polinomial para nenhuma função explícita em NP com circuitos gerais.

Referências: Paz & Schmidt (1982), Paul et al. (1983), recent works on circuit lower bounds.

---

## 3. Explicação didática (Professor)

NOT gates tornam funções não-monotônicas. Técnicas de limite inferior monotônio (aproximação por funções menores/maiores) falham porque NOT permite "desfazer" monotonicidade.

---

## 4. Derivação e testes (Aluno)

Exemplo: função PARIDADE tem circuito linear com NOT gates. Não é candidata para limite inferior alto.

Pseudocódigo de busca por limite inferior geral:
```
def busca_limite_geral(f, n_max):
    for n in range(1, n_max+1):
        tam = menor_circuito_geral(f, n)  # desconhecido para n grande
        if tam > n**10:
            reportar(n, tam)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Limite super-polinomial geral conhecido | REJEITADO (não existe para funções explícitas) |
| Barreira Natural Proofs bloqueia | APROVADO (Razborov–Rudich 1997) |
| Algebrization também bloqueia | APROVADO (Aaronson–Wigderson 2009) |

---

## 6. Registro de agentes

- Pesquisador: limites conhecidos, barreiras de prova.
- Professor: circuitos gerais, NOT gates, dificuldade.
- Aluno: exemplo paridade, pseudocódigo de busca.
- QA: confirma barreira, rejeita otimismo injustificado.

---

## 7. Quatro problemas derivados (terceira geração)

1. `nonmonotone-limit-3n` — Melhorar limite linear 3n para alguma função explícita.
2. `nonmonotone-barrier-analysis` — Análise detalhada de por que técnicas atuais falham.
3. `nonmonotone-proof-strategy` — Nova estratégia de prova contornando barreiras.
4. `nonmonotone-function-candidates` — Novas funções candidatas a limite inferior alto.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills