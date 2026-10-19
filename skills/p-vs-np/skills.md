# P vs NP Skill

**id:** p-vs-np  
**name:** P versus NP Problem — Clay Millennium Prize Problem  
**description:** 4-agent cycle skill for the P versus NP problem (open since 1971/2000). Investigates whether every problem whose solution can be quickly verified (NP) can also be quickly solved (P). Purely theoretical and educational — no claim of solution.  
**author:** codingsh <codingsh@pm.me>  
**status:** open (unsolved since 1971)  
**derived_from:** skills/millennium-prize-problems/skills.md  
**triggers:** "P vs NP", "P equals NP", "NP-complete", "NP-hard", "polynomial time", "verification", "computational complexity", "Cook-Levin", "millennium", "clay"

---

## 1. Enunciado (Professor)

**Problema P versus NP:** Toda problema cuja solução pode ser verificada em tempo polinomial também pode ser resolvida em tempo polinomial? Em termos formais: P = NP?

- **P**: classe de problemas de decisão solúveis em tempo polinomial por uma máquina de Turing determinística.
- **NP**: classe de problemas de decisão cujas soluções (certificados) podem ser verificadas em tempo polinomial por uma máquina determinística, dado o certificado.

**Por que importa:** Se P = NP, criptografia de chave pública (RSA, ECC), otimização, aprendizado de máquina e praticamente toda ciência da computação seriam impactados — problemas hoje considerados intratáveis se tornariam fáceis. Se P ≠ NP, há limites fundamentais ao que pode ser computado eficientemente.

---

## 2. Contexto e estado-da-arte (Pesquisador)

### Histórico
- Cook (1971) e Levin (1973) introduziram independentemente o conceito de NP-completude.
- O Teorema de Cook–Levin estabelece que o Problema da Satutibilidade Booleana (SAT) é NP-completo.
- Karp (1972) identificou 21 problemas NP-completos, incluindo CLIQUE, VERTEX COVER, HAMILTONIAN CYCLE.
- Clay Mathematics Institute incluiu P vs NP como um dos 7 Problemas do Prêmio do Milênio (2000).

### Resultados conhecidos
- P ⊆ NP (qualquer problema solúvel em tempo polinomial também tem sua solução verificável em tempo polinomial).
- Não se sabe se P = NP ou P ≠ NP.
- Centenas de problemas são conhecidos como NP-completos; se qualquer um estiver em P, então P = NP.
- Barreiras de prova conhecidas: Natural Proofs (Razborov–Rudich, 1997), Relativização (Baker–Gill–Solovay, 1975), Algebrization (Aaronson–Wigderson, 2009).

### Referências sugeridas
- Cook, S.A. (1971). "The Complexity of Theorem-Proving Procedures".
- Levin, L.A. (1973). "Universal sorting problems".
- Karp, R.M. (1972). "Reducibility among combinatorial problems".
- Arora & Barak, "Computational Complexity: A Modern Approach".
- arXiv: papers sobre P vs NP, barriers, complexidade.

---

## 3. Explicação didática (Professor)

### Intuição
Imagine um quebra-cabeça de 1000 peças. Verificar se uma montagem dada está correta é fácil (basta olhar se as peças encaixam). Mas encontrar a montagem correta do zero é difícil. P vs NP pergunta: existe um atalho que torne encontrar a solução tão fácil quanto verificá-la?

### Exemplo: SAT
Dada uma fórmula booleana (ex: (x₁ ∨ ¬x₂) ∧ (x₂ ∨ x₃)), existe uma atribuição de verdade às variáveis que torna a fórmula verdadeira?
- Verificar uma atribuição dada: fácil (tempo polinomial).
- Encontrar uma atribuição: pode exigir testar 2ⁿ possibilidades no pior caso.

### Estrutura de uma prova de P ≠ NP
1. Mostrar que existe um problema em NP que não tem algoritmo de tempo polinomial.
2. Geralmente via redução de um problema candidato NP-completo.
3. Ou mostrar uma barreira: nenhuma técnica de prova conhecida pode resolver P vs NP.

### Estrutura de uma prova de P = NP
1. Fornecer um algoritmo de tempo polinomial para um problema NP-completo (ex: SAT).
2. Como todo problema em NP se reduz a SAT, isso prova P = NP.

---

## 4. Derivação e testes (Aluno)

### Exemplo ilustrativo: problema do caixeiro-viajante (TSP)
Dadas n cidades e distâncias entre elas, existe um ciclo que visita cada cidade exatamente uma vez com custo total ≤ K?

- Verificar um ciclo dado: soma as distâncias, O(n) — fácil.
- Encontrar o ciclo ótimo: (n−1)!/2 possibilidades — crescimento fatorial.

### Pseudocódigo de verificação (SAT)
```
def verifica_sat(formula, atribuicao):
    for clausula in formula:
        if not avalia(clausula, atribuicao):
            return False
    return True  # tempo polinomial no tamanho da formula
```

### Pseudocódigo de busca (força bruta)
```
def resolve_sat(forca_bruta, formula):
    variaveis = extrai_variaveis(formula)
    for atribuicao em todas_as_2_n_atribuicoes(variaveis):
        if verifica_sat(formula, atribuicao):
            return atribuicao
    return None  # exponencial no pior caso
```

### Lacuna identificada pelo aluno
Não existe algoritmo conhecido de tempo polinomial para SAT. Provar que nenhum existe é o cerne de P ≠ NP. Técnicas atuais (diagonalização, circuitos, interpolação) todas enfrentam barreiras.

---

## 5. Contestação e casos extremos (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| P ⊆ NP | APROVADO | Definição padrão. |
| SAT é NP-completo | APROVADO | Teorema de Cook–Levin. |
| Se um problema NP-completo está em P, então P = NP | APROVADO | Por redução polinomial. |
| P = NP quebraria criptografia? | APROVADO (teoricamente) | RSA, ECC dependem de problemas supostamente fora de P. |
| Provas atuais resolveram P vs NP? | REJEITADO | Todas falharam ou enfrentam barreiras (natural proofs, relativização, algebrization). |
| "Eu provei P ≠ NP" em pré-print | ESPECULATIVO | Exige revisão por pares e aceitação da comunidade. |

**Parecer QA:** P vs NP permanece um dos problemas mais importantes e difíceis da ciência da computação. Não afirmar solução sem revisão por pares externa.

---

## 6. Registro de agentes participantes

- **Pesquisador**: Levantou Cook–Levin, Karp 21 problemas, barreiras de prova, referências clássicas e arXiv.
- **Professor**: Estruturou enunciado, intuição (quebra-cabeça), exemplo SAT e TSP, estrutura de prova para ambos os sentidos.
- **Aluno**: Testou SAT e TSP, pseudocódigo de verificação e busca, identificou ausência de algoritmo polinomial conhecido.
- **QA**: Contesta claims excessivos, valida reduções, rejeita provas não revisadas por pares.

---

## 7. Quatro problemas derivados (a partir deste skill)

1. `p-vs-np-circuit-lower-bounds` — Limites inferiores de circuitos para funções explícitas; mostrar que funções explícitas exigem circuitos super-polinomiais.
2. `p-vs-np-natural-proofs-barrier` — Investigar a barreira de Razborov–Rudich: por que provas de limites inferiores via "natural proofs" não resolvem P vs NP.
3. `p-vs-np-algebrization-barrier` — Estudar a barreira de algebrization de Aaronson–Wigderson e suas implicações.
4. `p-vs-np-interactive-proofs-pcp` — Teorema PCP e dureza de aproximação; conexão com NP e aproximação de problemas NP-difíceis.

---

## 8. Safety & Scope

- Conteúdo esteducional e teórico.
- Discussão de implicações criptográficas é defensiva (importância de P ≠ NP para segurança), nunca instruções para quebrar cifras.
- Não constitui prova de P = NP ou P ≠ NP.

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
