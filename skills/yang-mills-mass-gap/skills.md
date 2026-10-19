# Yang–Mills Existence and Mass Gap Skill

**id:** yang-mills-mass-gap  
**name:** Yang–Mills Existence and Mass Gap — Clay Millennium Prize Problem  
**description:** 4-agent cycle skill for Yang–Mills Existence and Mass Gap (open since 2000). Investigates whether quantum Yang–Mills theory on ℝ⁴ exists and has a mass gap: the lightest particle (glueball) has strictly positive mass. Purely theoretical and educational — no claim of solution.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (unsolved since 2000)  
**derived_from:** skills/millennium-prize-problems/skills.md  
**triggers:** "Yang Mills", "mass gap", "quantum field theory", "gauge theory", "glueball", "Standard Model", "millennium", "clay", "Yang-Mills equations"

---

## 1. Enunciado (Professor)

**Problema de Yang–Mills Existence and Mass Gap:** Provar que a teoria quântica de Yang–Mills existe no espaço-tempo de 4 dimensões (ℝ⁴) e possui um **espaço de massa (mass gap)**: existe uma constante Δ > 0 tal que todo estado de excitação da teoria tem energia pelo menos Δ acima do vácuo. Em outras palavras, não existe partícula sem massa (além do fóton, que não vem de Yang–Mills puro) no espectro da teoria.

A teoria de Yang–Mills descreve campos de medida (gauge fields) associados a um grupo de Lie compacto (tipicamente SU(3) para a força nuclear forte). As equações clássicas de Yang–Mills são:

```
D_μ F^{μν} = 0
```

Onde F^{μν} é o tensor do campo de medida e D_μ é a derivada covariante.

**Por que importa:** A força nuclear forte (cromodinâmica quântica, QCD) é uma teoria de Yang–Mills com grupo SU(3). O mass gap explica por que a força forte é de curto alcance: os glúons são sem massa no nível clássico, mas as partículas compostas (glueballs, hádrons) têm massa positiva, confinando os quarks.

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Histórico
- Yang & Mills (1954) introduziram teorias de medida não-abelianas.
- 't Hooft e Veltman (1971) mostraram renormalizabilidade de teorias de medida não-abelianas.
- Gross, Wilczek e Politzer (1973) descobriram assintoticamente livre (asymptotic freedom) da QCD — Prêmio Nobel 2004.
- Clay Mathematics Institute incluiu Yang–Mills como Problema do Prêmio do Milênio (2000).

### Resultados conhecidos
- **Assintoticamente livre:** Em altas energias, a interação se torna fraca; em baixas energias, fica forte (confinamento).
- **Simulações de rede (lattice QCD):** Evidência numérica forte de confinamento e mass gap positivo, mas não prova analítica.
- **Construção axiomática:** Não existe construção axiomática completa de Yang–Mills em 4D que satisfaça os axiomas de Wightman ou Osterwalder–Schrader.
- **Mass gap:** Não há prova analítica de que Δ > 0 para Yang–Mills puro em ℝ⁴.

### Referências sugeridas
- Yang, C.N. & Mills, R.L. (1954). "Conservation of Isotopic Spin and Isotopic Gauge Invariance".
- Jaffe, A. & Witten, E. (2006). "Quantum Yang–Mills theory" (Millennium Prize Problems volume).
- arXiv: papers sobre lattice QCD, construção axiomática de teorias de medida, mass gap.

---

## 3. Explicação didática (Professor)

### Intuição
Imagine o espaço-tempo como um tecido. Em cada ponto, há um "giroscopio interno" (grupo de medida SU(3)) que pode apontar em diferentes direções. O campo de medida mede como esse giroscopio muda de ponto a ponto. As partículas que mediam essa interação são os glúons.

No nível clássico, as equações de Yang–Mills permitem soluções sem massa (ondas de glúon). Mas na teoria quântica, interações fortes podem gerar uma massa efetiva para partículas compostas (como um sistema de duas massas conectadas por uma mola forte pode ter modos de vibração com frequência mínima não-zero).

### O mass gap
Se há um mass gap Δ > 0, então não há estados de energia arbitrariamente próxima do vácuo. Isso significa que a teoria tem uma "escala de massa" intrínseca — explica por que partículas fortes (prótons, nêutrons) têm massa ~1 GeV mesmo que quarks tenham massa pequena.

### Por que é difícil provar
- A teoria quântica de campos em 4D envolve integrais de caminho (path integrals) não bem definidos matematicamente.
- Não se sabe construir a teoria de forma axiomática (Wightman axioms) em 4D.
- O confinamento (quarks isolados não são observados) é observado numericamente, mas não provado analiticamente.

---

## 4. Derivação e testes numéricos (Aluno)

### Exemplo ilustrativo: lattice QCD
Em uma rede discreta de espaço-tempo, os campos de medida são variáveis nos elos entre sítios. A ação de Wilson:

```
S = (β / 2) Σ_{plaquetas} (1 − (1/N) Re Tr U_{plaqueta})
```

Simulações numericas computam o espectro de massa de glueballs e hádrons. Resultados típicos: o glueball mais leve tem massa ~1.5–1.7 GeV, consistente com mass gap positivo.

### Pseudocódigo (ilustrativo, não prova)
```
def lattqcd_mass_gap(beta, lattice_size):
    # Gerar configurações de campo de medida via importância amostragem
    configs = gerar_configuracoes(beta, lattice_size)
    # Calcular correlator de Wilson loops
    correlator = calcular_wilson_loop(configs)
    # Extrair massa do decaimento exponencial
    massa = extrair_massa(correlator)
    return massa
```

### Lacuna identificada pelo aluno
Simulações de rede são evidencia numérica, não prova analítica. Além disso, a rede tem espaçamento finito e volume finito; o limite contínuo e infinito-volume requer controle rigoroso.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Yang–Mills clássico bem definido | APROVADO | Equações diferenciais parciais clássicas. |
| Yang–Mills quântico em 4D axiomática | EM ABERTO | Não existe construção completa satisfazendo axiomas de Wightman. |
| Mass gap Δ > 0 | EM ABERTO | Evidência numérica forte, não prova analítica. |
| Lattice QCD prova mass gap? | REJEITADO | Evidência numérica; limite contínuo não provado rigorosamente. |
| Yang–Mills explica confinamento? | ESPECULATIVO | Confinamento observado numericamente; mecanismo analítico não provado. |

**Parecer QA:** Yang–Mills massa gap é um dos problemas centrais da física matemática. Não afirmar solução sem prova analítica e aceitação da comunidade.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou história (Yang–Mills 1954, 't Hooft–Veltman, Nobel 2004), lattice QCD, axiomas de Wightman, referências.
- **Professor**: Explicou intuição do campo de medida, mass gap, confinamento, dificuldade da construção quântica em 4D.
- **Aluno**: Testou conceito de lattice QCD, pseudocódigo de extração de massa, identificou limitação numérica vs analítica.
- **QA**: Contesta claims de prova, valida distinção entre evidência numérica e prova, rejeita confinamento como fato demonstrado.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `yang-mills-lattice-gap` — Evidência numérica de mass gap via simulações de lattice QCD com diferentes grupos de medida (SU(2), SU(3)).
2. `yang-mills-axiomatic-construction` — Tentativa de construção axiomática de Yang–Mills em 4D (axiomas de Osterwalder–Schrader ou Wightman).
3. `yang-mills-confinement-mechanism` — Estudo do mecanismo de confinamento (imagem de supercondutor dual, cordas de fluxo).
4. `yang-mills-mass-gap-rigorous` — Prova ou contra-exemplo para existência de mass gap Δ > 0 em Yang–Mills puro em ℝ⁴.

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Física de partículas teórica; não implica aplicação tecnológica ou militar.
- Não constitui prova do Prêmio do Milênio de Yang–Mills.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
