# Multi-Agent Mathematics Workflow

Este documento define como os agentes **QA, Aluno, Professor e Pesquisador** atuam em ciclos de rebuttal (contestação), validação e descoberta matemática, salvando tudo nos skills e criando novos skills a cada descoberta.

## Agentes envolvidos

| Agent | Arquivo | Foco |
|-------|---------|------|
| Pesquisador | `skills/researcher-agent/skills.md` | Investiga problemas em aberto, papers do arXiv, formula conjecturas, conecta áreas. |
| Professor | `skills/teacher-agent/skills.md` | Estrutura explicações didáticas, prova passo a passo, cria exercícios, valida clareza pedagógica. |
| Aluno | `skills/student-agent/skills.md` | Deriva do zero, testa com exemplos numéricos, identifica lacunas de entendimento, pergunta "por quê". |
| QA | `skills/qa-agent/skills.md` | Contesta teorias, busca contra-exemplos, casos extremos, valida reprodutibilidade numérica, revisa rigor. |

## Ciclo de trabalho (rebuttal → descoberta → novo skill)

1. **Entrada**: Uma teoria, problema ou conjectura entra no ciclo (ex: Hipótese de Riemann, equação de Navier-Stokes, conjectura de Goldbach).
2. **Pesquisa**: O pesquisador levanta papers do arXiv, resultados parciais e contexto histórico.
3. **Ensino**: O professor estrutura a explicação, prova parcial ou heurística de forma didática.
4. **Aprendizado**: O aluno deriva passo a passo, testa com exemplos concretos e sinaliza pontos obscuros.
5. **Contestação (QA)**: O QA rebutta a teoria, busca contra-exemplos, verifica casos extremos e exige rigor formal.
6. **Iteração**: Professor e aluno refinam a explicação com base nas críticas do QA.
7. **Registro**: Se o consenso for alcançado ou houver avanço, salva-se no `skills/math/skills.md`.
8. **Novo skill**: Toda descoberta nova (nova prova, nova conjectura, novo método numérico) gera um arquivo próprio em `skills/` (ex: `skills/riemann-heuristic/skills.md`).
9. **Commit**: Cada ciclo é registrado com [Conventional Commits](https://www.conventionalcommits.org/) (`feat:`, `fix:`, `docs:`, `refactor:`, `chore:`).

## Convenção de commits

```
<type>(<scope>): <description>

[opcional] corpo
```

Tipos usados neste repositório:
- `feat`: nova funcionalidade/skill, nova teoria validada, novo método.
- `fix`: correção de erro matemático, contra-exemplo encontrado, ajuste de prova.
- `docs`: documentação, explicações didáticas, referências bibliográficas.
- `refactor`: reestruturação de skill sem mudança de conteúdo matemático.
- `chore`: manutenção, ajuste de fluxo, metadados.

## Como salvar uma descoberta

1. Crie `skills/<nome-da-descoberta>/skills.md`.
2. Documente: enunciado, contexto, prova/heurística, status (aberto/parcial/resolvido), referências (arXiv quando aplicável), agentes que participaram.
3. Atualize `skills/math/skills.md` com referência cruzada, se aplicável.
4. Commit com `feat(scope): ...`.
