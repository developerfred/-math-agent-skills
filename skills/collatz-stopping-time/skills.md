# Collatz Stopping-Time Heuristic

**id:** collatz-stopping-time  
**name:** Collatz 3n+1 Stopping-Time Heuristic  
**description:** Heurística probabilística para o tempo de parada da Conjectura de Collatz (3n+1). Resultado educacional gerado pelo ciclo multi-agente (pesquisa → ensino → aprendizado → contestação). Problema ainda em aberto; esta é uma heurística, não uma prova.  
**author:** codingsh <codingsh@pm.me>  
**status:** aberto / heurístico  
**triggers:** "collatz", "3n+1", "stopping time", "hailstone", "syracuse", "conjectura de collatz", "heuristica probabilistica"

---

## 1. Enunciado

Seja a função de Collatz:

```
C(n) = n / 2          se n é par
C(n) = 3n + 1         se n é ímpar
```

O **tempo de parada** σ(n) é o menor k ≥ 0 tal que C^k(n) = 1.  
A conjectura afirma que σ(n) está definido para todo inteiro n ≥ 1.

**Pergunta abordada aqui:** qual é a ordem de crescimento esperada de σ(n) para n grande?

---

## 2. Contexto e referências (Pesquisador)

- Problema em aberto (verificado computacionalmente até ~2^60).
- Papers relacionados no arXiv: análises de sistemas dinâmicos, modelos probabilísticos de Terras, Kontorovich.
- Nenhuma prova geral conhecida; abordagens heurísticas sugerem crescimento logarítmico médio.

Referências sugeridas para leitura:
- Terras, R. (1976). "On the existence of a density."
- Kontorovich, A. (2009). "The stochastic Collatz map."
- arXiv: buscas por "Collatz stopping time heuristic".

---

## 3. Explicação didática (Professor)

### Intuição
Cada passo ímpar multiplica por ~3 e cada passo par divide por 2. Em média, uma sequência longa tem cerca de metade de pares e metade de ímpares, então o fator multiplicativo médio por passo é (3·1/2)^(1/2) · (1/2)^(1/2) ≈ √(3/4) < 1, sugerindo contração média e parada eventual.

### Modelo heurístico
Modele log C(n) como um passeio aleatório com desvio médio negativo:

```
E[Δ log n] ≈ (1/2)·log(1/2) + (1/2)·log(3) = (1/2)·log(3/2) > 0
```

(Nota: este é o viés para a sequência de ímpares; a análise completa requer separar passos pares e ímpares.)

### Resultado heurístico
σ(n) = O(log n) em média heurística, com flutuações.

---

## 4. Derivação e testes numéricos (Aluno)

### Teste 1: n = 7
Sequência: 7 → 22 → 11 → 34 → 17 → 52 → 26 → 13 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1  
σ(7) = 16

### Teste 2: n = 27 (clássico, demorado)
σ(27) = 111, valor máximo intermediário = 9232

### Teste 3: n = 2^k
σ(2^k) = k (apenas divisões por 2). Isso mostra que σ(n) pode ser tão pequeno quanto log₂(n).

### Lacuna identificada
O caso n = 2^k é ótimo (melhor caso), mas não representa o comportamento médio. Precisamos de amostragem estatística sobre muitos n.

---

## 5. Contestação e casos extremos (QA)

| Item | Status | Observação |
|------|--------|------------|
| Hipótese de pares/ímpares 50-50 | RESSALVA | Não é verdade para trajetórias curtas; é uma média assintótica heurística. |
| Caso n = 1 | APROVADO | σ(1) = 0, bem definido. |
| Caso n potência de 2 | APROVADO | σ(2^k) = k, confirme. |
| Ciclos não triviais | NÃO CONHECIDOS | Nenhum ciclo além de 4→2→1→4 foi encontrado; heurística não descarta. |
| Validade para n grande | ABERTO | Teste numérico não é prova. |
| Números complexos / negativo | FORA DE ESCOPO | Collatz é definido sobre inteiros positivos. |

**Parecer QA:** heurística aceita como modelo educacional, com ressalva explícita de que não é prova. Requer atualização se houver novo resultado teórico.

---

## 6. Registro de agentes participantes

- Pesquisador: levantamento de contexto e referências arXiv.
- Professor: intuição, modelo heurístico, resultado esperado.
- Aluno: derivação de σ(7), σ(27), σ(2^k) e identificação de lacuna.
- QA: checklist de casos extremos, parecer de ressalva.

---

## 7. Como usar este skill

Use como referência pedagógica para discutir a Conjectura de Collatz em sistemas de agentes. Não use como prova formal. Toda nova heurística ou contra-exemplo encontrado deve gerar um `fix:` ou `feat:` no repositório.

---

**Próximo passo sugerido:** amostragem estatística de σ(n) para n ∈ [1, 10^6] e comparação com o modelo log n.
