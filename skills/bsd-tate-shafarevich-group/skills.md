# BSD — Tate–Shafarevich Group Skill

**id:** bsd-tate-shafarevich-group  
**name:** Tate–Shafarevich Group X(E)  
**description:** Derived from bsd-elliptic-curve-rank. Investigate the Tate–Shafarevich group X(E): its finiteness, size, and role in the BSD formula. Purely theoretical — arithmetic geometry.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (finiteness conjecture)  
**derived_from:** skills/bsd-elliptic-curve-rank/skills.md  
**triggers:** "BSD", "Tate-Shafarevich", "Sha", "finiteness", "elliptic curve", "Shafarevich", "derived"

---

## 1. Enunciado (Professor)

Investigar o grupo de Tate–Shafarevich X(E) de uma curva elíptica E: o grupo de classes de homogeneidades espaços-locais que não vêm de pontos globais. BSD prevê que X(E) é finito e aparece na fórmula do coeficiente líder.

---

## 2. Contexto (Pesquisador)

X(E) mede a falha do princípio Hasse para curvas elípticas. Conhecido finito para curvas de posto 0 e 1 (Kolyvagin). Para posto ≥ 2, finitude é aberta.

Referências: Tate (1960s), Shafarevich, Kolyvagin (1990).

---

## 3. Explicação didática (Professor)

Princípio Hasse: se uma equação tem soluções em todos ℚ_p e em ℝ, então tem solução em ℚ. Para curvas elípticas, isso pode falhar; X(E) mede essa falha.

Fórmula de BSD inclui |X(E)| no numerador do coeficiente líder.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def calcular_sha(E):
    # Calcular grupos locais de Selmer e Sha
    # X(E) = Selmer(E) / imagem(E(Q))
    return tamanho_sha
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| X(E) finito para posto 0/1 | APROVADO (Kolyvagin) |
| X(E) finito para posto ≥ 2 | EM ABERTO |
| Fórmula de BSD inclui |X(E)| | APROVADO |

---

## 6. Registro de agentes

- Pesquisador: Tate, Shafarevich, Kolyvagin, grupos de Selmer.
- Professor: Princípio Hasse, espaços-locais, grupo de Sha.
- Aluno: Pseudocódigo de cálculo de Sha, exemplos.
- QA: Contesta que finitude para posto ≥ 2 não é conhecida.

---

## 7. Quatro problemas derivados (terceira geração)

1. `sha-finiteness-proof` — Tentativa de provar finitude de X(E) em geral.
2. `sha-size-bounds` — Limites superiores para |X(E)|.
3. `sha-examples` — Exemplos explícitos de curvas com X(E) não-trivial.
4. `sha-selmer-connection` — Relação entre grupos de Selmer e Sha.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills