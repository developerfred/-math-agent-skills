# Birch–Swinnerton-Dyer Conjecture Skill

**id:** birch-swinnerton-dyer  
**name:** Birch–Swinnerton-Dyer Conjecture — Clay Millennium Prize Problem  
**description:** 4-agent cycle skill for the Birch–Swinnerton-Dyer Conjecture (open since 1960s/2000). Investigates whether the rank of the group of rational points on an elliptic curve equals the order of vanishing of its L-function at s = 1. Purely theoretical and educational — no claim of solution.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (unsolved since 1960s)  
**derived_from:** skills/millennium-prize-problems/skills.md  
**triggers:** "Birch Swinnerton Dyer", "BSD", "elliptic curve", "L-function", "rank", "rational points", "Diophantine", "millennium", "clay", "congruent number"

---

## 1. Enunciado (Professor)

**Conjectura de Birch–Swinnerton-Dyer (BSD):** Seja E uma curva elíptica sobre ℚ. Então o posto (rank) do grupo de pontos racionais E(ℚ) é igual à ordem de anulação da função L associada L(E, s) em s = 1.

Em outras palavras:
```
rank(E(ℚ)) = ord_{s=1} L(E, s)
```

Além disso, o coeficiente líder da expansão de Taylor de L(E, s) em s = 1 é dado por uma fórmula explícita (fórmula de BSD) envolvendo o regulador, números de Tamagawa, o grupo de Tate–Shafarevich X(E), e o período real da curva.

**Por que importa:** Conecta objetos aritméticos (pontos racionais em curvas elípticas, usados em criptografia de curva elíptica) com objetos analíticos (funções L, zeros e polos). A conjectura é central na teoria dos números moderna.

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Histórico
- Birch e Swinnerton-Dyer formularam a conjectura na década de 1960 com base em computações numéricas na EDSAC (computador da Universidade de Cambridge).
- Wiles (1995) provou o Último Teorema de Fermat usando curvas elípticas e formas modulares — conexão indireta com BSD.
- Clay Mathematics Institute incluiu BSD como Problema do Prêmio do Milênio (2000).

### Resultados conhecidos
- **Coates–Wiles (1977):** Se L(E, 1) ≠ 0, então E(ℚ) tem posto 0 (finito).
- **Gross–Zagier (1986) e Kolyvagin (1990):** Se L(E, s) tem uma zero simples em s = 1 (ordem de anulação 1), então o posto é 1 e X(E) é finito.
- **Casos conhecidos:** A conjectura é verdadeira para curvas com posto 0 ou 1 (sob condições técnicas), e para certas famílias de curvas.
- **Casos abertos:** Posto ≥ 2 é amplamente aberto; não se conhece prova geral para nenhuma curva de posto ≥ 2.

### Referências sugeridas
- Birch, B.J. & Swinnerton-Dyer, H.P.F. (1960s). "Notes on elliptic curves I, II".
- Coates, J.H. & Wiles, A.W. (1977). "On the conjecture of Birch and Swinnerton-Dyer".
- Gross, B.H. & Zagier, D.B. (1986). "Heegner points and derivatives of L-series".
- Kolyvagin, V.A. (1990). "Euler systems".
- arXiv: papers sobre curvas elípticas, função L, BSD.

---

## 3. Explicação didática (Professor)

### Intuição
Uma curva elíptica é definida por uma equação do tipo y² = x³ + ax + b. Os pontos racionais na curva (x, y ∈ ℚ) formam um grupo abeliano. Por um teorema de Mordell–Weil, este grupo é finitamente gerado:
```
E(ℚ) ≅ ℤ^r ⊕ E(ℚ)_tors
```
Onde r é o posto (rank) e E(ℚ)_tors é o grupo de torção (finito).

A conjectura de BSD diz que este posto r (quão "grande" é o grupo de pontos racionais) é determinado pelo comportamento da função L(E, s) perto de s = 1. Quanto maior o posto, mais rápido L(E, s) se anula em s = 1.

### A função L de uma curva elíptica
Para cada primo p, definimos um fator local a_p dependendo do número de pontos da curva módulo p. Então:
```
L(E, s) = ∏_p (1 − a_p p^{−s} + p^{1−2s})^{−1}
```
(Para bons primos; primos ruins têm fatores modificados.)

### Fórmula de BSD (coeficiente líder)
```
lim_{s→1} L(E, s) / (s − 1)^r = (Ω · Reg · ∏ c_p · |X(E)|) / |E(ℚ)_tors|²
```
Onde Ω é o período real, Reg o regulador, c_p os números de Tamagawa, X(E) o grupo de Tate–Shafarevich.

---

## 4. Derivação e testes numéricos (Aluno)

### Exemplo ilustrativo: curva congruente
A curva y² = x³ − n²x está relacionada ao problema dos números congruentes (qual número inteiro n é área de um triângulo retângulo com lados racionais?).

Para n = 5, a curva y² = x³ − 25x tem posto 1 (existe ponto racional de ordem infinita, ex: (−4, 6)). A função L(E, s) tem uma zero simples em s = 1. Isso é consistente com BSD.

### Pseudocódigo (ilustrativo)
```
def posto_curva_elíptica(E):
    # Calcular posto via descent ou Heegner points (casos especiais)
    pass

def ordem_anulacao_L(E, s0=1):
    # Expandir L(E, s) em série de Taylor em s0
    # Retornar a ordem do primeiro coeficiente não-nulo
    pass

# Verificar BSD para curvas de posto 0 e 1
for E em curvas_de_posto_0_ou_1:
    assert posto_curva_elíptica(E) == ordem_anulacao_L(E)
```

### Lacuna identificada pelo aluno
Para curvas de posto ≥ 2, não se conhece algoritmo geral para calcular o posto nem provar BSD. A verificação numérica é possível para curvas específicas, mas não é prova geral.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Coates–Wiles: L(E,1) ≠ 0 ⇒ posto 0 | APROVADO | Resultado clássico. |
| Gross–Zagier–Kolyvagin: ordem 1 ⇒ posto 1 | APROVADO | Resultado profundo, condições técnicas. |
| BSD para posto ≥ 2 | EM ABERTO | Amplamente aberto; sem prova geral. |
| Verificação numérica prova BSD? | REJEITADO | Não. É evidência para curvas específicas. |
| BSD quebra criptografia de curva elíptica? | REJEITADO | BSD é sobre estrutura de pontos racionais, não sobre dificuldade do problema do logaritmo discreto em curvas elípticas. |

**Parecer QA:** BSD é uma das conjecturas mais profundas da teoria dos números. Não afirmar solução sem prova geral e revisão por pares.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou história (Birch–Swinnerton-Dyer 1960s), Coates–Wiles, Gross–Zagier, Kolyvagin, referências clássicas e arXiv.
- **Professor**: Explicou grupo de pontos racionais, posto, teorema de Mordell–Weil, função L de curva elíptica, fórmula de BSD.
- **Aluno**: Testou curva congruente n=5, pseudocódigo de posto e ordem de anulação, identificou limitação para posto ≥ 2.
- **QA**: Contesta que casos posto 0/1 não provam geral, valida distinção entre criptografia e BSD, exige prova geral.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `bsd-elliptic-curve-rank` — Cálculo de posto para curvas elípticas específicas (descent, pontos de Heegner) e verificação numérica de BSD.
2. `bsd-l-function-vanishing` — Estudo da ordem de anulação de L(E, s) em s = 1 para famílias de curvas.
3. `bsd-tate-shafarevich-group` — Investigação do grupo de Tate–Shafarevich X(E): finitude, tamanho, conexão com BSD.
4. `bsd-congruent-number-problem` — Conexão entre BSD e o problema dos números congruentes (qual inteiro n é área de triângulo retângulo racional?).

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Curvas elípticas são usadas em criptografia (ECC), mas BSD é discutida como teoria dos números, não como ataque a cifras.
- Não constitui prova da Conjectura de Birch–Swinnerton-Dyer.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
