# Closed Timelike Curves Skill

**id:** closed-timelike-curves  
**name:** Closed Timelike Curves (CTCs) — Gödel, Wormholes, Tipler  
**description:** Mathematical study of spacetimes containing closed timelike curves. Gödel universe, Tipler cylinder, Morris–Thorne traversable wormholes, exotic matter, energy conditions. Purely theoretical general relativity.  
**author:** codingsh <codingsh@pm.me>  
**status:** theoretical (no physical CTCs observed)  
**derived_from:** skills/time-travel-teleportation-foundation/skills.md  
**triggers:** "closed timelike curve", "ctc", "godel", "tipler", "wormhole", "morris thorne", "exotic matter", "energy conditions", "general relativity", "lorentzian metric"

---

## 1. Enunciado (Teacher)

Um **curva fechada tipo-tempo (CTC)** é uma linha mundial em um espaço-tempo lorentziano que retorna ao próprio passado. Se CTCs existem fisicamente, viagem no tempo para o passado é, em princípio, possível dentro da relatividade geral.

Perguntas centrais:
1. Quais métricas admitem CTCs?
2. Que tipos de matéria/energia são necessários?
3. CTCs violam causalidade? Existe proteção cronológica?

---

## 2. Métricas com CTCs (Teacher)

### Gödel (1949)
Métrica do universo de Gödel (coordenadas cilíndricas):
```
ds² = -dt² + dr² + dz² + (sinh⁴r - sinh²r) dφ² + 2√2 sinh²r dt dφ
```
Possui CTCs através de todas as pontos. Universo rotativo, não-expansivo.

### Tipler Cilindro
Cilindro infinito, denso e rotativo. Métrica aproximada (coordenadas cilíndricas):
```
ds² = -dt² + dr² + dz² + r² dφ² + 2ω r² dt dφ
```
Para ω suficientemente grande, CTCs aparecem fora do cilindro.

### Morris–Thorne Wormhole (1988)
Métrica esferoidal simétrica:
```
ds² = -e^{2Φ(r)} dt² + dr²/(1 - b(r)/r) + r² (dθ² + sin²θ dφ²)
```
- Φ(r): redshift function (deve ser finita para buraco de minhoca travessável).
- b(r): função de forma (gargalo em r = b₀).

Condição de travessabilidade: não horizonte de eventos (Φ finito), condição de flare-out (b'(b₀) < 1).

---

## 3. Condições de Energia e Matéria Exótica (Teacher)

Para buracos de minhoca travessáveis, são necessárias violações das condições de energia:

- **Condição de energia nula (NEC):** $T_{\mu\nu} k^\mu k^\nu \ge 0$ para todo vetor nulo $k^\mu$.
- Wormholes travessáveis exigem violação da NEC perto do gargalo → **matéria exótica** (densidade de energia negativa observada por algum observador).

Não se conhece matéria exótica macroscópica. Efeitos quânticos (Casimir) produzem densidade negativa em escalas microscópicas, insuficientes para wormholes macroscópicos conhecidos.

---

## 4. Derivação e Testes (Student)

### Teste 1: Gödet CTC
Para r grande em Gödel, o coeficiente de dφ² torna-se negativo em algumas regiões, permitindo curvas fechadas tipo-tempo.

### Teste 2: Condição de flare-out
No gargalo r = b₀: 1 - b(r)/r = 0. Derivada em r:
```
d/dr [1 - b(r)/r] em r=b₀ = -(b'(b₀)·b₀ - b(b₀))/b₀² = -(b'(b₀)·b₀ - b₀)/b₀² = (1 - b'(b₀))/b₀
```
Para flare-out (abertura), precisamos 1 - b'(b₀) > 0 → b'(b₀) < 1.

### Pseudocódigo (ilustrativo, não prova física)
```
# Verificar se métrica de Gödel admite CTC em ponto (r, phi)
g_phiphi = sinh(r)**4 - sinh(r)**2
if g_phiphi < 0:
    # direcao phi se torna tipo-tempo -> CTC possivel
    report_CTC(r)
```

### Lacuna do aluno
Métricas exatas com CTCs são soluções da relatividade geral, mas não há evidência de que o universo real permita sua formação estável.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Gödel admite CTCs | APROVADO | Solução exata conhecida. |
| Tipler cilindro admite CTCs | APROVADO | Sob condições de rotação/densidade. |
| Wormhole travessável exige matéria exótica | APROVADO | Violação da NEC. |
| Matéria exótica existe em escala macroscópica | NÃO CONHECIDA | Efeito Casimir é microscópico. |
| CTCs permitem viagem no tempo física | ESPECULATIVO | Matemática permite; física não comprovada. |
| CTCs violam causalidade | RESSALVA | Paradoxos (avô) não resolvidos na teoria clássica. |

**Parecer QA:** CTCs são matematicamente consistentes em certas métricas, mas não há evidência física de sua existência. Não afirmar viagem no tempo como fato.

---

## 6. Registro de agentes

- **Pesquisador**: métricas de Gödel, Tipler, Morris–Thorne; literatura sobre energia exótica.
- **Professor**: equações das métricas, condição de flare-out, interpretação física.
- **Aluno**: derivação do flare-out, pseudocódigo de verificação de Gödel, identificação de lacuna.
- **QA**: contesta claims físicos, valida separação entre matemática e física experimental.

---

## 7. Próximo passo sugerido

Estudar a **conjectura de proteção cronológica de Hawking** (o universo impede a formação de CTCs) e sua relação com desigualdades quânticas (quantum inequalities).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
