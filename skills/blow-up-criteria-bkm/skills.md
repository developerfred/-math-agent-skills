# Blow-up Criteria (Beale–Kato–Majda) Skill

**id:** blow-up-criteria-bkm  
**name:** Beale–Kato–Majda Criterion for Fluid Singularities  
**description:** Skill derivado do ciclo Euler/Navier–Stokes. Formaliza o critério de Beale–Kato–Majda para explosão de soluções de equações de Euler e Navier–Stokes em 3D. Conteúdo esteducional e teórico.  
**author:** codingsh <codingsh@pm.me>  
**status:** teorema conhecido (1984) — aplicado a problemas em aberto  
**derived_from:** skills/euler-equations-regularity/skills.md  
**triggers:** "beale kato majda", "bkm", "blow up", "vorticity", "singularity", "criteria", "regularity", "fluid", "euler", "navier stokes"

---

## 1. Enunciado (Professor)

Seja u(x,t) uma solução de Euler ou Navier–Stokes incompressível em 3D, suave em [0, T). Se a solução deixa de ser suave no tempo T* (primeiro tempo de explosão), então:

```
∫₀^T* ||ω(t)||_{L^∞} dt = ∞
```

Onde ω = ∇ × u é a vorticidade.

**Contrapositive:** Se ∫₀^T ||ω(t)||_{L^∞} dt < ∞ para algum T, então a solução pode ser estendida suavemente além de T.

Equivalentemente, a explosão requer que a vorticidade máxima cresça de forma não integrável no tempo.

---

## 2. Contexto (Pesquisador)

- Beale, Kato e Majda (1984), "Remarks on the breakdown of smooth solutions for the 3-D Euler equations", Communications in Mathematical Physics.
- O critério se aplica tanto a Euler (ν = 0) quanto a Navier–Stokes (ν > 0).
- É um dos principais resultados sobre regularidade de equações de fluidos incompressíveis.
- Relacionado ao Prêmio do Milênio: prova de que ||ω||_∞ permanece limitado para Navier–Stokes resolveria o problema da existência e suavidade.

---

## 3. Explicação didática (Professor)

### O que o critério diz em palavras
Para que um fluido desenvolva uma singularidade em tempo finito (velocidade ou vorticidade "explode"), a vorticidade máxima deve se tornar tão grande que sua integral no tempo diverge. Se a vorticidade máxima cresce devagar o suficiente (integrável), não há explosão.

### Intuição da prova (esboço)
1. Use a equação da vorticidade com termo de alongamento (ω · ∇)u.
2. Use desigualdades de Sobolev e de Biot–Savart para controlar u em termos de ω.
3. Aplique desigualdade de Gronwall a uma norma de Sobolev de ordem alta de u.
4. O coeficiente de Gronwall envolve ||ω||_{L^∞}. Se essa norma for integrável no tempo, a norma de Sobolev permanece limitada → não há explosão.

---

## 4. Derivação e exemplos (Aluno)

### Exemplo numérico ilustrativo (não prova)
Considere ||ω(t)||_∞ ~ (T* - t)^(-α) próximo de T*.

- Se α < 1: ∫₀^T* (T* - t)^(-α) dt < ∞ → BKM não prevê explosão necessária (mas não descarta).
- Se α ≥ 1: ∫₀^T* (T* - t)^(-α) dt = ∞ → condição BKM para explosão satisfeita.

### Pseudocódigo de verificação (ilustrativo)
```
max_vorticity_over_time = []
for t in time_steps:
    omega = compute_vorticity(u)
    max_vorticity_over_time.append(max(abs(omega)))
# Verificar se integral de max(|omega|) diverge à medida que t -> T*
```

### Lacuna do aluno
Estimar ||ω||_∞ numericamente perto de uma suposta singularidade é extremamente sensível à resolução da grade e ao esquema numérico.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Teorema BKM (1984) | APROVADO | Resultado rigoroso, publicado, amplamente aceito. |
| Aplicação a Navier–Stokes | APROVADO | Válido para ν > 0 também. |
| BKM prova que Navier–Stokes explode? | REJEITADO | Não. BKM dá condição necessária, não prova nem existência nem explosão. |
| BKM prova que Navier–Stokes é suave globalmente? | REJEITADO | Não. Só mostra que se ||ω||_∞ for integrável, não explode. |
| Propostas recentes (2026) usando BKM | RESSALVA | Exigir revisão por pares e verificação independente (Clay Institute, ≥ 2 anos). |

**Parecer QA:** BKM é uma ferramenta válida e rigorosa, mas não resolve por si só o Prêmio do Milênio.

---

## 6. Registro de agentes

- **Pesquisador**: origem do teorema (Beale-Kato-Majda, 1984), aplicação a fluidos incompressíveis.
- **Professor**: enunciado formal, contrapositivo, intuição da prova via Gronwall.
- **Aluno**: exemplo de taxa de crescimento (T* - t)^(-α), pseudocódigo de verificação.
- **QA**: contesta claims excessivos, valida escopo do teorema.

---

## 7. Próximo passo sugerido

Estudar extensões do critério BKM (espaços de Besov, critérios de tipo Serrin para Navier–Stokes) e sua relação com a regularidade de soluções fracas de Leray–Hopf.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
