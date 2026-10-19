# Fluid Simulation Space-Time Parallelism Skill

**id:** fluid-simulation-space-time  
**name:** Space-Time Methods for Parallel Fluid Simulation  
**description:** Investiga se métodos espaço-tempo (parareal, elementos finitos espaço-tempo, integração temporal paralela) podem colocar a simulação de fluidos incompressíveis em classe NC. Conteúdo esteducional e teórico.  
**author:** codingsh <codingsh@pm.me>  
**status:** aberto (pesquisa ativa)  
**derived_from:** skills/p-vs-nc-fluids-connection/skills.md  
**triggers:** "parareal", "space time", "space-time finite element", "parallel time integration", "fluid simulation nc", "parallel pde time stepping"

---

## 1. Enunciado (Professor)

Métodos espaço-tempo tratam o tempo como outra dimensão, resolvendo o sistema espaço-tempo inteiro de uma vez, em vez de passo a passo sequencialmente.

Pergunta central: Existe um método espaço-tempo para Navier–Stokes/Euler cuja complexidade paralela é polilogarítmica no tempo (ou seja, o problema está em NC)?

Métodos candidatos:
- **Parareal**: decomposição temporal com propagador grosso e fino, iteração de correção.
- **Elementos finitos espaço-tempo**: malha espaço-tempo unificada.
- **Método de múltiplos escopos temporais (multirrate)**.

---

## 2. Contexto (Pesquisador)

- Parareal (Lions, Maday, Turinici, 2001): acelera integração temporal em máquinas paralelas, mas convergência não é garantida em número polilogarítmico de iterações para problemas não lineares rígidos.
- Elementos finitos espaço-tempo: resolvem o sistema completo, mas o sistema linear resultante é enorme; solucionadores paralelos (Krylov, multigrid) aceleram, mas não provam pertencimento a NC.
- Não se conhece prova de que simulação de fluidos incompressíveis está em NC.
- Não se conhece prova de P-completude para esses métodos.

Referências sugeridas:
- Lions, J.L., Maday, Y., Turinici, G. "Résolution d'équations aux dérivées partielles par des schémas temps–espace" (2001).
- Trabalhos sobre solucionadores paralelos de EDPs (multigrid, domain decomposition).
- Greenlaw et al., "Limits to Parallel Computation" (P-completude).

---

## 3. Explicação didática (Professor)

### Intuição do Parareal
Divide o intervalo [0, T] em subintervalos. Um propagador "grosso" (barato, impreciso) dá uma estimativa inicial; um propagador "fino" (caro, preciso) refina em paralelo; iterações corrigem a solução globalmente.

### Por que ainda não provamos NC
- Para problemas não lineares (Navier–Stokes), a convergência do Parareal pode exigir número de iterações dependente de T e da não linearidade.
- Cada iteração envolve resolver sistemas grandes (espaço × tempo).
- Não há limite superior polilogarítmico conhecido no número de iterações para o caso geral.

### Estrutura de possível resultado positivo (em NC)
1. Provar que o número de iterações do Parareal é O(log^k(T)) para Navier–Stokes.
2. Mostrar que cada iteração é paralelizável em NC no espaço.
3. Concluir: simulação em NC → sugere P = NC se o problema for P-duro.

---

## 4. Derivação e testes (Aluno)

### Pseudocódigo Parareal ilustrativo (não prova)
```
for cada subintervalo [t_i, t_{i+1}] em paralelo:
    u_grosso[i] = propagador_barato(u_i, dt_grosso)
iterar:
    para cada subintervalo em paralelo:
        u_fino[i] = propagador_preciso(u_grosso[i], dt_fino)
        corrigir u_grosso com diferenca fino-grosso
    ate convergencia
```

### Lacuna do aluno
Para EDPs não lineares e rígidas (como Navier–Stokes próximo de singularidade), a convergência do Parareal pode ser lenta ou falhar. Não há garantia de complexidade polilogarítmica.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Parareal acelera simulações | APROVADO (empiricamente em muitos casos) | Não é prova de complexidade NC. |
| Elementos finitos espaço-tempo resolvem sistema completo | APROVADO | Sistema grande, solucionadores paralelos ajudam. |
| Simulação de fluidos está em NC | EM ABERTO | Não há prova conhecida. |
| Simulação de fluidos é P-completo | EM ABERTO | Não há redução conhecida. |
| Parareal tem iterações O(log^k T)? | EM ABERTO | Não demonstrado para Navier–Stokes geral. |

**Parecer QA:** Métodos espaço-tempo são promissores para aceleração prática, mas não estabelecem pertencimento a NC nem P-completude.

---

## 6. Registro de agentes

- **Pesquisador**: Parareal, elementos finitos espaço-tempo, literatura de integração temporal paralela.
- **Professor**: enunciado do problema espaço-tempo, intuição do Parareal, estrutura de resultado em NC.
- **Aluno**: pseudocódigo Parareal, identificação da lacuna de convergência para EDPs não lineares.
- **QA**: contesta claims de eficiência teórica, valida distinção entre aceleração empírica e classe de complexidade.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
