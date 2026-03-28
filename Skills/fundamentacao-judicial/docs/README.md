# fundamentacao-judicial

Skill para elaboração da fundamentação de decisões judiciais: sentenças, decisões interlocutórias e tutelas provisórias.

> **Não** cobre fundamentação de **Embargos de Declaração**, que possui skill própria.

---

## Estrutura de arquivos

```
fundamentacao-judicial/
├── SKILL.md                                  # Instrução principal da skill
├── assets/
│   ├── template-sentenca.md                  # Template de fundamentação de sentença
│   ├── template-decisao-interlocutoria.md    # Template de decisão interlocutória
│   └── template-tutela-provisoria.md         # Template de tutela provisória
├── references/
│   ├── regras-de-estilo.md                   # Regras de estilo textual
│   ├── system-memories.json                  # Memórias gerais (fase de preparação)
│   ├── analysis-memories.json                # Memórias de análise (etapa 1)
│   └── style-memories.json                   # Memórias de estilo (etapa 3)
└── docs/
    └── README.md                             # Esta documentação
```

---

## Fluxo de execução

A skill opera em três etapas sequenciais, com checkpoints obrigatórios entre elas:

```
FASE 00 — Preparação
    └─ Identifica o tipo de decisão e carrega system-memories.json

Etapa 1 — Análise                         [STOP → aguarda usuário]
    └─ Mapeia controvérsias e apresenta encaminhamentos para validação

Etapa 2 — Plano de Argumentação
    └─ Estrutura o raciocínio em tópicos (skeleton-of-thought)

Etapa 3 — Redação
    └─ Produz a fundamentação em prosa, conforme template e regras de estilo
```

---

## Hierarquia de regras

| Prioridade | Fonte | Governa |
|---|---|---|
| 1 (absoluta) | `references/*-memories.json` | Qualquer matéria — prevalecem sobre tudo |
| 2 | `references/regras-de-estilo.md` + `SKILL.md` | Estilo textual (grafia, numerais, Ids., citações) |
| 3 | `assets/template-*.md` | Estrutura e encadeamento lógico-argumentativo |
| 4 | Arquivo-modelo do usuário | Estilo textual (sobrepõe nível 2, não os demais) |

---

## Templates

| Tipo de decisão | Template |
|---|---|
| Sentença | `assets/template-sentenca.md` |
| Decisão Interlocutória | `assets/template-decisao-interlocutoria.md` |
| Tutela Provisória | `assets/template-tutela-provisoria.md` |

Os templates governam a **estrutura** da fundamentação (ordem de análise, abertura de tópicos, parágrafos-padrão). Regras de estilo textual são definidas em `references/regras-de-estilo.md`.

---

## Arquivos de memórias

Os arquivos `*-memories.json` contêm instruções dinâmicas com prioridade absoluta sobre todas as demais regras da skill. São carregados em etapas específicas:

| Arquivo | Etapa |
|---|---|
| `system-memories.json` | FASE 00 — Preparação |
| `analysis-memories.json` | Etapa 1 — Análise |
| `style-memories.json` | Etapa 3 — Redação |

---

## Licença

GPL-3.0
