# Lattice Gap — SU(2) vs SU(3) Skill

**id:** lattice-gap-su2-vs-su3  
**name:** Comparing Mass Gap between SU(2) and SU(3) Gauge Groups  
**description:** Derived from yang-mills-lattice-gap. Compare numerical mass gap evidence between SU(2) and SU(3) pure Yang–Mills lattice simulations. Purely theoretical — numerical evidence only.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (numerical comparison)  
**derived_from:** skills/yang-mills-lattice-gap/skills.md  
**triggers:** "SU(2)", "SU(3)", "mass gap", "lattice", "glueball", "comparison", "Yang-Mills derived"

---

## 1. Enunciado (Professor)

Comparar o mass gap entre grupos de medida SU(2) e SU(3) em simulações de lattice QCD pura. O grupo SU(3) descreve a força forte real; SU(2) é um caso simplificado útil para testes.

---

## 2. Contexto (Pesquisador)

Simulações de lattice mostram:
- SU(2): glueball escalar mais leve ~1.5 GeV (em unidades de escala).
- SU(3): glueball escalar mais leve ~1.5–1.7 GeV.

Referências: Teper (1998), Chen et al. (2006), lattice QCD reviews.

---

## 3. Explicação didática (Professor)

Grupo SU(N): matrizes unitárias N×N com determinante 1. SU(2) é mais simples (3 geradores), SU(3) tem 8 geradores (cromodinâmica quântica real).

O mass gap depende do grupo: mais geradores = interações mais complexas = possível massa diferente.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo de comparação:
```
def comparar_gap_grupo(grupo, beta, L, T):
    massa = lattqcd_mass_gap(beta, L, T, grupo)
    return massa

gap_su2 = comparar_gap_grupo('SU(2)', beta, L, T)
gap_su3 = comparar_gap_grupo('SU(3)', beta, L, T)
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Diferença numérica SU(2) vs SU(3) | APROVADO (evidência de simulação) |
| Prova analítica de diferença | REJEITADO |
| SU(2) como modelo para SU(3) | RESSALVA (aproximação) |

---

## 6. Registro de agentes

- Pesquisador: Teper, Chen, comparações de grupo.
- Professor: SU(N), SU(2) vs SU(3), física de partículas.
- Aluno: Pseudocódigo de comparação, execução mental.
- QA: Contesta extrapolação, valida evidência numérica.

---

## 7. Quatro problemas derivados (terceira geração)

1. `lattice-gap-su-n-general` — Generalizar para SU(N) com N arbitrário.
2. `lattice-gap-scaling` — Escala do mass gap com N.
3. `lattice-gap-quenched-vs-dynamic` — Comparar aproximação quenched vs quarks dinâmicos.
4. `lattice-gap-temperature` — Mass gap em temperatura finita (desconfínamento).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills