# Riemann Critical Line Zeros Skill

**id:** riemann-critical-line-zeros  
**name:** Numerical Verification of Zeros on the Critical Line  
**description:** Distributed numerical verification of Riemann zeta zeros on Re(s) = 1/2 up to large height T; analysis of gaps between consecutive zeros. Derived from riemann-hypothesis skill. Purely theoretical and educational.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (computational evidence only)  
**derived_from:** skills/riemann-hypothesis/skills.md  
**triggers:** "riemann zeros", "critical line", "zeta zeros", "numerical verification", "zero gaps", "montgomery odlyzko", "Turing method", "Riemann-Siegel"

---

## 1. Enunciado (Professor)

**Problema:** Verificar numericamente que todos os zeros não triviais de ζ(s) com |Im(s)| ≤ T estão na linha crítica Re(s) = 1/2, para T cada vez maior, e analisar a distribuição dos gaps (espaçamentos) entre zeros consecutivos na linha crítica.

O método padrão é o **método de Turing** (ou argumento do princípio do argumento), que conta zeros em retângulos do plano complexo usando a variação do argumento de ζ(s) ao longo do contorno.

**Perguntas centrais:**
1. Até que altura T podemos verificar computacionalmente que todos os zeros estão na linha crítica?
2. Os gaps entre zeros consecutivos seguem a previsão da teoria de matrizes aleatórias (GUE)?

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Histórico computacional
- Gourdon (2004): verificação dos primeiros 10 trilhões de zeros (T ≈ 10^12).
- Platt & Trudgian (2021): verificação até T ≈ 3 × 10^12.
- Xavier Gourdon e Patrick Demichel: projetos distribuídos de verificação de zeros.

### Métodos numéricos
- **Fórmula de Riemann-Siegel:** cálculo eficiente de ζ(1/2 + it) para t grande, com complexidade O(√t) por avaliação.
- **Método de Turing:** contagem de zeros em intervalos via variação do argumento; detecta se algum zero "escapou" da linha crítica.
- **Verificação de Gram points:** pontos onde ζ(1/2 + it) é real; usados para localizar zeros entre Gram points.

### Análise de gaps
- Montgomery (1973): conjectura de correlação de pares de zeros (pair correlation conjecture).
- Odlyzko (1987): evidência numérica forte de que os gaps seguem a estatística da Unitary Ensemble (GUE) de matrizes aleatórias.

### Referências sugeridas
- Gourdon, X. (2004). "The 10^13 first zeros of the Riemann Zeta function".
- Platt, D. & Trudgian, T. (2021). "The Riemann hypothesis is true up to 3·10^12".
- Odlyzko, A.M. (1987). "On the distribution of spacings between zeros of the zeta function".
- arXiv: papers sobre verificação distribuída de zeros da zeta.

---

## 3. Explicação didática (Professor)

### Por que verificar zeros importa
Cada zero ρ = β + iγ contribui para o termo x^ρ/ρ na fórmula explícita de von Mangoldt. Se algum zero tiver β ≠ 1/2, o termo de erro na contagem de primos cresce mais rápido do que √x log x.

### O método de Riemann-Siegel em palavras
Para t grande, calculamos ζ(1/2 + it) usando uma soma finita de termos até √(t/2π), mais um termo de correção. Isso permite avaliar a função zeta em milhões de pontos da linha crítica de forma eficiente.

### Contagem de zeros com o método de Turing
1. Percorra um contorno retangular no plano complexo.
2. Calcule a variação contínua do argumento de ζ(s) ao longo do contorno.
3. Pelo princípio do argumento, o número de zeros dentro do retângulo é (variação do argumento)/(2π).
4. Se o número de zeros encontrados na linha crítica é igual ao número total no retângulo, não há zeros fora da linha naquela região.

### Gaps entre zeros
Se normalizarmos os gaps pela densidade média local (que é ~ (1/2π) log t), a distribuição normalizada dos gaps deve coincidir com a distribuição de espaçamento de eigenvalores de matrizes hermitianas aleatórias (GUE).

---

## 4. Derivação e testes numéricos (Aluno)

### Teste numérico ilustrativo (não prova)
```
# Verificar primeiros 10 zeros na linha crítica
zeros = [14.134725, 21.022040, 25.010858, 30.424876, 32.935062,
         37.586178, 40.918719, 43.327073, 48.005151, 49.773832]
# Todos têm parte real 0.5 com precisão machine epsilon
```

### Análise de gaps
Para zeros consecutivos γ_n e γ_{n+1}, o gap normalizado é:
```
δ_n = (γ_{n+1} − γ_n) * (log(γ_n) / 2π)
```
A distribuição de δ_n deve coincidir com a distribuição de Wigner surmise para GUE:
```
P(s) = (32/π²) s² exp(−4s²/π)
```

### Pseudocódigo (ilustrativo)
```
def verifica_zeros_ate(T_max):
    zeros_encontrados = []
    t = 14.134725  # primeiro zero
    while t < T_max:
        # Encontrar próximo zero via busca de mudança de sinal de Z(t)
        t_proximo = proximo_zero_zeta(t)
        zeros_encontrados.append(t_proximo)
        t = t_proximo
    return todos_na_linha_critica(zeros_encontrados)

def analisa_gaps(zeros):
    gaps = []
    for i in range(len(zeros)-1):
        gap_raw = zeros[i+1] - zeros[i]
        gap_norm = gap_raw * (log(zeros[i]) / (2*pi))
        gaps.append(gap_norm)
    return comparar_com_GUE(gaps)
```

### Lacuna identificada pelo aluno
Verificação até T = 10^13 é imensa, mas o domínio de s é infinito. Não há como verificar todos os zeros numericamente; é necessário um argumento analítico para cobrir T → ∞.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Verificação até 10^13 zeros | APROVADO | Evidência computacional massiva, reproduzida independentemente. |
| Método de Riemann-Siegel | APROVADO | Algoritmo padrão, complexidade O(√t) por avaliação. |
| Método de Turing para contagem | APROVADO | Detecta zeros fora da linha crítica em intervalos verificados. |
| Gaps seguem GUE | APROVADO (empiricamente) | Odlyzko e outros confirmaram numericamente. |
| Verificação numérica prova RH? | REJEITADO | Não. Domínio é infinito; zero pode existir em T não testado. |
| "Todos os zeros estão na linha" | EM ABERTO | É o conteúdo da Hipótese de Riemann. |

**Parecer QA:** A verificação numérica é uma ferramenta valiosa para gerar conjecturas e detectar contra-exemplos, mas não substitui prova analítica.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou estado-da-arte computacional (Gourdon, Platt-Trudgian), métodos (Riemann-Siegel, Turing), análise de gaps (Montgomery-Odlyzko).
- **Professor**: Estruturou enunciado, explicou método de contagem de zeros, intuição da fórmula explícita, distribuição de gaps.
- **Aluno**: Derivou fórmula de gap normalizado, pseudocódigo de verificação, identificou limitação T → ∞.
- **QA**: Contesta que prova numérica ≠ prova analítica, valida métodos, exige distinção clara entre evidência e demonstração.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `critical-line-zeros-distributed-computing` — Verificação distribuída de zeros até T > 10^13 usando rede de voluntários (estilo GIMPS).
2. `zero-gap-statistics-large-height` — Análise de gaps de zeros em alturas muito grandes (T > 10^20) via aproximações assintóticas.
3. `turing-method-interval-certification` — Certificação formal de intervalos livres de zeros fora da linha crítica usando aritmética de intervalos.
4. `gaps-deviation-GUE` — Quantificar desvios estatísticos dos gaps em relação à previsão GUE; testar hipótese de correlação de pares.

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Verificação numérica de zeros não constitui prova da Hipótese de Riemann.
- Não implica quebra de criptografia (RSA depende da dificuldade de fatoração, não diretamente da localização exata dos zeros).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
