# Yang–Mills Lattice Gap Skill

**id:** yang-mills-lattice-gap  
**name:** Lattice QCD Evidence for Mass Gap  
**description:** Derived from Yang–Mills Mass Gap. Numerical evidence for mass gap via lattice gauge theory simulations with SU(2) and SU(3). Purely theoretical and educational — numerical evidence is not proof.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (numerical evidence only)  
**derived_from:** skills/yang-mills-mass-gap/skills.md  
**triggers:** "lattice QCD", "mass gap", "SU(2)", "SU(3)", "gauge theory", "Wilson loop", "glueball", "Yang-Mills numerical"

---

## 1. Enunciado (Professor)

**Problema:** Fornecer evidência numérica convincente de que a teoria de Yang–Mills pura tem mass gap Δ > 0, computando o espectro de massa de glueballs em simulações de lattice QCD.

**Método:** Simulações de Monte Carlo em rede euclidiana com ação de Wilson, extração de massas a partir de correlações de loop de Wilson.

---

## 2. Contexto (Pesquisador)

### Resultados conhecidos
- Simulações de lattice QCD mostram glueball mais leve com massa ~1.5–1.7 GeV (SU(3)).
- Para SU(2), glueball escalar mais leve ~1.5 GeV em unidades da escala da rede.
- Extrapolação para limite contínuo e volume infinito é não-trivial.

### Referências
- Teper, M.J. (1998). "Glueball masses and matrix elements".
- Chen et al. (2006). "Glueball spectrum and matrix elements on anisotropic lattices".
- arXiv: lattice QCD mass spectrum.

---

## 3. Explicação didática (Professor)

### Lattice QCD
Espaço-tempo discreto em rede. Campos de medida são variáveis nos elos (matrizes unitárias). Ação de Wilson:

```
S = β Σ_plaqueta (1 − (1/N) Re Tr U_plaqueta)
```

### Loop de Wilson
Correlator de loop de Wilson decai exponencialmente com área, revelando confinamento e massa.

### Mass gap
Se o correlator decai como exp(−Δ·t), então Δ é o mass gap.

---

## 4. Derivação e testes (Aluno)

### Pseudocódigo (ilustrativo)
```
def lattqcd_mass_gap(beta, L, T, grupo):
    configs = gerar_configuracoes_monte_carlo(beta, L, T, grupo)
    correlator = calcular_wilson_loop_correlator(configs)
    massa = ajustar_decaimento_exponencial(correlator)
    return massa
```

### Lacuna
Evidência numérica não é prova analítica. Limite contínuo (espaçamento da rede → 0) não controlado rigorosamente.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Glueball ~1.5 GeV em lattice | APROVADO | Evidência numérica robusta. |
| Mass gap provado analiticamente | REJEITADO | Não existe prova. |
| Limite contínuo controlado | EM ABERTO | Requer análise de erro de discretização. |

**Parecer QA:** Evidência forte, mas não substitui prova axiomática.

---

## 6. Registro de agentes

- **Pesquisador**: Lattice QCD, Teper, Chen et al., arXiv.
- **Professor**: Ação de Wilson, loop de Wilson, mass gap.
- **Aluno**: Pseudocódigo Monte Carlo, identificação da lacuna do limite contínuo.
- **QA**: Contesta prova analítica, valida evidência numérica.

---

## 7. Quatro problemas derivados

1. `lattice-gap-su2-vs-su3` — Comparar mass gap entre SU(2) e SU(3).
2. `lattice-continuum-limit` — Análise de erro na extrapolação para limite contínuo.
3. `lattice-glueball-spectrum` — Espectro completo de glueballs (escalar, tensor, pseudoscalar).
4. `lattice-yang-mills-pure` — Yang–Mills puro sem quarks (quenched approximation).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
