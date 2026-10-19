# Hodge Conjecture — K3 Surfaces Skill

**id:** hodge-k3-surfaces  
**name:** Hodge Conjecture for K3 Surfaces  
**description:** Derived from Hodge Conjecture. Verify the Hodge conjecture for K3 surfaces (dimension 2, p = 1) using Lefschetz (1,1) theorem. Purely theoretical and educational.  
**author:** codingsh <codingsh@pm.me>  
**status:** known case (p = 1)  
**derived_from:** skills/hodge-conjecture/skills.md  
**triggers:** "Hodge conjecture", "K3 surface", "Lefschetz (1,1)", "algebraic cycle", "cohomology", "Kähler"

---

## 1. Enunciado (Professor)

**Problema:** Verificar que para uma superfície K3 (variedade complexa projetiva suave de dimensão 2), toda classe de Hodge de tipo (1,1) é a classe de Chern de um divisor algébrico (ciclo algébrico de codimension 1).

Isso é o teorema de Lefschetz (1,1), que resolve o caso p = 1 da conjectura de Hodge.

---

## 2. Contexto (Pesquisador)

### Resultados conhecidos
- **Lefschetz (1,1):** Toda classe de Hodge racional de tipo (1,1) em uma variedade Kähler projetiva é a classe de Chern de um feixe de linhas holomorfo.
- Superfícies K3 têm h^{1,1} = 20, h^{2,0} = h^{0,2} = 1.
- O caso p = 2 em dimensão 2 é trivial (H^{4} é gerado pela classe do ponto, que é algébrica).

### Referências
- Lefschetz, S. "L'Analysis Situs et la Géométrie Algébrique".
- Griffiths & Harris, "Principles of Algebraic Geometry".
- Huybrechts, "Lectures on K3 Surfaces".

---

## 3. Explicação didática (Professor)

### Superfície K3
Variedade complexa projetiva suave de dimensão 2, canonicamente trivial, simplesmente conexa.

### Decomposição de Hodge para K3
```
H²(K3, ℂ) = H^{2,0} ⊕ H^{1,1} ⊕ H^{0,2}
dimensões: 1 + 20 + 1 = 22 = b₂
```

### Teorema de Lefschetz (1,1)
Uma classe α ∈ H²(X, ℚ) está em H^{1,1} se e somente se α é a classe de Chern c₁(L) de algum feixe de linhas L.

Portanto, para p = 1, a conjectura de Hodge é verdadeira para K3.

---

## 4. Derivação e testes (Aluno)

### Exemplo: superfície K3 quartica em ℙ³
Definida por equação homogênea de grau 4 em 4 variáveis. Sua cohomologia H² tem 22 dimensões. As 20 classes de tipo (1,1) vêm de divisores algébricos (seções hiperplanas, curvas na superfície).

### Pseudocódigo (ilustrativo)
```
def verifica_hodge_k3_p1(X):
    # X: superfície K3
    hodge_classes = classes_tipo_11(X)  # H²(X, Q) ∩ H^{1,1}
    algebraic = classes_c1_feixes_linhas(X)
    return hodge_classes == span_racional(algebraic)
```

### Lacuna
Para p = 2 em dimensão ≥ 4, a conjectura é aberta.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Lefschetz (1,1) para K3 | APROVADO | Teorema clássico. |
| p = 1 resolvido para K3 | APROVADO | Caso conhecido. |
| p ≥ 2 em K3 | TRIVIAL | H⁴ gerado pelo ponto (algébrico). |
| Conjectura geral de Hodge | EM ABERTO | Dimensão ≥ 4, p ≥ 2. |

**Parecer QA:** Caso p = 1 está resolvido; o desafio é p ≥ 2.

---

## 6. Registro de agentes

- **Pesquisador**: Lefschetz (1,1), cohomologia de K3, referências.
- **Professor**: Decomposição de Hodge, teorema de Lefschetz, classes de Chern.
- **Aluno**: Exemplo quartica em ℙ³, pseudocódigo de verificação.
- **QA**: Valida caso conhecido, distingue do caso aberto.

---

## 7. Quatro problemas derivados

1. `hodge-k3-p2` — Caso p = 2 para superfícies K3 (trivial, mas documentar).
2. `hodge-abelian-varieties` — Conjectura de Hodge para variedades abelianas.
3. `hodge-motivic` — Interpretação motívica de classes de Hodge.
4. `hodge-algebraic-cycles` — Construção explícita de ciclos algébricos.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
