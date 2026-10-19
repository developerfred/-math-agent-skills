# Hodge Conjecture Skill

**id:** hodge-conjecture  
**name:** Hodge Conjecture — Clay Millennium Prize Problem  
**description:** 4-agent cycle skill for the Hodge Conjecture (open since 1950/2000). Investigates whether every Hodge class on a smooth complex projective algebraic variety is a rational linear combination of cohomology classes of algebraic cycles. Purely theoretical and educational — no claim of solution.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (unsolved since 1950)  
**derived_from:** skills/millennium-prize-problems/skills.md  
**triggers:** "Hodge conjecture", "algebraic geometry", "Hodge class", "algebraic cycle", "cohomology", "complex projective variety", "millennium", "clay", "Hodge theory"

---

## 1. Enunciado (Professor)

**Conjectura de Hodge (1950):** Seja X uma variedade algébrica complexa projetiva suave. Toda classe de Hodge (uma classe de cohomologia racional de tipo (p,p) que também é racional) é uma combinação racional linear de classes de cohomologia de ciclos algébricos.

Em termos mais formais: seja H^{2p}(X, ℚ) o grupo de cohomologia de grau 2p com coeficientes racionais, e H^{p,p}(X) o subespaço de classes de tipo (p,p) na decomposição de Hodge. Então:

```
H^{2p}(X, ℚ) ∩ H^{p,p}(X) = imagem do grupo de ciclos algébricos de codimension p em H^{2p}(X, ℚ)
```

**Por que importa:** A conjectura pontua entre geometria algébrica (ciclos algébricos = subvariedades definidas por equações polinomiais) e topologia/diferencial (classes de cohomologia). Se verdadeira, diz que certas informações topológicas complexas são, na verdade, algébricas.

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Histórico
- Hodge (1950) formulou a conjectura em sua palestra no Congresso Internacional de Matemáticos.
- Clay Mathematics Institute incluiu a Conjectura de Hodge como Problema do Prêmio do Milênio (2000).
- Casos especiais são conhecidos (variedades de dimensão < 4, certas superfícies, variedades abelianas em alguns casos).

### Resultados conhecidos
- A conjectura é verdadeira para variedades de dimensão ≤ 3 (Lefschetz (1,1) teorema para p=1; casos de p=2 em dimensão 3 conhecidos).
- A conjectura de Hodge é conhecida para certas classes de variedades (ex: variedades abelianas com multiplicação complexa suficiente, certas superfícies K3).
- Contra-exemplos são conhecidos para a versão integral (coeficientes ℤ em vez de ℚ) — Atiyah–Hirzebruch mostrou que a versão integral é falsa.

### Referências sugeridas
- Hodge, W.V.D. (1950). "The topological invariants of algebraic varieties".
- Lefschetz, S. "L'Analysis Situs et la Géométrie Algébrique".
- Atiyah & Hirzebruch — contra-exemplos na versão integral.
- arXiv: papers sobre geometria algébrica, teoria de Hodge, ciclos algébricos.

---

## 3. Explicação didática (Professor)

### Intuição
Imagine uma variedade algébrica complexa (solucionário de equações polinomiais em variáveis complexas). Ela tem uma estrutura topológica (buracos, ciclos) e uma estrutura algébrica (subvariedades definidas por equações). A teoria de Hodge decompõe a cohomologia em tipos (p,q). As classes de tipo (p,p) são as que "se comportam bem" sob conjugação complexa.

A Conjectura de Hodge diz: toda classe topológica racional de tipo (p,p) pode ser escrita como combinação de classes de subvariedades algébricas. Ou seja: topologia (p,p) = álgebra.

### Exemplo: o teorema de Lefschetz (1,1)
Para p = 1, a conjectura é verdadeira: toda classe de Hodge de tipo (1,1) é a classe de Chern de um feixe de linhas (divisor algébrico). Este é o Teorema de Lefschetz sobre (1,1).

### Casos em que falha (versão integral)
Se usarmos coeficientes inteiros (ℤ) em vez de racionais (ℚ), a conjectura é falsa. Existem classes de cohomologia inteira de tipo (p,p) que não são combinações inteiras de ciclos algébricos (Atiyah–Hirzebruch).

---

## 4. Derivação e testes (Aluno)

### Exemplo ilustrativo: superfície K3
Uma superfície K3 é uma variedade complexa projetiva suave de dimensão 2. Sua cohomologia H² tem decomposição de Hodge:
```
H² = H^{2,0} ⊕ H^{1,1} ⊕ H^{0,2}
```
Para K3, h^{2,0} = 1, h^{1,1} = 20, h^{0,2} = 1. As classes de tipo (1,1) são conhecidas por serem geradas por divisores algébricos (teorema de Lefschetz). Assim, para p=1 em dimensão 2, a conjectura vale.

### Pseudocódigo (ilustrativo, conceitual)
```
def eh_classe_hodge_gerada_por_ciclos(X, p):
    # X: variedade algébrica complexa projetiva suave
    # p: codimension
    hodge_classes = classes_tipo_pp(X, p)  # H^{2p}(X, Q) ∩ H^{p,p}(X)
    algebraic_cycles = ciclos_algebricos(X, p)
    for classe in hodge_classes:
        if classe not in span_racional(algebraic_cycles):
            return False, classe
    return True, None
```

### Lacuna identificada pelo aluno
Para dimensões ≥ 4 e p ≥ 2, a conjectura é aberta. Não se conhece um contra-exemplo nem uma prova geral. Além disso, a construção explícita de ciclos algébricos a partir de classes de Hodge é não-trivial.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Conjectura de Hodge para p=1 | APROVADO | Teorema de Lefschetz (1,1). |
| Conjectura para dimensão ≤ 3 | APROVADO | Casos parciais conhecidos. |
| Versão integral (coeficientes ℤ) | REJEITADO como falsa | Contra-exemplos de Atiyah–Hirzebruch. |
| Conjectura geral (dimensão ≥ 4, p ≥ 2) | EM ABERTO | Sem prova nem contra-exemplo conhecido. |
| Hodge conecta topologia e álgebra | APROVADO | Interpretação correta do problema. |

**Parecer QA:** A Conjectura de Hodge é central na geometria algébrica moderna. Não afirmar solução sem prova geral e revisão por pares.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou história (Hodge 1950), casos conhecidos (Lefschetz, dimensão ≤ 3), contra-exemplos integrais (Atiyah–Hirzebruch), referências.
- **Professor**: Explicou decomposição de Hodge, classes (p,p), intuição topologia = álgebra, teorema de Lefschetz (1,1).
- **Aluno**: Testou superfície K3, pseudocódigo conceitual de verificação, identificou limitação para dimensão ≥ 4.
- **QA**: Contesta que casos particulares não provam o geral, valida versão integral como falsa, exige distinção clara.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `hodge-k3-surfaces` — Verificação da conjectura de Hodge para superfícies K3 (caso p=1, dim 2) e extensão para p=2.
2. `hodge-abelian-varieties` — Estudo da conjectura para variedades abelianas, especialmente com multiplicação complexa.
3. `hodge-motivic-interpretation` — Interpretação motívica de classes de Hodge; conexão com motivos de Grothendieck.
4. `hodge-algebraic-cycles-construction` — Construção explícita de ciclos algébricos a partir de classes de Hodge dadas em exemplos concretos.

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Geometria algébrica pura; não implica aplicação tecnológica.
- Não constitui prova da Conjectura de Hodge.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
