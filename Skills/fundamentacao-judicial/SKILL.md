---
name: fundamentacao-judicial
description: Redige a fundamentação de decisões judiciais (decisões interlocutórias, sentenças e tutelas provisórias). Use esta skill sempre que o usuário pedir para redigir, desenvolver ou elaborar a fundamentação de uma decisão ou sentença judicial, inclusive quando usar termos como "fundamentos", "razões de decidir", "fundamente", "redija a fundamentação", "desenvolva a argumentação" ou equivalentes. VEDADA a utilização para fundamentação de decisão sobre EMBARGOS DE DECLARAÇÃO, que possui skill própria.
license: GPL-3.0
---

# Skill: Fundamentação Judicial

Esta skill conduz a elaboração da fundamentação de sentenças e decisões judiciais, de acordo com templates e regras de estilo especificadas.

---

## FASE 00 - PREPARAÇÃO

Ao iniciar:
1. Leia as instruções dinâmicas em `/references/system-memories.json`
2. Certifique-se de que os documentos apresentados pelo usuário estão legíveis e íntegros. 
3. Em seguida, identifique o tipo de decisão que será fundamentada:
  - **Sentença**: decisão que encerra a fase de conhecimento do processo.
  - **Tutela Provisória**: decisão que antecipa ou assegura o provimento jurisdicional.
  - **Decisão Interlocutória**: decisão que resolve questão incidental ao processo (aplicação subsidiária em relação aos outros tipos).  

ATENÇÃO: Se o tipo de decisão não estiver claro, pergunte ao usuário antes de prosseguir.

---

## Etapa 1 — Análise

**Objetivo**: compreender o caso, mapear as controvérsias e apresentar encaminhamentos para escolha ou confirmação do usuário antes de qualquer redação.

Execute os seguintes passos:

1. Carregue e leia as instruções dinâmicas em `/references/analysis-memories.json`.
2. Leia os documentos do processo fornecidos pelo usuário (petições, decisões, laudos, atas de audiência etc.).
3. Identifique as controvérsias relevantes para a fundamentação, separando-as por questão ou tópico.
4. Apresente a análise de cada controvérsia no formato abaixo.
5. Ao final, apresente a tabela-resumo e aguarde o checkpoint do usuário.

**Encaminhamentos por tipo de controvérsia**:

- Sugira até três direcionamentos possíveis, cada um com título sintético, encaminhamento e justificativa em até três linhas. Os direcionamentos devem ser genuinamente distintos — não variações de tom, mas diferenças reais de encaminhamento ou fundamento (ex.: acolhimento total, acolhimento parcial, rejeição; ou fundamentos alternativos para o mesmo encaminhamento quando há mais de uma via jurídica plausível). Indique, quando houver, qual direcionamento parece mais adequado ao caso e por quê.

**Formato da Etapa 1**:

```
### ETAPA 1 — ANÁLISE

**Tipo de decisão identificado**: [interlocutória / sentença / tutela provisória]
**Template aplicável**: [nome do template]

---

**[Controvérsia N — Título sintético]**

[Síntese fática da questão, com referência aos Ids. relevantes.]
[Normas e institutos jurídicos aplicáveis — apenas mapeamento, sem aprofundamento.]

Direcionamentos possíveis:
  Opção A — [Título]: [encaminhamento + justificativa em até três linhas.]
  Opção B — [Título]: [encaminhamento + justificativa em até três linhas.]
  Opção C — [Título, se aplicável]: [encaminhamento + justificativa em até três linhas.]
[Indicação do direcionamento sugerido, se houver, com justificativa.]
--

[Pontos de atenção ou riscos relevantes, se houver.]

---

**RESUMO**

| Controvérsia | Encaminhamento proposto | Fundamento principal |
|---|---|---|
| ... | ... | ... |

---
⚠️ Aguardo confirmação dos encaminhamentos ou instruções antes de prosseguir para o Plano de Argumentação.
```

**STOP**: Após apresentar a Etapa 1, aguarde o checkpoint do usuário. **Não avance para a Etapa 2 sem confirmação ou instrução explícita**.

---

## Etapa 2 — Plano de Argumentação

**Objetivo**: estruturar, em tópicos sintéticos, o raciocínio que orientará a redação. Não é rascunho; é um esqueleto argumentativo (skeleton-of-thought).

IMPORTANTE: Execute após o checkpoint da Etapa 1:

1. Para cada controvérsia com encaminhamento confirmado, desenvolva um plano em tópicos com frases curtas e diretas, seguindo, por padrão, a seguinte **estrutura lógico-argumentativa**:
```
→ {Apresentação das controvérsias}
→ [para cada controvérsia]:
    → {Apresentação das normas, precedentes e institutos jurídicos aplicáveis}
    → {Aplicação no caso concreto}
    → {Refutação de argumentos contrários}
    → {Conclusão parcial}
→ {Conclusão geral}
```
2. Cada tópico deve representar um bloco argumentativo na redação final e pode ser divido em subtópicos, a depender da complexidade do argumento.
3. O plano deve ser enxuto — frases de até duas linhas por tópico.

**Formato da Etapa 2**:

```
### ETAPA 2 — PLANO DE ARGUMENTAÇÃO

**[Controvérsia N — Título sintético]**

1. [Frase direta descrevendo o que o parágrafo fará — ex.: "Apresentar o instituto X e a norma Y aplicável ao caso."]
2. [Frase direta — ex.: "Aplicar o requisito Z ao contexto fático do Id. XXXXX."]
    2.1. [Subtópico, se necessário]
    2.2. [Subtópico, se necessário]
    ...
3. [Frase direta — ex.: "Refutar a tese da parte RÉ de que [...], com base em [fundamento]."]
    3.1. [Subtópico, se necessário]
    3.2. [Subtópico, se necessário]
    ...
4. [Conclusão parcial — ex.: "Concluir pelo acolhimento/rejeição do pedido."]

**[Controvérsia N+1 — ...]**
...

**CONCLUSÃO GERAL**
- [Síntese do que será deliberado na conclusão.]
```

**Autoreflexão**: Antes de apresentar o Plano, certifique-se de está condizente com as deliberações do usuário na etapa 1 e com a estrutura lógico-argumentativa padrão. Se estiver, apresente o plano; senão, faça os ajustes necessários e repita a autoreflexão (máx: 2 rodadas).
---

### CHECKPOINT OBRIGATÓRIO — VALIDAÇÃO DO PLANO DE ARGUMENTAÇÃO

**STOP AQUI.** Após apresentar o Plano de Argumentação no formato da Etapa 2, **aguarde validação explícita do usuário antes de qualquer avanço para a Etapa 3**.

O usuário pode:
- Aceitar o plano integralmente (responda: "Aprove o plano" ou "Prossiga para redação").
- Solicitar edições no plano (indique quais tópicos alterar, como reformular, ou adicione novos desdobramentos).
- Rejeitar o plano e solicitar reconstrução total.

IMPORTANTE: **Você não avança para a Etapa 3 (Redação) sem autorização expressa do usuário.** Este é um checkpoint obrigatório.

---

## Etapa 3 — Redação

**Objetivo**: redigir a fundamentação completa, observando o template aplicável, as regras de estilo e o plano de argumentação aprovado.

### Mapeamento de Templates

| Tipo de Decisão | Arquivo |
|---|---|
| Sentença | `assets/template-sentenca.md` |
| Decisão Interlocutória | `assets/template-decisao-interlocutoria.md` |
| Tutela Provisória | `assets/template-tutela-provisoria.md` |

### Hierarquia de Regras (aplicar na fase de redação)

As regras de elaboração da fundamentação obedecem à seguinte hierarquia:

1. **Arquivo de memórias** (`/references/style-memories.json`): regras absolutas — prevalecem sobre qualquer outra instrução.
2. **Regras de estilo textual** (`/references/regras-de-estilo.md` e esta SKILL): governam a forma do texto (grafia de nomes das partes, numerais por extenso, referência a Ids., formato de citações etc.) — prevalecem sobre o template nessas matérias.
3. **Templates** (`assets/template-*.md`): governam a estrutura e o encadeamento lógico-argumentativo (ex.: ordem de análise dos requisitos, abertura de tópicos, parágrafos-padrão) — prevalecem sobre as regras de estilo em matéria estrutural.
4. **Arquivo-modelo fornecido pelo usuário**: prevalece sobre as regras de estilo textual, mas não sobre as memórias nem sobre a estrutura definida no template.

### Instruções:

1. Carregue e leia as instruções dinâmicas em `/references/style-memories.json` e as regras de estilo definidas em `/references/regras-de-estilo.md`.
2. Carregue e leia o template correspondente ao tipo de decisão (ver mapeamento acima) antes de iniciar a redação.
3. Siga a estrutura do template, preenchendo cada bloco conforme as instruções nele contidas.
4. Aplique todas as regras de estilo definidas nesta skill (Seção Regras de Estilo).
5. Siga o plano de argumentação da Etapa 2 como guia para cada parágrafo, sem citá-lo como fonte.
6. Não invente Ids., valores, datas ou fatos não fornecidos pelo usuário. Se uma informação necessária estiver ausente, sinalize com `[COMPLETAR: descrição do dado ausente]`.
7. Não cite jurisprudência ou doutrina que não tenha sido fornecida pelo usuário ou prevista no arquivo-modelo ou no template.
8. Ao referenciar documentos do processo, sempre indique o Id. correspondente (salvo a petição inicial).

9. Antes de entregar a resposta ao usuário, faça uma reflexão silenciosa, certificando-se de que a redação obedeceu as regras de estilo e o plano de argumentação, bem como as regras negativas e as restrições da skill. Caso não tenha obedecido, faça os ajustes necessários.

**Formato da saída**: Utilize a ferramenta `artifacts` com os seguintes parâmetros:
- `command`: "create"
- `type`: "text/plain"
- `title`: "Fundamentação — [Tipo de Decisão]"
- `content`: [texto da fundamentação conforme redação abaixo]

Produza o texto da fundamentação em prosa corrida, conforme o template. Não inclua marcações de template, comentários ou instruções do SKILL.md na saída final. O texto será entregue em artefato editável, pronto para incorporação à minuta da decisão e para edições do usuário inline.

---

## Notas de Comportamento

- IMPORTANTE: as instruções de memória (`/references/*-memories.json`) têm prevalência sobre todas as demais. Leia-as atentamente de acordo com as etapas de execução.
- Se o usuário fornecer um "esqueleto de pensamento", arquivo-modelo ou estrutura argumentativa própria, incorpore-a ao plano (fase 2) sem citá-la como fonte e sem transformá-la em tópicos numerados na redação.
- Se todas as controvérsias compartilharem a mesma solução ou premissa fático-jurídica, reúna-as em bloco único para evitar redundâncias, desde que não haja prejuízo à estrutura lógica.
- Questões prefaciais (gratuidade da justiça, emenda à inicial etc.) devem ser tratadas antes do mérito ou do pedido de tutela, conforme previsto nos templates.