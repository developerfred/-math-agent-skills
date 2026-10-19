# BKM Criterion Parallel Complexity Skill

**id:** bkm-criterion-parallel-complexity  
**name:** Parallel Complexity of the Beale–Kato–Majda Integral  
**description:** Investiga se calcular ∫₀^T ||ω(t)||∞ dt (critério de Beale–Kato–Majda) pode ser paralelizado eficientemente (NC) ou é sequencialmente difícil (P-completo). Conteúdo esteducional e teórico.  
**author:** codingsh <codingsh@pm.me>  
**status:** aberto (conjectura de pesquisa)  
**derived_from:** skills/blow-up-criteria-bkm/skills.md, skills/p-vs-nc-fluids-connection/skills.md  
**triggers:** "beale kato majda", "bkm", "parallel complexity", "nc", "p complete", "vorticity integral", "parallel quadrature"

---

## 1. Enunciado (Professor)

Problema de decisão BKM-DECIDE:
```
Entrada: campo de velocidade u(t) amostrado em passos dt, tempo T.
Pergunta: ∫₀^T ||ω(t)||∞ dt excede um limiar K? (ou diverge à medida que dt → 0?)
```

Questão: BKM-DECIDE está em NC ou é P-completo?

O critério BKM diz que explosão de Euler/Navier–Stokes requer essa integral divergir. Se calcular essa integral paralelamente fosse eficiente (NC), poderíamos avaliar o risco de singularidade rapidamente com muitos processadores.

---

## 2. Contexto (Pesquisador)

- O cálculo de ∫||ω||∞ dt envolve:
  1. Calcular ω = ∇ × u em cada ponto da grade (paralelizável no espaço).
  2. Calcular ||ω||∞ (máximo global — redução paralela em O(log n) com processadores suficientes).
  3. Integrar no tempo (sequencial no tempo, passo a passo).
- O gargalo é a integração temporal: cada passo depende do campo de velocidade do passo anterior.
- Quadrature paralela (independente) existe para integrais estáticas, mas aqui a integranda ||ω(t)||∞ depende da evolução temporal sequencial.

Referências sugeridas:
- Beale, Kato, Majda (1984) — critério original.
- Trabalhos sobre integração temporal paralela (parareal, PFMAT, space-time methods).
- Reduções paralelas (máximo global em NC com processadores suficientes).

---

## 3. Explicação didática (Professor)

### O que é paralelizável e o que não é
- **Paralelizável no espaço:** curl, norma ∞ em cada passo (redução paralela).
- **Sequencial no tempo:** a evolução u(t_{k+1}) = F(u(t_k)) forma cadeia de dependências.
- Resultado: o custo paralelo é dominado pelo número de passos de tempo, não pelo tamanho da espaço.

### Análogo simples
Calcular ∫₀^T f(t) dt onde f(t) é dado por fórmula fechada é paralelizável (dividir intervalo). Mas se f(t) só é obtível por simulação sequencial (como ||ω(t)||∞ de Euler), a integração herda a sequência.

### Estrutura de possível resultado
1. BKM-DECIDE ∈ P (calcular passo a passo).
2. Pergunta aberta: existe algoritmo paralelo polilogarítmico em T?
3. Se não, e for P-completo → paralelização eficiente improvável.

---

## 4. Derivação e testes (Aluno)

### Pseudocódigo sequencial (ilustrativo)
```
integral = 0
for t = 0 to T step dt:
    omega = curl(u(t))
    norm_inf = max(abs(omega))  # reducao paralela no espaco (OK)
    integral += norm_inf * dt   # sequencial no tempo
    u(t+dt) = passo_euler(u(t), dt)  # dependencia temporal
return integral > K
```

### Lacuna do aluno
A atualização de u(t) é inerentemente sequencial. Mesmo que o máximo global seja paralelo, o loop temporal não pode ser paralelizado sem um método que "pule" no tempo (ex: parareal), cuja correção para Euler próximo de singularidade não está estabelecida.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| ||ω||∞ por passo em NC | APROVADO | Redução paralela em O(log n) com processadores suficientes. |
| Integração temporal ∫dt em NC | EM ABERTO | Depende de método de salto temporal não sequencial. |
| BKM-DECIDE é P-completo | EM ABERTO | Não há prova conhecida. |
| Parareal resolve o problema? | RESSALVA | Parareal acelera mas não garante complexidade polilogarítmica no pior caso. |
| Conclusão definitiva | EM ABERTO | Não afirmar P-completude nem pertencimento a NC sem prova. |

**Parecer QA:** O cálculo de cada amostra de ||ω||∞ é paralelizável, mas a integração temporal acumulada permanece sequencialmente difícil.

---

## 6. Registro de agentes

- **Pesquisador**: critério BKM, estrutura da integral, literatura de integração temporal paralela.
- **Professor**: enunciado de BKM-DECIDE, separação espaço/tempo, análogo com integral estática vs sequencial.
- **Aluno**: pseudocódigo, identificação da dependência temporal como gargalo.
- **QA**: contesta claims sobre parareal, valida o que é paralelizável (espaço) vs não (tempo).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
