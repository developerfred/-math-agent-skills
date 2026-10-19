# Hodge Conjecture — Algebraic Cycles Construction Skill

**id:** hodge-algebraic-cycles-construction  
**name:** Explicit Construction of Algebraic Cycles from Hodge Classes  
**description:** Derived from hodge-k3-surfaces. Investigate explicit construction of algebraic cycles representing given Hodge classes in concrete examples. Purely theoretical — computational algebraic geometry.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (computational)  
**derived_from:** skills/hodge-k3-surfaces/skills.md  
**triggers:** "algebraic cycles", "construction", "Hodge classes", "explicit", "computational algebraic geometry", "derived"

---

## 1. Enunciado (Professor)

Dada uma classe de Hodge específica em uma variedade concreta, construir explicitamente um ciclo algébrico que a represente. Esta é a direção construtiva da conjectura de Hodge.

---

## 2. Contexto (Pesquisador)

Para variedades específicas (curvas elípticas, superfícies K3, hiperssuperfícies), é possível encontrar ciclos algébricos explicitamente. Para variedades genéricas, a construção é não-trivial e não algorítmica conhecida.

Referências: Griffiths & Harris, Voisin (Hodge theory and complex algebraic geometry).

---

## 3. Explicação didática (Professor)

Um ciclo algébrico de codimension p é uma combinação formal de subvariedades irreduzíveis de dimensão n−p. Sua classe de cohomologia está em H^{2p}. A conjectura diz que toda classe de Hodge racional de tipo (p,p) vem de tal ciclo.

---

## 4. Derivação e testes (Aluno)

Exemplo: em uma curva elíptica E: y² = x³ + ax + b, uma classe (1,1) é gerada por [E] (a própria curva) e por pontos [P]. Qual classe (1,1) é combinação racional desses.

Pseudocódigo:
```
def construir_ciclo_algebrico(classe_hodge, variedade):
    # Buscar subvariedades cuja classe de cohomologia seja classe_hodge
    return ciclo_encontrado
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Construção em casos específicos | APROVADO (curvas elípticas, K3 simples) |
| Construção geral algorítmica | NÃO CONHECIDA |
| Computacionalmente viável | PARCIAL (para variedades pequenas) |

---

## 6. Registro de agentes

- Pesquisador: Construção explícita, geometria algébrica computacional.
- Professor: Ciclos algébricos, classes de cohomologia, direção construtiva.
- Aluno: Exemplo curva elíptica, pseudocódigo de busca.
- QA: Contesta falta de algoritmo geral.

---

## 7. Quatro problemas derivados (terceira geração)

1. `algebraic-cycles-curves` — Construção explícita para curvas algébricas.
2. `algebraic-cycles-surfaces` — Construção para superfícies (divisores e curvas nelas).
3. `algebraic-cycles-hypersurfaces` — Construção para hiperssuperfícies em ℙⁿ.
4. `algebraic-cycles-algorithm` — Tentativa de algoritmo geral para construção de ciclos.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills