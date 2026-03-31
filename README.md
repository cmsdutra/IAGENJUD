# IAGENJUD

Repositório de prompts e skills para uso de inteligência artificial generativa no fluxo de trabalho judicial — voltado, principalmente, à elaboração de minutas de decisões judiciais no âmbito da Justiça Federal.

---

## Estrutura

```
IAGENJUD/
├── Prompts Avulsos/   # Prompts independentes, de uso direto
└── Skills/            # Workflows estruturados para Claude Code
    ├── relatorio-judicial/
    ├── fundamentacao-judicial/
    ├── embargos-declaracao/
    └── img-to-data/
```

---

## Prompts Avulsos

Prompts independentes, prontos para uso em qualquer interface de LLM (ChatGPT, Claude, Gemini etc.). Não exigem configuração prévia — basta colar o conteúdo do arquivo no início da conversa.

| Arquivo | Função |
|---|---|
| `analisa-controversia.md` | Mapeamento e classificação de pontos controvertidos a partir das peças processuais |
| `analisa-embargos-declaracao.md` | Análise e minuta de decisão em embargos de declaração (versão avulsa, sem memória) |
| `analisa-laudo.md` | Análise crítica de laudo pericial |
| `case-brief.md` | Elaboração de case brief jurisprudencial |
| `deep_research.md` | Pesquisa acadêmica aprofundada em Direito |
| `deep_research (med).md` | Pesquisa de evidências clínicas sobre medicamentos e tratamentos |
| `gera-argumentos.md` | Desenvolvimento de teses e argumentos por método evolutivo |
| `IMG2TXT.md` | Transcrição de documentos escaneados ou fotografados |
| `meta_deepresearch.md` | Meta-prompt para pesquisa profunda (ChatGPT Deep Research) |
| `meta_prompting.md` | Geração de prompts jurídicos otimizados |
| `redige-ementa-cnj.md` | Redação de ementa no padrão CNJ |
| `redige-gutachtenstil.md` | Elaboração de parecer pelo método Gutachtenstil |
| `redige-relatorio-geral.md` | Redação de relatório judicial (versão avulsa, sem memória) |
| `redige-resumo-ementa.md` | Síntese de ato judicial em parágrafo estilo ementa |
| `resume-artigo.md` | Resumo e análise de artigos acadêmicos |
| `corrige-redacao-enem.md` | Avaliação de redação nos critérios do ENEM |
| `style_config.md` | Guia de estilo para documentos judiciais (referência) |

---

## Skills

Skills são workflows estruturados para uso com **Claude Code**. Diferente dos Prompts Avulsos, as skills mantêm memória de trabalho entre etapas, carregam templates e referências automaticamente, e impõem checkpoints obrigatórios de validação pelo usuário antes de avançar.

Para instalar uma skill no Claude Code, copie o arquivo `SKILL.md` para o diretório de skills configurado (tipicamente `~/.claude/skills/`).

---

### `relatorio-judicial`

Redige o **relatório** de decisões e sentenças judiciais no padrão da Justiça Federal da 1ª Região.

**Quando usar:** ao solicitar a seção de relatório de sentença, saneamento, tutela provisória ou decisão interlocutória. Não usar para embargos de declaração.

**Fluxo:**
1. Identifica o tipo de minuta (sentença, tutela provisória ou decisão interlocutória)
2. Confirma as peças processuais disponíveis
3. Redige o relatório em texto corrido, sem marcação estrutural visível, a partir dos templates e exemplos da skill

**Arquivos de referência:** templates por tipo de decisão (`t_sentenca.md`, `t_interlocutoria.md`, `t_tutProv.md`), exemplos de relatório completo e conciso, guia de estilo.

---

### `fundamentacao-judicial`

Elabora a **fundamentação** de sentenças, decisões interlocutórias e tutelas provisórias.

**Quando usar:** ao pedir a redação dos fundamentos, razões de decidir ou argumentação jurídica de uma decisão. **Não cobre embargos de declaração**, que possui skill própria.

**Fluxo:**
1. **Fase 00 — Preparação:** carrega `system-memories.json` e identifica o tipo de decisão
2. **Etapa 1 — Análise:** mapeia controvérsias e apresenta encaminhamentos para validação pelo usuário *(checkpoint)*
3. **Etapa 2 — Plano de argumentação:** estrutura a linha decisória para aprovação *(checkpoint)*
4. **Etapa 3 — Redação:** produz a fundamentação conforme template e regras de estilo

**Arquivos de referência:** templates por tipo de decisão, `regras-de-estilo.md`, `analysis-memories.json`, `style-memories.json`.

---

### `embargos-declaracao`

Conduz a elaboração completa da **minuta de decisão em embargos de declaração** — do relatório ao dispositivo.

**Quando usar:** sempre que o recurso em análise for embargos de declaração. Esta skill substitui integralmente `relatorio-judicial` e `fundamentacao-judicial` nesse contexto.

**Fluxo (quatro etapas sequenciais obrigatórias):**
1. **Relatório** — narra a decisão embargada, os fundamentos dos embargos e eventuais contrarrazões *(checkpoint)*
2. **Admissibilidade e mérito** — analisa os vícios alegados (obscuridade, contradição, omissão, erro material) *(checkpoint)*
3. **Plano de argumentação** — estrutura a resposta decisória para aprovação pelo usuário *(checkpoint)*
4. **Fundamentação** — redige os fundamentos conforme template e regras de estilo

**Limitações absolutas:** não inventa fatos, não avança sem confirmação do usuário, não cita jurisprudência além do previsto nos templates ou fornecido pelo usuário.

---

### `img-to-data`

Transcreve fielmente o conteúdo de **documentos escaneados ou fotografados**, preservando grafia, formatação e erros originais.

**Quando usar:** ao enviar imagens de documentos físicos (digitalizações, fotos, manuscritos, formulários, certidões, laudos) e solicitar transcrição ou extração de texto. Não usar para documentos já em formato digital editável.

**Fluxo:**
1. Confirma o recebimento e a quantidade de imagens
2. Se múltiplas imagens, pergunta se devem ser tratadas como documento único ou separado
3. Processa em lotes de até 3 imagens, aguardando confirmação entre lotes
4. Entrega a transcrição em bloco de código, com metadados de identificação

---

## Licença

GPL-3.0
