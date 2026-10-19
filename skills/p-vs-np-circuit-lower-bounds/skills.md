# P vs NP — Circuit Lower Bounds Skill

**id:** p-vs-np-circuit-lower-bounds  
**name:** Circuit Lower Bounds for Explicit Functions  
**description:** Derived from P vs NP. Investigates whether explicit Boolean functions require super-polynomial circuit size. If an explicit function requires super-polynomial circuits, then P ≠ NP. Purely theoretical and educational.  
**author:** codingsh <codingsh@pm.me>  
**status:** open  
**derived_from:** skills/p-vs-np/skills.md  
**triggers:** "circuit lower bounds", "P vs NP", "boolean circuit", "super-polynomial", "explicit function", "circuit complexity", "Razborov", "natural proofs"

---

## 1. Enunciado (Professor)

**Problema:** Existe uma função booleana explícita $f: \{0,1\}^n \to \{0,1\}$ tal que qualquer circuito booleano que a compute tenha tamanho super-polinomial em $n$?

Se sim, então P ≠ NP, porque se P = NP, toda função em NP teria circuitos de tamanho polinomial.

**Funções candidatas:**
- **Clique:** Dado um grafo com $n$ vértices, existe um clique de tamanho $k$?
- **Paridade:** $f(x) = x_1 \oplus x_2 \oplus ... \oplus x_n$
- **Majority:** $f(x) = 1$ se mais da metade dos bits é 1
- **Permanente:** $\text{Per}(A)$ para matriz $n \times n$ 0-1

---

## 2. Contexto (Pesquisador)

### Resultados conhecidos
- **Razborov (1985):** Limite inferior exponencial para clique em circuitos monotônios (não usa NOT gates).
- **Razborov–Rudich (1997):** Barreira dos "Natural Proofs" — muitas técnicas de limite inferior não conseguem provar P ≠ NP porque provariam demais.
- **Limites para circuitos não-monotônios:** Muito mais difíceis; melhores limites conhecidos são apenas lineares ou quase-lineares para funções explícitas.

### Referências
- Razborov, A.A. (1985). "Lower bounds on the monotone complexity of some Boolean functions".
- Razborov, A.A. & Rudich, S. (1997). "Natural proofs".
- Arora & Barak, "Computational Complexity", Capítulo 14.

---

## 3. Explicação didática (Professor)

### Circuito booleano
Um circuito booleano é um DAG com portas AND, OR, NOT. O tamanho é o número de portas.

### Por que limite inferior implica P ≠ NP
Se toda função em NP tem circuito de tamanho polinomial, e SAT é NP-completo, então SAT tem circuito polinomial. Como a avaliação de circuito é em P, isso implicaria P = NP.

Portanto, provar que alguma função explícita em NP exige circuitos super-polinomiais prova P ≠ NP.

### Estratégia de prova
1. Escolha uma função explícita $f$ em NP (ex: clique).
2. Mostre que qualquer circuito computando $f$ tem tamanho $\omega(n^k)$ para todo $k$.
3. Conclua P ≠ NP.

---

## 4. Derivação e testes (Aluno)

### Exemplo: paridade em circuitos monotônios
Paridade não pode ser computada por circuitos monotônios (sem NOT). Mas com NOT gates, paridade tem circuito linear.

### Pseudocódigo de busca (ilustrativo)
```
def encontra_limite_inferior(f, n_max):
    for n in range(1, n_max+1):
        tamanho_min = buscar_menor_circuito(f, n)
        if tamanho_min > polinomio(n, grau=10):
            reportar(n, tamanho_min)
```

### Lacuna
Não se conhece limite inferior super-polinomial para circuitos gerais (com NOT) de nenhuma função explícita em NP.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Limite inferior exponencial para clique monotônio | APROVADO | Razborov 1985, circuito sem NOT. |
| Limite inferior para circuitos gerais | EM ABERTO | Não conhecido para funções explícitas. |
| Barreira Natural Proofs | APROVADO | Razborov–Rudich bloqueia muitas abordagens. |
| Limite linear implica P ≠ NP? | REJEITADO | Precisa ser super-polinomial. |

**Parecer QA:** Abordagem promissora, mas bloqueada por barreiras conhecidas.

---

## 6. Registro de agentes

- **Pesquisador**: Razborov, Natural Proofs, literatura de complexidade de circuitos.
- **Professor**: Circuito booleano, implicação P ≠ NP, estratégia de prova.
- **Aluno**: Paridade, pseudocódigo de busca, identificação da lacuna.
- **QA**: Contesta limitações, valida barreiras.

---

## 7. Quatro problemas derivados

1. `circuit-lower-bounds-monotone` — Limites inferiores para circuitos monotônicos de funções específicas.
2. `circuit-lower-bounds-nonmonotone` — Tentativa de quebrar a barreira para circuitos com NOT.
3. `natural-proofs-barrier-analysis` — Análise detalhada de por que natural proofs falham.
4. `algebrization-barrier-circuit` — Algebrization aplicada a limites inferiores de circuitos.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
