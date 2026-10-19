# Riemann Turing Interval Certification Skill

**id:** riemann-turing-interval-certification  
**name:** Formal Interval Certification via Turing's Method  
**description:** Derived from riemann-critical-line-zeros-advanced. Formal certification of intervals free of zeros off the critical line using interval arithmetic and Turing's argument principle method. Purely theoretical — numerical certification.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (formal certification)  
**derived_from:** skills/riemann-critical-line-zeros-advanced/skills.md  
**triggers:** "Turing method", "interval certification", "interval arithmetic", "argument principle", "zeros off critical line", "Riemann derived"

---

## 1. Enunciado (Professor)

Desenvolver certificação formal de intervalos livres de zeros fora da linha crítica usando aritmética de intervalos e o método de Turing (princípio do argumento). O objetivo é provar rigorosamente que não há zeros com Re(s) ≠ 1/2 em intervalos específicos.

---

## 2. Contexto (Pesquisador)

O método de Turing conta zeros em retângulos via variação do argumento. Com aritmética de intervalos, pode-se garantir bounds rigorosos para |ζ(s)| e argumentar que não há zeros em regiões específicas.

Referências: Turing (1939), Platt & Trudgian (2021), interval arithmetic literature.

---

## 3. Explicação didática (Professor)

Princípio do argumento: número de zeros menos polos dentro de um contorno = variação do argumento / 2π. Se ζ(s) não tem polos (exceto s=1), a variação do argumento conta zeros. Aritmética de intervalos fornece bounds rigorosos para a variação.

---

## 4. Derivação e testes (Aluno)

Pseudocódigo:
```
def certificar_intervalo_sem_zeros(fora_da_linha, retangulo):
    variacao_argumento = calcular_variacao_argumento_zeta(retangulo)
    numero_zeros = variacao_argumento / (2*pi)
    zeros_na_linha = contar_zeros_linha_critica(retangulo)
    return numero_zeros == zeros_na_linha
```

---

## 5. Contestação (QA)

| Item | Parecer |
|------|---------|
| Método de Turing para contagem | APROVADO |
| Aritmética de intervalos para bounds | APROVADO |
| Certificação para todo T → ∞ | REJEITADO (infinito não coberto) |

---

## 6. Registro de agentes

- Pesquisador: Turing, interval arithmetic, argument principle.
- Professor: Princípio do argumento, contagem de zeros, certificação formal.
- Aluno: Pseudocódigo de certificação, exemplo de retângulo.
- QA: Contesta que certificação finita não prova para infinito.

---

## 7. Quatro problemas derivados (terceira geração)

1. `turing-interval-higher-precision` — Aritmética de intervalos com maior precisão.
2. `turing-interval-automation` — Automatizar certificação de intervalos.
3. `turing-interval-large-T` — Aplicar a intervalos em alturas muito grandes.
4. `turing-interval-other-functions` — Aplicar a outras funções L.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills