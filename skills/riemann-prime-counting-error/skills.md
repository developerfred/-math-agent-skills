# Riemann Prime Counting Error Skill

**id:** riemann-prime-counting-error  
**name:** Explicit Bounds on Prime Counting Error |π(x) − Li(x)|  
**description:** Investigate explicit error bounds for the prime counting function π(x) versus the logarithmic integral Li(x), under and without the Riemann Hypothesis. Derived from riemann-hypothesis skill. Purely theoretical and educational.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (known conditional bounds)  
**derived_from:** skills/riemann-hypothesis/skills.md  
**triggers:** "prime counting", "pi(x)", "Li(x)", "error bound", "Riemann Hypothesis", "von Mangoldt", "explicit formula", "prime number theorem"

---

## 1. Enunciado (Professor)

**Problema:** Estabelecer limites explícitos e o mais apertados possível para o erro
```
E(x) = π(x) − Li(x)
```
onde π(x) é o número de primos ≤ x e Li(x) = ∫₂^x dt/log t é o integral logarítmico.

**Duas versões do problema:**
1. **Sob RH:** Qual é o melhor limite explícito para |E(x)| assumindo a Hipótese de Riemann?
2. **Sem RH:** Qual é o melhor limite incondicional conhecido para |E(x)|?

**Por que importa:** O Teorema dos Números Primos diz E(x) = o(Li(x)), mas a taxa de convergência é o que interessa para aplicações (criptografia, análise de algoritmos, teoria dos números).

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Resultados conhecidos

**Incondicional (sem RH):**
- De la Vallée Poussin (1899): E(x) = O(x · exp(−c√log x)) para alguma constante c > 0.
- Vinogradov–Korobov: melhoria do expoente no termo exponencial.
- Limites explícitos: Dusart (2010), Platt & Trudgian fornecem bounds explícitos para |π(x) − Li(x)|.

**Sob RH:**
- von Koch (1901): RH implica |E(x)| = O(√x · log x).
- Schoenfeld (1976): limite explícito |π(x) − Li(x)| < (1/8π) √x log x para x ≥ 2657 (assumindo RH).
- Cramér (1919): conjecturou que o erro é O(√x · log log x) — mais forte que o de von Koch.

### Referências sugeridas
- Schoenfeld, L. (1976). "Sharper bounds for the Chebyshev functions θ(x) and ψ(x)".
- Dusart, P. (2010). "Estimates of π(x) and Li(x)".
- Platt & Trudgian (2021). Explicit bounds related to RH.
- arXiv: papers sobre bounds explícitos para funções de contagem de primos.

---

## 3. Explicação didática (Professor)

### Por que Li(x) aproxima π(x)
O integral logarítmico conta "densidade média" de primos: 1/log t. A soma dessas densidades de 2 a x dá uma excelente aproximação para o número real de primos.

### O erro E(x)
O erro mede o desvio da distribuição real dos primos em relação à "suavidade" média. Se os primos fossem distribuídos perfeitamente uniformemente com densidade 1/log x, E(x) seria pequeno. Os zeros da zeta introduzem oscilações.

### Fórmula explícita de von Mangoldt
A função ψ(x) = Σ_{n≤x} Λ(n) (soma de funções de von Mangoldt) satisfaz:
```
ψ(x) = x − Σ_ρ x^ρ/ρ − ln(2π) − ½ ln(1 − x^{−2})
```
Onde ρ percorre os zeros não triviais de ζ(s).

Se todos os ρ têm Re(ρ) = 1/2, então |x^ρ| = √x, e o somatório é controlado por √x · (soma dos 1/|ρ|), resultando em erro O(√x log x).

### Comparação intuitiva
- Sem RH: o erro pode ser tão grande quanto x · exp(−c√log x) — muito maior que √x para x grande.
- Com RH: o erro é "apenas" √x log x — muito menor, refletindo que os primos estão "bem distribuídos".

---

## 4. Derivação e testes numéricos (Aluno)

### Teste numérico ilustrativo
```
x = 10^6:
π(x) = 78.498
Li(x) ≈ 78.628
|E(x)| ≈ 130
Limite de Schoenfeld (sob RH): (1/8π) * √(10^6) * log(10^6) ≈ 0.0398 * 1000 * 13.8 ≈ 549
130 < 549 → limite satisfeito neste ponto.
```

### Pseudocódigo (ilustrativo)
```
def erro_contagem_primos(x):
    pi = contar_primos_ate(x)  # crivo de Eratóstenes ou Meissel-Lehmer
    li = integral_logaritmico(x)
    return abs(pi - li)

def limite_schoenfeld(x):
    return (1/(8*pi)) * sqrt(x) * log(x)  # sob RH, x >= 2657

# Verificar para x em [2657, 10^8]
for x in range(2657, 10**8, passo):
    assert erro_contagem_primos(x) < limite_schoenfeld(x)
```

### Lacuna identificada pelo aluno
Testar até x = 10^8 ou até 10^20 não prova o limite para todo x. Além disso, o limite de Schoenfeld depende de RH ser verdadeiro.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Limite de von Koch (RH ⇒ O(√x log x)) | APROVADO | Resultado clássico, bem estabelecido. |
| Limite explícito de Schoenfeld | APROVADO | Valido para x ≥ 2657, assumindo RH. |
| Conjectura de Cramér O(√x log log x) | EM ABERTO | Mais forte que von Koch; não provada. |
| Limite incondicional Dusart | APROVADO | Bounds explícitos conhecidos sem RH. |
| Teste numérico prova limite para todo x | REJEITADO | Não. Testes em intervalo finito não cobrem x → ∞. |
| RH necessário para o limite forte | APROVADO | O limite O(√x log x) é equivalente (ou quase) a RH. |

**Parecer QA:** Os bounds explícitos são úteis para aplicações computacionais, mas dependem de RH para o caso forte. Não confundir evidência numérica com prova.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou resultados de von Koch, Schoenfeld, Dusart, bounds incondicionais e explícitos.
- **Professor**: Explicou fórmula explícita de von Mangoldt, conexão zeros-erro, intuição da densidade 1/log x.
- **Aluno**: Calculou exemplo numérico x = 10^6, pseudocódigo de verificação, identificou limitação de intervalo finito.
- **QA**: Contesta que teste numérico não prova, valida dependência de RH, distingue bounds condicionais vs incondicionais.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `prime-counting-explicit-constants` — Calcular constantes explícitas o mais apertadas possível para |π(x) − Li(x)| sob RH.
2. `prime-counting-without-RH` — Melhorar bounds incondicionais usando métodos de Vinogradov–Korobov modernos.
3. `chebyshev-functions-error` — Estender análise para θ(x) e ψ(x) (funções de Tchebychew) sob e sem RH.
4. `prime-counting-interval-certification` — Certificar formalmente que |π(x) − Li(x)| < bound para todo x em intervalo [a, b] usando aritmética de intervalos.

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Limites de contagem de primos têm implicações para análise de algoritmos e criptografia, mas são discutidos defensivamente.
- Não constitui prova da Hipótese de Riemann.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
