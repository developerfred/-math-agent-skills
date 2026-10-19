# BSD — Congruent Number Problem Skill

**id:** bsd-congruent-number-problem  
**name:** Congruent Numbers and Elliptic Curves  
**description:** Derived from bsd-elliptic-curve-rank. Study the connection between BSD and the congruent number problem: which integers n are areas of right triangles with rational sides? Purely theoretical — number theory.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (Tunnel's theorem connection)  
**derived_from:** skills/bsd-elliptic-curve-rank/skills.md  
**triggers:** "BSD", "congruent number", "right triangle", "rational sides", "elliptic curve y2=x3-n2x", "derived"

---

## 1. Enunciado (Professor)

Estudar a conexão entre BSD e o problema dos números congruentes: um inteiro n é congruente se é a área de um triângulo retângulo com lados racionais. Isso está relacionado à curva elíptica E_n: y² = x³ − n²x.

---

## 2. Contexto (Pesquisador)

Teorema de Tunnel (1983): Se n é congruente, então certa condição sobre coeficientes de formas modulares vale. A recíproca é verdadeira assumindo BSD para curvas y² = x³ − n²x.

Referências: Tunnel (1983), BSD original, congruent number problem history.

---

## 3. Explicação didática (Professor)

Um triângulo retângulo com lados racionais a, b, c e área n satisfaz a² + b² = c² e ab/2 = n. Isso leva à curva elíptica y² = x³ − n²x. n é congruente se e somente se esta curva tem posto ≥ 1 (ponto de ordem infinita).

---

## 4. Derivação e testes (Aluno)

Exemplo: n = 5 é congruente (triângulo 3/2, 20/3, 41/6 tem área 5). Curva y² = x³ − 25x tem ponto (−4, 6) de ordem infinita → posto 1. BSD e Tunnel são consistentes.

Pseudocódigo:
```
def eh_congruente(n):
    # Verificar se curva y² = x³ − n²x tem posto >= 1
    return posto_curva(n) >= 1
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| n = 5 é congruente | APROVADO (exemplo explícito) |
| Conexão com BSD | APROVADO (Tunnel, assumindo BSD) |
| Recíproca de Tunnel sem BSD | EM ABERTO |

---

## 6. Registro de agentes

- Pesquisador: Tunnel, problema dos números congruentes, história.
- Professor: Curva y² = x³ − n²x, posto ↔ congruência.
- Aluno: Exemplo n = 5, pseudocódigo de teste.
- QA: Contesta que BSD não é necessária para todos os casos conhecidos.

---

## 7. Quatro problemas derivados (terceira geração)

1. `congruent-number-numerical` — Verificação numérica de números congruentes para n grande.
2. `congruent-number-tunnel` — Aplicação do teorema de Tunnel para classes de n.
3. `congruent-number-other-curves` — Outras curvas elípticas relacionadas a congruência.
4. `congruent-number-history` — Revisão histórica do problema dos números congruentes.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills