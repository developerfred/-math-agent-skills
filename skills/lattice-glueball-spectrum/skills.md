# Lattice Glueball Spectrum Skill

**id:** lattice-glueball-spectrum  
**name:** Complete Glueball Spectrum from Lattice QCD  
**description:** Derived from yang-mills-lattice-gap. Compute the complete glueball spectrum (scalar, tensor, pseudoscalar) from pure Yang–Mills lattice simulations. Purely theoretical — numerical evidence.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (numerical spectrum)  
**derived_from:** skills/yang-mills-lattice-gap/skills.md  
**triggers:** "glueball", "spectrum", "scalar", "tensor", "pseudoscalar", "lattice QCD", "Yang-Mills derived"

---

## 1. Enunciado (Professor)

Calcular o espectro completo de glueballs (estados ligados de glúons) da Yang–Mills pura via simulações de lattice. Incluir canais escalar (0⁺⁺), tensor (2⁺⁺), pseudoscalar (0⁻⁺), etc.

---

## 2. Contexto (Pesquisador)

Resultados conhecidos:
- Glueball escalar mais leve: ~1.5–1.7 GeV (SU(3)).
- Glueball tensor: ~2.2–2.4 GeV.
- Pseudoscalar: ~2.5–2.6 GeV.

Referências: Teper (1998), Morningstar & Peardon (1999), lattice glueball reviews.

---

## 3. Explicação didática (Professor)

Glueballs são estados ligados apenas de glúons (sem quarks). Em lattice, usam operadores de loop de Wilson em várias representações de grupo para projetar estados de diferente spin-paridade.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo de espectro:
```
def espectro_glueballs(configs, representacoes):
    espectro = {}
    for rep in representacoes:
        correlator = calcular_correlator_operador(configs, rep)
        massa = extrair_massa(correlator)
        espectro[rep] = massa
    return espectro
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Espectro numérico conhecido | APROVADO (evidência de simulação) |
| Identificação de estados | RESSALVA (mistura de estados possíveis) |
| Prova de existência analítica | REJEITADO |

---

## 6. Registro de agentes

- Pesquisador: Teper, Morningstar–Peardon, espectro de glueballs.
- Professor: Operadores de projeção, spin-paridade, canais.
- Aluno: Pseudocódigo de cálculo de espectro.
- QA: Contesta identificação de estados, valida método numérico.

---

## 7. Quatro problemas derivados (terceira geração)

1. `glueball-spectrum-su2` — Espectro de glueballs para SU(2).
2. `glueball-spectrum-excited` — Estados excitados de glueballs.
3. `glueball-decay-widths` — Larguras de decaimento de glueballs (se estáveis).
4. `glueball-mixing` — Mistura entre glueballs e mesons (quando quarks incluídos).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills