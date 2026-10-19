# Hodge Conjecture — Abelian Varieties Skill

**id:** hodge-abelian-varieties  
**name:** Hodge Conjecture for Abelian Varieties  
**description:** Derived from hodge-k3-surfaces. Investigate the Hodge conjecture for abelian varieties, especially those with complex multiplication (CM). Known cases and open questions. Purely theoretical.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (partial results)  
**derived_from:** skills/hodge-k3-surfaces/skills.md  
**triggers:** "Hodge conjecture", "abelian varieties", "complex multiplication", "CM", "algebraic cycles", "derived"

---

## 1. Enunciado (Professor)

Investigar a conjectura de Hodge para variedades abelianas, especialmente aquelas com multiplicação complexa (CM). Variedades abelianas são variedades projetivas com estrutura de grupo abeliano.

---

## 2. Contexto (Pesquisador)

Resultado conhecido: A conjectura de Hodge vale para variedades abelianas com CM suficiente (Shimura, Deligne). Para variedades abelianas gerais, é aberta.

Referências: Shimura (1960s), Deligne (1970s), Milne (notes on motives).

---

## 3. Explicação didática (Professor)

Variedade abeliana: variedade projetiva com lei de grupo abeliano (ex: curvas elípticas, jacobianas de curvas). CM significa que o anel de endomorfismos é maior que o usual.

Classes de Hodge em variedades abelianas com CM são geradas por ciclos algébricos (resultado de Shimura).

---

## 4. Derivação e testes (Aluno)

Exemplo: curva elíptica com CM por ℤ[i] (curva y² = x³ − x). Suas classes de Hodge são geradas por ciclos algébricos (divisores).

Pseudocódigo:
```
def verifica_hodge_abeliana_com_cm(A):
    # A: variedade abeliana com CM
    return classes_hodge_sao_algebricas(A)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| CM resolve Hodge para variedades abelianas | APROVADO (casos conhecidos) |
| Variedade abeliana geral | EM ABERTO |
| Construção explícita de ciclos | DIFÍCIL (não construtiva em geral) |

---

## 6. Registro de agentes

- Pesquisador: Shimura, Deligne, CM, conjectura de Hodge para abelianas.
- Professor: Variedades abelianas, estrutura de grupo, CM.
- Aluno: Exemplo curva elíptica CM, pseudocódigo.
- QA: Contesta que CM não cobre todos os casos.

---

## 7. Quatro problemas derivados (terceira geração)

1. `abelian-varieties-jacobian` — Conjectura de Hodge para jacobianas de curvas.
2. `abelian-varieties-cm-classification` — Classificação de variedades abelianas com CM.
3. `abelian-varieties-motive` — Motivos associados a variedades abelianas.
4. `abelian-varieties-hodge-group` — Grupo de Hodge e sua relação com ciclos algébricos.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills