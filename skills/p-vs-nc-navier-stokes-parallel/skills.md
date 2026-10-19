# P vs NC — Navier–Stokes Parallel Decision Problem Skill

**id:** p-vs-nc-navier-stokes-parallel  
**name:** Is the Navier–Stokes Decision Problem P-Complete?  
**description:** Investiga se o problema de decisão para equações de Navier–Stokes (excede limiar de velocidade em tempo T?) é P-completo ou está em NC. Conteúdo esteducional e teórico.  
**author:** codingsh <codingsh@pm.me>  
**status:** aberto (conjectura de pesquisa)  
**derived_from:** skills/p-vs-nc-fluids-connection/skills.md  
**triggers:** "navier stokes p complete", "p vs nc", "navier stokes decision problem", "parallel pde solver", "p complete pde"

---

## 1. Enunciado (Professor)

Problema de decisão NS-DECIDE:
```
Entrada: condições iniciais u₀ (discretizadas), tempo T, limiar C.
Pergunta: Existe t ∈ [0, T] tal que ||u(t)||_∞ > C?
```

Questão: NS-DECIDE é P-completo? Ou está em NC?

Se NS-DECIDE for P-completo, então a menos que P = NC, não existe algoritmo paralelo polilogarítmico para decidir se a solução de Navier–Stokes excede um limiar — implicando limite fundamental à paralelização de simulações de fluidos.

---

## 2. Contexto (Pesquisador)

- Problemas P-completos conhecidos: Circuit Value Problem (CVP), Programação Linear (com certas formulações), Busca em Profundidade em grafo (DFS).
- Não se conhece redução de CVP para NS-DECIDE.
- Métodos paralelos para EDPs (multigrid, domain decomposition, Krylov) aceleram cada passo de tempo, mas não removem a dependência sequencial no tempo.
- Pesquisa sobre "parareal" e métodos espaço-tempo tenta quebrar essa dependência, sem resultado de complexidade definitiva.

Referências sugeridas:
- Greenlaw et al., "Limits to Parallel Computation: P-completeness Theory"
- Circuit Value Problem como problema P-completo canônico
- Literatura sobre parareal e integração temporal paralela

---

## 3. Explicação didática (Professor)

### Por que CVP é P-completo
O Circuit Value Problem avalia um circuito booleano dado entradas fixas. A avaliação é inerentemente sequencial (portas dependem da saída de outras). Qualquer problema que possa ser reduzido a CVP herda essa dificuldade de paralelização.

### Analogia com Navier–Stokes
Cada passo de tempo de Navier–Stokes depende do passo anterior (a evolução temporal é causal). Isso lembra a avaliação sequencial de circuitos. Se essa dependência causal é inerente (não apenas artefato do método numérico), NS-DECIDE tende a ser P-completo.

### Estrutura de uma possível prova de P-completude
1. Mostrar que NS-DECIDE ∈ P (simulação sequencial polinomial).
2. Construir redução logarítmica de CVP para NS-DECIDE: codificar portas booleanas em campos de velocidade de modo que a evolução de Navier–Stokes simule a avaliação do circuito.
3. Concluir: NS-DECIDE é P-completo.

---

## 4. Derivação e testes (Aluno)

### Teste conceitual: equação de advecção linear
Considere `∂u/∂t + c·∇u = 0`. A solução em tempo T é apenas o perfil inicial deslocado por cT. Isso é paralelizável (cada ponto independente). Mas Navier–Stokes não é linear; o termo não linear (u · ∇)u acopla todos os pontos.

### Pseudocódigo de redução ilustrativa (não prova)
```
# Tentativa: codificar porta AND em interação de dois vórtices
# Se u1 e u2 colidem -> u_saida > limiar (saída TRUE)
# Caso contrario -> u_saida <= limiar (saída FALSE)
```

### Lacuna do aluno
Não se sabe como codificar arbitrariamente portas booleanas em campos de fluido contínuo preservando as equações de Navier–Stokes. É um grande obstáculo técnico para qualquer prova de P-completude.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| NS-DECIDE ∈ P | APROVADO (discretização fixa) | Simulação numérica é polinomial. |
| NS-DECIDE é P-completo | EM ABERTO | Não há redução conhecida de CVP. |
| P = NC implicaria paralelos eficientes para fluidos | APROVADO (teórico) | Mas P = NC é aberto. |
| Métodos paralelos existentes provam NC | REJEITADO | Aceleram passos, não removem sequência temporal. |
| Prova de P-completude seria fácil | REJEITADO | Requer codificar computação booleana em fluidos contínuo; dificuldade aberta. |

**Parecer QA:** O problema é aberto. Qualquer redução de CVP para Navier–Stokes seria um resultado de destaque em complexidade computacional.

---

## 6. Registro de agentes

- **Pesquisador**: definição de P-completude, CVP, literatura de paralelismo de EDPs.
- **Professor**: enunciado de NS-DECIDE, analogia circuito–fluido, estrutura de prova.
- **Aluno**: teste com equação de advecção, pseudocódigo de redução, identificação da lacuna de codificação booleana.
- **QA**: contesta claims, valida escopo das classes de complexidade.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
