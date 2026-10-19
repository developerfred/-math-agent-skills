# Pure Yang–Mills Lattice Skill

**id:** lattice-yang-mills-pure  
**name:** Pure Yang–Mills (Quenched) Lattice Simulations  
**description:** Derived from yang-mills-lattice-gap. Study pure Yang–Mills theory (no quarks, quenched approximation) on the lattice to isolate the mass gap from fermion effects. Purely theoretical — numerical.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (quenched approximation)  
**derived_from:** skills/yang-mills-lattice-gap/skills.md  
**triggers:** "pure Yang-Mills", "quenched", "no quarks", "lattice", "mass gap", "gluons only", "Yang-Mills derived"

---

## 1. Enunciado (Professor)

Estudar Yang–Mills pura (sem quarks, aproximação quenched) na lattice para isolar o mass gap dos efeitos de férmions. Isso permite focar na interação gluão-gluão pura.

---

## 2. Contexto (Pesquisador)

Aproximação quenched: ignorar determinante de férmion (det D = 1). Simulações mais rápidas, mas não incluem efeitos de pares virtuais quark-antiquark. Bom primeiro passo para isolar o mass gap gluônico.

Referências: Creutz (1983), Wilson (1974), lattice gauge theory textbooks.

---

## 3. Explicação didática (Professor)

Yang–Mills pura: apenas campos de medida, sem matéria. A ação de Wilson descreve a interação gluônica. Sem quarks, não há quebra de simetria quiral nem hádrons com quarks — apenas glueballs.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo de simulação quenched:
```
def simular_yang_mills_puro(beta, L, T, grupo):
    # Sem determinante de férmion no peso de Boltzmann
    peso = exp(-beta * ação_wilson)
    configs = amostragem_importancia(peso)
    return configs
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Quenched isola efeitos gluônicos | APROVADO |
| Não é QCD completa (sem quarks) | APROVADO (limitação conhecida) |
| Mass gap quenched ≈ mass gap QCD? | EM ABERTO (diferença pode ser pequena) |

---

## 6. Registro de agentes

- Pesquisador: Creutz, Wilson, lattice gauge theory pura.
- Professor: Aproximação quenched, ação de Wilson, gluões apenas.
- Aluno: Pseudocódigo de simulação sem férmions.
- QA: Contesta diferença com QCD completa, valida isolamento gluônico.

---

## 7. Quatro problemas derivados (terceira geração)

1. `pure-yang-mills-glueballs` — Calcular glueballs em Yang–Mills puro.
2. `pure-yang-mills-confinement` — Estudar confinamento sem quarks (cordas de fluxo).
3. `pure-yang-mills-temp` — Transição de desconfínamento em temperatura finita (puro).
4. `pure-yang-mills-unquenching` — Adicionar efeitos de férmions gradualmente.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills