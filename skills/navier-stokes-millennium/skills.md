# Navier–Stokes Millennium Prize Skill

**id:** navier-stokes-millennium  
**name:** Navier–Stokes Existence and Smoothness (Millennium Prize Problem)  
**description:** Skill gerado pelo ciclo multi-agente (pesquisador → professor → aluno → QA) sobre o Problema de Navier–Stokes da Existência e Suavidade, um dos sete Problemas do Prêmio do Milênio do Clay Mathematics Institute. Conteúdo esteducional e teórico. Não constitui prova válida nem reivindicação do prêmio.  
**author:** codingsh <codingsh@pm.me>  
**status:** aberto (problema do Prêmio do Milênio)  
**triggers:** "navier stokes", "millennium", "clay", "existence and smoothness", "fluid dynamics", "pde", "openai 2026", "counterexample", "millennium prize"

---

## 1. Enunciado (Professor)

O problema de Navier–Stokes pergunta: dado um campo de velocidade inicial suave em ℝ³ (ou no torus 3D), existem soluções suaves e globalmente definidas para o tempo para as equações de Navier–Stokes incompressíveis, ou pode ocorrer ruptura (singularidade) em tempo finito?

Equações (forma incompressível, sem forças externas):

```
∂u/∂t + (u · ∇)u = -∇p + ν Δu
∇ · u = 0
u(x, 0) = u₀(x)
```

Onde:
- `u(x,t)` = campo de velocidade (vetor em ℝ³)
- `p(x,t)` = pressão (escalar)
- `ν` = viscosidade cinemática (constante positiva)
- `u₀` = condição inicial, assumida suave e de média zero

O prêmio de US$ 1 milhão é concedido por uma prova de que:
- (A) Para toda condição inicial suave, existe uma solução suave para todo t > 0, **ou**
- (B) Existe uma condição inicial suave para a qual a solução se torna singular em tempo finito (contra-exemplo).

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Fonte: Clay Mathematics Institute (claymath.org)
O problema foi um dos sete anunciados em 2000. Apenas a Conjectura de Poincaré foi resolvida (Grigori Perelman, 2002–2003).

### Atualização de setembro de 2026 (web)
Em setembro de 2026, a OpenAI anunciou uma proposta de solução para o problema de Navier–Stokes existência e suavidade, incluindo uma prova e uma formalização em Lean. A OpenAI declarou que **não pretende reivindicar o Prêmio do Milênio** pelo resultado.

### Posicionamento do Clay Institute
O Clay Mathematics Institute **não considera** soluções propostas para problemas do Prêmio do Milênio até pelo menos dois anos após a publicação. Como de setembro de 2026, o problema segue **em aberto** do ponto de vista oficial do prêmio.

### Referências sugeridas
- Clay Mathematics Institute: https://www.claymath.org/millennium/navier-stokes-equation/
- OpenAI announcement (set/2026): "On the Navier–Stokes Millennium Prize Problem"
- Jaffe & Witten, "Quantum Yang–Mills theory" (para contexto de problemas do milênio)
- Wikipedia: Millennium Prize Problems

---

## 3. Explicação didática (Professor)

### O que o problema quer dizer em linguagem natural
Imagine fluido (água ou ar) em movimento. As equações de Navier–Stokes descrevem como a velocidade e pressão evoluem no tempo. A grande questão é: será que o fluido pode desenvolver "vórtices infinitamente intensos" (singularidades) em tempo finito, fazendo a velocidade explodir? Ou a viscosidade sempre impede isso, mantendo o movimento suave para sempre?

### Por que é difícil
- O termo não linear `(u · ∇)u` pode amplificar perturbações.
- Em 3D, não se conhece controle global da enstrofia (∫|∇×u|²) que impeça a explosão.
- Provas de existência global existem para 2D, mas não para 3D.

### Estrutura de uma possível prova
1. **Existe­ncia local**: para dados suaves, existe solução suave por algum tempo T > 0 (resultado clássico de Leray/Hopf para soluções frágeis; Kato para soluções fortes locais).
2. **Estimativas a priori**: mostrar que certas normas (ex: energia, enstrofia) permanecem limitadas para todo t.
3. **Princípio de continuação**: se a solução permanece limitada, ela pode ser estendida indefinidamente.
4. **Conclusão**: existência e suavidade globais.

Ou, para um contra-exemplo (caso B):
1. Construir dados iniciais suaves específicos.
2. Mostrar que a solução correspondente desenvolve singularidade em tempo finito T*.
3. Verificar que todas as hipóteses do problema são satisfeitas.

---

## 4. Derivação e testes numéricos (Aluno)

### Teste conceitual: equação do calor vs Navier–Stokes
A equação do calor `∂u/∂t = ν Δu` suaviza tudo e nunca explode. Adicionar o termo não linear `(u · ∇)u` introduz a possibilidade de transferência de energia para escalas menores (cascata de turbulência).

### Teste numérico simplificado (pseudo-código)
```
# Não é uma prova, apenas ilustração de instabilidade potencial
u = campo_inicial_suave()
for t in range(T_max):
    u = u + dt * (-convective(u) - grad(p) + nu * laplacian(u))
    projete_para_divergencia_zero(u)  # ∇·u = 0
    if norma_infinito(u) > limite_enorme:
        reportar_possivel_singularidade(t)
```

### Lacuna identificada pelo aluno
Simulações numéricas não são prova. Uma "explosão" numérica pode ser artefato de discretização (tamanho de passo, grade). É necessário análise analítica rigorosa.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Proposta da OpenAI (set/2026) | **REPROVADO como prova oficial** | Não foi independentemente verificada; Clay Institute exige ≥ 2 anos após publicação; OpenAI não reivindica o prêmio. |
| Existem­cia global em 2D | APROVADO | Resultado conhecido (Leray, Hopf); não resolve o caso 3D. |
| Soluções fracas de Leray–Hopf | APROVADO | Existem globalmente, mas podem não ser suaves nem únicas. |
| Suavidade para dados pequenos | APROVADO | Se ||u₀|| pequeno em certo espaço, existe solução suave global (resultado clássico). |
| Caso geral 3D, dados grandes | **EM ABERTO** | É exatamente o conteúdo do problema do milênio. |
| Uso ofensivo da matemática | REJEITADO | Este skill é puramente educacional; não se destina a modelar armas, explosões ou danos. |

**Parecer QA**: O problema permanece aberto. Qualquer afirmação de "resolução" deve ser tratada com extrema cautela até revisão por pares e verificação independente.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou estado-da-arte no Clay Math Institute e noticiário de setembro/2026 (OpenAI).
- **Professor**: Estruturou enunciado, intuição e estrutura de prova.
- **Aluno**: Derivou analogia com equação do calor e pseudocódigo numérico; identificou lacuna de simulação vs prova.
- **QA**: Contesta proposta da OpenAI, valida casos conhecidos (2D, dados pequenos), exige revisão por pares.

---

## 7. Como usar este skill

Use como referência didática sobre o Problema de Navier–Stokes. Não use como prova válida. Toda nova heurística, contra-exemplo ou atualização de status deve gerar um novo commit (`feat:` ou `fix:`) neste repositório.

**Próximo passo sugerido**: Acompanhar a revisão independente da proposta de 2026 e atualizar este skill quando houver decisão do Clay Institute.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
