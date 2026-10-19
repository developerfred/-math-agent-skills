# Unsolved Mathematics Problems Skill

**id:** unsolved-problems  
**name:** Open Problems in Mathematics  
**description:** Catálogo de problemas matemáticos ainda não resolvidos, usados como desafios para o ciclo multi-agente (pesquisa → ensino → aprendizado → contestação → registro). Conteúdo esteducional e teórico.  
**author:** codingsh <codingsh@pm.me>  
**triggers:** "unsolved", "open problem", "millennium", "conjecture", "challenge", "riddle", "proof", "collatz", "goldbach", "riemann", "navier-stokes", "p vs np", "parallel", "gpu", "memory", "amdahl", "roofline", "p vs nc", "memory wall"

---

## Millennium Prize Problems (Clay Mathematics Institute)

1. **P vs NP**: Todo problema cuja solução pode ser verificada rapidamente pode ser resolvido rapidamente? (Aberto)
2. **Hipótese de Riemann**: Todos os zeros não triviais da função zeta de Riemann têm parte real 1/2? (Aberto)
3. **Conjectura de Birch e Swinnerton-Dyer**: Relaciona pontos racionais de curvas elípticas com o comportamento da função L associada. (Aberto)
4. **Equação de Navier-Stokes**: Existem soluções suaves e globalmente definidas para todas as condições iniciais em 3D? (Aberto)
5. **Conjectura de Hodge**: Relação entre ciclos algébricos e classes de cohomologia em variedades projetivas não singulares. (Aberto)
6. **Teorema de Poincaré**: Toda variedade fechada 3-meromorfa simplesmente conexa é homeomorfa à 3-esfera. **Resolvida** por Grigori Perelman (2002-2003).
7. **Teoria de Yang-Mills e espaço de massa**: Existe uma teoria quântica de Yang-Mills com espaço de massa positivo? (Aberto)

## Outros desafios clássicos em aberto

- **Conjectura de Goldbach**: Todo inteiro par maior que 2 é soma de dois primos? (Aberto; verificado computacionalmente até grandes limites).
- **Conjectura dos primos gêmeos**: Existem infinitos pares (p, p+2) de primos? (Aberto; progresso com Zhang/Maynard/Tao em gaps limitados).
- **Conjectura de Collatz (3n+1)**: Toda sequência definida por n → n/2 (par) ou 3n+1 (ímpar) eventualmente chega a 1? (Aberto).
- **Conjectura de Legendre**: Entre n² e (n+1)² sempre há um primo? (Aberto).
- **Conjectura de Brocard**: n! + 1 = m² tem apenas soluções (4,5), (5,11), (7,71)? (Aberto).

## Paralelismo, GPU e Memória — Problemas em Aberto

- **Memory Wall**: A intensidade aritmética cresce rápido o suficiente para superar o gap de latência entre CPU/GPU e DRAM? (Aberto; problema de co-design arquitetural sem limite de forma fechada.)
- **Tamanho ótimo de tile (blocking)**: Para hierarquias de cache arbitrárias e formatos de tensor, encontrar fatores de bloqueio globalmente ótimos é NP-hard no geral; heurísticas dominam. (Aberto)
- **Paralelismo irregular**: Algoritmos de grafo (BFS, PageRank, SpMV) têm desbalanceamento de carga; limites teóricos para travessia paralela work-efficient permanecem abertos para muitas classes. (Aberto)
- **Pressão de registradores vs ocupação GPU**: Modelo analítico para alocação ótima de registradores sob restrições de ocupação é um problema de otimização aberto. (Aberto)
- **P vs NC**: Todo problema eficientemente solúvel em paralelo (NC) é igual a P? Questão fundamental de complexidade paralela, relacionada a P vs NP. (Aberto)
- **P vs NC × Fluidos**: A simulação de Navier–Stokes/Euler é P-completa ou está em NC? Conexão investigada em `skills/p-vs-nc-fluids-connection/skills.md` com 4 problemas derivados (Navier–Stokes P-completo, verificação de explosão de Euler, integral BKM paralela, métodos espaço-tempo/Parareal).

## Atualização de 2026 — Navier–Stokes (Millennium Prize)

Em setembro de 2026, a OpenAI anunciou uma proposta de solução para o Problema de Navier–Stokes Existência e Suavidade, com prova e formalização em Lean. A OpenAI declarou que **não reivindica o Prêmio do Milênio**. O Clay Mathematics Institute **não considera** propostas até pelo menos 2 anos após publicação. Portanto, o problema segue **aberto oficialmente**. Esse caso foi documentado em `skills/navier-stokes-millennium/skills.md` pelo ciclo dos 4 agentes (pesquisador, professor, aluno, QA).

## Millennium Prize Problems — Clay Mathematics Institute

- **Hipótese de Riemann (1859)**: Todos os zeros não triviais da função zeta ζ(s) têm parte real 1/2? (Aberto desde 1859).
- **P vs NP**: Se uma solução pode ser verificada rapidamente, pode ser resolvida rapidamente? P = NP? (Aberto).
- **Navier–Stokes Existência e Suavidade**: Existem soluções suaves globalmente definidas para as equações de Navier–Stokes incompressíveis em 3D? (Aberto; documentado em `skills/navier-stokes-millennium/skills.md`).
- **Yang–Mills e Espaço de Massa**: Existe uma teoria quântica de Yang–Mills com espaço de massa positivo? (Aberto).
- **Conjectura de Hodge**: Toda classe de Hodge é uma combinação racional de classes de ciclos algébricos? (Aberto).
- **Conjectura de Birch e Swinnerton-Dyer**: O posto do grupo de pontos racionais de uma curva elíptica é igual à ordem de anulação de sua função L em s = 1? (Aberto).

**Nota:** A Conjectura de Poincaré foi resolvida por Grigori Perelman (2002–2003). Catálogo completo e ciclo dos 4 agentes em `skills/millennium-prize-problems/skills.md`.

## Viagem no Tempo e Teleportação — Problemas Teoréticos

- **CTCs (Gödel, Tipler, wormholes)**: métricas da relatividade geral admitem curvas fechadas tipo-tempo? Exigem matéria exótica (violação da NEC). Documentado em `skills/closed-timelike-curves/skills.md`.
- **Teleportação quântica**: protocolo estabelecido (Bennett et al. 1993). Transmite informação, não matéria. Exige canal clássico. Documentado em `skills/quantum-teleportation/skills.md`.
- **Proteção cronológica (Hawking)**: conjectura de que efeitos quânticos impedem CTCs. Em aberto. Documentado em `skills/chronology-protection/skills.md`.
- **Complexidade de simular espaço-tempo com CTCs**: em NC ou P-completo? Modelo Aaronson–Watrous (P = PSPACE com CTCs) é teórico de computação, não física real. Documentado em `skills/spacetime-simulation-complexity/skills.md`.

## Como os agentes atuam sobre esses problemas

1. **Pesquisador**: Levanta papers do arXiv e resultados parciais sobre o problema escolhido.
2. **Professor**: Estrutura o enunciado, histórico e tentativas famosas de forma didática.
3. **Aluno**: Deriva casos particulares, testa numericamente, aponta o que não entende.
4. **QA**: Busca contra-exemplos computacionais, valida razões pelas quais tentativas conhecidas falharam.
5. **Registro**: Cada avanço ou heurística válida gera um novo skill em `skills/` (ex: `skills/riemann-heuristic/skills.md`).

## Regras de uso

- Esses problemas são desafios intelectuais educacionais.
- Nenhum agente deve afirmar ter "resolvido" um problema do Prêmio do Milênio sem revisão por pares externa e publicação aceita.
- O registro no repositório é heurístico/documental, não substitui revisão científica formal.
