# Quantum Teleportation Skill

**id:** quantum-teleportation  
**name:** Quantum Teleportation Protocol — Mathematics  
**description:** Mathematical foundations of quantum teleportation: Bell states, entanglement, quantum channel, classical communication, no-cloning theorem. Information-only teleportation; no matter transportation. Purely theoretical quantum information.  
**author:** codingsh <codingsh@pm.me>  
**status:** established protocol (Bennett et al. 1993)  
**derived_from:** skills/time-travel-teleportation-foundation/skills.md  
**triggers:** "quantum teleportation", "bell state", "entanglement", "no cloning", "quantum channel", "qubit", "pauli", "bennett 1993"

---

## 1. Enunciado (Teacher)

Teleportação quântica é um protocolo que transmite um **estado quântico desconhecido** de um qubit de Alice para Bob usando:
1. Um par entrelaçado previamente compartilhado (Bell state).
2. Dois bits clássicos de comunicação de Alice para Bob.

**Importante:** Não transporta matéria nem energia. Transporta **informação quântica**. O estado original em Alice é destruído (medida), respeitando o teorema do não-clonagem.

---

## 2. Protocolo Passo a Passo (Teacher)

### Estados de Bell
```
|Φ⁺⟩ = (|00⟩ + |11⟩)/√2
|Φ⁻⟩ = (|00⟩ − |11⟩)/√2
|Ψ⁺⟩ = (|01⟩ + |10⟩)/√2
|Ψ⁻⟩ = (|01⟩ − |10⟩)/√2
```

### Estado a ser teleportado
Alice tem qubit: |ψ⟩ = α|0⟩ + β|1⟩ (α, β desconhecidos).

### Estado global inicial (3 qubits: Alice 1, Alice 2, Bob)
```
|ψ⟩ ⊗ |Φ⁺⟩ = (α|0⟩ + β|1⟩) ⊗ (|00⟩ + |11⟩)/√2
```

### Passos
1. Alice aplica CNOT (controle: seu qubit |ψ⟩, alvo: sua metade do Bell) e depois Hadamard em |ψ⟩.
2. Alice mede seus 2 qubits na base computacional → obtém 2 bits clássicos (m₁m₂).
3. Alice envia m₁m₂ por canal clássico para Bob.
4. Bob aplica correção condicional:
   - 00: identidade (I)
   - 01: X (bit-flip)
   - 10: Z (phase-flip)
   - 11: ZX (ou iY)

Resultado: Bob recupera |ψ⟩ exatamente.

---

## 3. Teorema do Não-Clonagem (Teacher)

Não existe operação quântica unitária U tal que:
```
U |ψ⟩|0⟩ = |ψ⟩|ψ⟩   para todo |ψ⟩ desconhecido
```
Prova por contradição usando linearidade e produto interno:
Se |ψ⟩ e |φ⟩ são clonáveis, então ⟨ψ|φ⟩ = ⟨ψ|φ⟩², o que só vale se ⟨ψ|φ⟩ ∈ {0,1}. Estados não-ortogonais não podem ser clonados.

Consequência: teleportação não clona o estado; o original é destruído na medida de Alice.

---

## 4. Derivação e Testes (Student)

### Teste numérico ilustrativo (simulação de 3 qubits)
```
# Estados de base computacional
# Alice mede (m1, m2) = (1, 0) -> Bob aplica Z
# Estado final de Bob deve ser alpha|0> + beta|1> (fidelidade 1)
```

### Pseudocódigo (ilustrativo, não execução física)
```
protocolo_teleportacao(alpha, beta):
    # Preparar Bell entre Alice2 e Bob
    bell = (|00> + |11>)/sqrt(2)
    estado = (alpha|0> + beta|1>) otimes bell
    # Alice: CNOT + H + medida
    m1, m2 = medir(estado[alice1, alice2])
    # Enviar m1,m2 classicamente para Bob
    if (m1,m2) == (0,0): bob.aplicar(I)
    elif (m1,m2) == (0,1): bob.aplicar(X)
    elif (m1,m2) == (1,0): bob.aplicar(Z)
    elif (m1,m2) == (1,1): bob.aplicar(Z @ X)
    return bob.estado  # == alpha|0> + beta|1>
```

### Lacuna do aluno
A comunicação clássica de 2 bits é obrigatória. Sem ela, Bob não sabe qual correção aplicar → não há sinalização mais rápida que a luz.

---

## 5. Contestação (QA)

| Item | Parecer | Observação |
|------|---------|------------|
| Teleportação transmite estado quântico | APROVADO | Protocolo de Bennett et al. (1993), verificado experimentalmente. |
| Transmite matéria/energia | REJEITADO | Apenas informação quântica. |
| Mais rápido que a luz | REJEITADO | Exige canal clássico (limitado por c). |
| Clona estados | REJEITADO | Não-clonagem impede; original é destruído. |
| Teleportação macroscópica (pessoa) | ESPECULATIVA/FICÇÃO | Não há base física conhecida. |

**Parecer QA:** Teleportação quântica é real no domínio da informação quântica. Não confundir com teleportação de ficção científica.

---

## 6. Registro de agentes

- **Pesquisador**: protocolo Bennett-Brassard-Crépeau-Jozsa-Peres-Wootters (1993), estados de Bell, não-clonagem.
- **Professor**: derivação do protocolo, correções de Pauli, interpretação.
- **Aluno**: pseudocódigo, simulação conceitual, identificação da necessidade de canal clássico.
- **QA**: contesta confundimento com ficção científica, valida limites (canal clássico, não-clonagem).

---

## 7. Próximo passo sugerido

Estudar **teleportação de estados contínuos (variáveis contínuas)** e **entanglement swapping**, e a capacidade de canais quânticos (teorema de Holevo).

---

**Maintainer:** codingsh <codingsh@pm.me>  
**Repository:** github.com/developerfred/-math-agent-skills
