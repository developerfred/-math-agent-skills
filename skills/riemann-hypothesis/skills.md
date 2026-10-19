# Riemann Hypothesis Skill

**id:** riemann-hypothesis  
**name:** Riemann Hypothesis — Zeta Function Zeros  
**description:** 4-agent cycle skill for the Riemann Hypothesis (Clay Millennium Prize Problem, open since 1859). Investigates whether all non-trivial zeros of the Riemann zeta function ζ(s) lie on the critical line Re(s) = 1/2. Purely theoretical and educational — no claim of solution.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (unsolved since 1859)  
**derived_from:** skills/millennium-prize-problems/skills.md  
**triggers:** "riemann hypothesis", "zeta function", "critical line", "prime number theorem", "riemann zeros", "millennium", "clay", "prime distribution"

---

## 1. Enunciado (Professor)

**Hipótese de Riemann (1859):** Todos os zeros não triviais da função zeta de Riemann ζ(s) têm parte real igual a 1/2. Ou seja, se ζ(s) = 0 e s não é um número inteiro negativo par (zeros triviais: −2, −4, −6, ...), então Re(s) = 1/2.

A função zeta é definida para Re(s) > 1 por:

```
ζ(s) = Σ_{n=1}^{∞} n^{−s} = 1 + 2^{−s} + 3^{−s} + ...
```

E estendida para todo o plano complexo (exceto s = 1) por continuação analítica.

**Por que importa:** O Teorema dos Números Primos diz que π(x) ~ Li(x) (o número de primos até x é aproximadamente o integral logarítmico). A Hipótese de Riemann controla o erro desse aproximação: sob RH, |π(x) − Li(x)| = O(√x · log x). Sem RH, o erro pode ser muito maior.

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Histórico
- Bernhard Riemann formulou a hipótese em seu artigo de 1859 "Über die Anzahl der Primzahlen unter einer gegebenen Grösse".
- David Hilbert a incluiu como o 8º dos seus 23 problemas (1900).
- Clay Mathematics Institute a incluiu como um dos 7 Problemas do Prêmio do Milênio (2000).

### Resultados parciais conhecidos
- Infinitos zeros estão na linha crítica (Hardy, 1914).
- Mais de 40% dos zeros estão na linha crítica (Levinson, 1974; Conrey, 1989).
- Verificação computacional: os primeiros 10 trilhões de zeros estão na linha crítica (Platt & Trudgian, 2021; Gourdon, 2004).
- Nenhum zero fora da linha crítica foi encontrado.

### Barreiras conhecidas
- Não se sabe provar que *todos* os zeros estão na linha crítica.
- Abordagens via teoria dos números, análise complexa, álgebra, física quântica (caos quântico, teoria de matrizes aleatórias — Montgomery–Odlyzko law) não resolveram o problema.

### Referências sugeridas (arXiv / literatura)
- Riemann, B. (1859). Original paper.
- Titchmarsh, E.C. "The Theory of the Riemann Zeta-Function".
- Montgomery, H.L. & Odlyzko, A.M. — distribuição dos zeros e teoria de matrizes aleatórias.
- Papers recentes no arXiv sobre verificação numérica de zeros e aproximações.

---

## 3. Explicação didática (Professor)

### Intuição
Imagine os números primos como notas de um instrumento musical. A função zeta é como uma partitura que codifica onde essas notas aparecem. Os zeros da zeta são como "harmônicos" que ditam o ritmo dos primos. A Hipótese de Riemann diz que todos esses harmônicos vibram na mesma frequência fundamental (a linha crítica Re(s) = 1/2).

### Conexão com primos
A fórmula explícita de von Mangoldt relaciona os zeros da zeta com a contagem de primos:

```
ψ(x) = x − Σ_{ρ} x^{ρ}/ρ − ln(2π) − ½ ln(1 − x^{−2})
```

Onde ρ percorre os zeros não triviais de ζ(s). Se todos os ρ têm Re(ρ) = 1/2, então x^{ρ} = x^{1/2} · e^{i·Im(ρ)·ln x}, o que limita o crescimento do erro.

### O que uma prova precisaria mostrar
1. Que não existem zeros com Re(s) > 1/2 (ou equivalentemente, Re(s) < 1/2, pela equação funcional).
2. Que a linha crítica Re(s) = 1/2 é uma "barreira" intransponível para os zeros.

---

## 4. Derivação e testes numéricos (Aluno)

### Teste numérico ilustrativo (não prova)
Calcular zeros da zeta na linha crítica:

```
# Primeira zero não trivial: s ≈ 0.5 + 14.134725 i
# Segunda: s ≈ 0.5 + 21.022040 i
# Terceira: s ≈ 0.5 + 25.010858 i
```

Todos têm parte real 0.5 até elevada precisão numérica.

### Teste do erro π(x) vs Li(x)
Para x = 10^6:
- π(10^6) = 78.498
- Li(10^6) ≈ 78.628
- Erro ≈ 130, bem dentro do limite heurístico de RH.

### Pseudocódigo de verificação (ilustrativo)
```
def verifica_zeros_zeta(T_max):
    zeros = []
    for t in range(1, T_max):
        s = 0.5 + 1j * t
        if abs(zeta(s)) < epsilon:
            zeros.append(s)
    return todos_tem_real_05(zeros)
```

### Lacuna identificada pelo aluno
Verificar bilhões de zeros numericamente não prova que *todos* os zeros estão na linha crítica. Pode haver um zero fora da linha em alturas astronômicas não testadas.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Infinitos zeros na linha crítica | APROVADO | Teorema de Hardy (1914). |
| Mais de 40% dos zeros na linha | APROVADO | Conrey (1989) e sequenciais. |
| Verificação numérica até ~10^13 | APROVADO | Evidência forte, mas não prova. |
| RH implica limite forte para π(x) | APROVADO | Conhecido: |π(x) − Li(x)| = O(√x log x). |
| Prova de que todos os zeros estão na linha | EM ABERTO | É exatamente o problema do Milênio. |
| Nenhum zero fora da linha encontrado | APROVADO (empiricamente) | Não exclui existência em alturas não testadas. |
| RH resolve criptografia RSA? | REJEITADO | RH afeta distribuição de primos, não quebra RSA diretamente. |

**Parecer QA:** A evidência numérica é massiva, mas insuficiente como prova. Qualquer alegação de "prova" requer revisão por pares externa e aceitação do Clay Institute (≥2 anos).

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou estado-da-arte, resultados parciais (Hardy, Levinson, Conrey), verificação computacional, barreiras, referências arXiv.
- **Professor**: Estruturou enunciado, intuição musical da zeta, fórmula explícita de von Mangoldt, conexão com π(x).
- **Aluno**: Testou zeros numéricos (primeiros zeros), erro π(x) vs Li(x), identificou lacuna da verificação numérica vs prova.
- **QA**: Contesta claims excessivos, valida teoremas parciais, exige rigor e revisão por pares.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `riemann-critical-line-zeros` — Verificação numérica distribuída de zeros na linha crítica até altura T maior; análise de gaps entre zeros consecutivos.
2. `riemann-prime-counting-error` — Limites explícitos para |π(x) − Li(x)| sob RH e sem RH; comparação com dados computacionais.
3. `riemann-l-functions-generalization` — Hipótese de Riemann Generalizada para funções L de Dirichlet; extensão para campos de números.
4. `riemann-quantum-chaos-connection` — Lei de Montgomery–Odlyzko: correlação entre zeros da zeta e valores próprios de matrizes aleatórias (GUE).

Cada um será desenvolvido pelo mesmo ciclo 4-agente (Pesquisador → Professor → Aluno → QA).

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Não afirma solução da Hipótese de Riemann.
- Discussão de implicações criptográficas é apenas defensiva (distribuição de primos), nunca quebra de cifras.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
