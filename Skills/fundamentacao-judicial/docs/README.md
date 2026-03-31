# SKILL — FUNDAMENTACAO-JUDICIAL

Skill do sistema IAGENJUD destinada à redação assistida da fundamentação de decisões judiciais. Conduz o processo de elaboração em três etapas sequenciais — análise, plano de argumentação e redação —, submetendo cada fase à validação do usuário antes de avançar.

---

## Sumário

1. [Visão Geral](#1-visão-geral)
2. [Estrutura de Arquivos](#2-estrutura-de-arquivos)
3. [Funcionamento — Etapas de Execução](#3-funcionamento--etapas-de-execução)
4. [Tipos de Decisão e Templates](#4-tipos-de-decisão-e-templates)
5. [Regras de Estilo](#5-regras-de-estilo)
6. [Instruções Dinâmicas](#6-instruções-dinâmicas)
7. [Como Usar](#7-como-usar)
8. [Restrições e Limites](#8-restrições-e-limites)

---

## 1. Visão Geral

A skill `fundamentacao-judicial` é ativada sempre que o usuário solicita a redação, desenvolvimento ou elaboração da fundamentação de uma decisão ou sentença judicial. Expressões que disparam a skill incluem, entre outras: "fundamente", "redija a fundamentação", "desenvolva a argumentação", "razões de decidir" e equivalentes.

> **Vedação expressa**: a skill **não** deve ser utilizada para fundamentação de decisões sobre **embargos de declaração**, que possui skill própria.

O fluxo de trabalho é estruturado em três etapas com checkpoints obrigatórios, garantindo que o usuário valide os encaminhamentos propostos antes de qualquer redação.

---

## 2. Estrutura de Arquivos

```
fundamentacao-judicial/
├── SKILL.md                              # Definição da skill e instruções de execução
├── assets/
│   ├── template-sentenca.md              # Template da fundamentação de sentença
│   ├── template-decisao-interlocutoria.md # Template de decisão interlocutória
│   └── template-tutela-provisoria.md     # Template de tutela provisória
├── references/
│   ├── instrucoes-dinamicas.yaml         # Instruções de sistema, análise e estilo (alta precedência)
│   └── regras-de-estilo.md               # Regras gerais de estilo e vedações
└── docs/
    └── README.md                         # Este arquivo
```

### Descrição dos arquivos

| Arquivo | Função |
|---|---|
| `SKILL.md` | Define o comportamento da skill, as etapas de execução e as notas de comportamento. É o arquivo de orquestração central. |
| `assets/template-*.md` | Templates estruturais que definem a forma e os blocos obrigatórios de cada tipo de decisão. |
| `references/instrucoes-dinamicas.yaml` | Instruções de sistema, análise e estilo com **precedência máxima** sobre todas as demais. Consultado no início de cada etapa pertinente. |
| `references/regras-de-estilo.md` | Conjunto de regras de linguagem, formatação, citação e vedações a ser observado na redação. |

---

## 3. Funcionamento — Etapas de Execução

A skill opera em quatro fases, sendo três delas produtivas e uma preparatória.

### Fase 00 — Preparação

Antes de qualquer análise, a skill:

1. Lê as instruções dinâmicas de `sistema` e `analise` em `references/instrucoes-dinamicas.yaml`.
2. Verifica a integridade e legibilidade dos documentos fornecidos pelo usuário. Se os documentos estiverem corrompidos ou ilegíveis, a execução é **abortada**.
3. Identifica o tipo de decisão a ser fundamentada (sentença, tutela provisória ou decisão interlocutória). Caso o tipo não esteja claro, pergunta ao usuário antes de prosseguir.

---

### Etapa 1 — Análise

**Objetivo**: compreender o caso, mapear as controvérsias relevantes e apresentar encaminhamentos para escolha ou confirmação do usuário, **antes de qualquer redação**.

A skill lê os documentos do processo (petições, decisões, laudos, atas de audiência etc.), identifica as controvérsias e apresenta, para cada uma:

- síntese fática da questão, com referência aos Ids. dos documentos relevantes;
- normas e institutos jurídicos aplicáveis (apenas mapeamento, sem aprofundamento);
- até três direcionamentos possíveis, genuinamente distintos (ex.: acolhimento total, acolhimento parcial, rejeição), cada um com título, encaminhamento e justificativa de até três linhas;
- indicação do direcionamento sugerido, quando houver, com justificativa.

Ao final, apresenta uma tabela-resumo das controvérsias e encaminhamentos propostos.

> **Checkpoint obrigatório**: a skill aguarda validação ou instrução do usuário antes de avançar para a Etapa 2. Nenhuma redação é iniciada sem confirmação.

---

### Etapa 2 — Plano de Argumentação

**Objetivo**: estruturar, em tópicos sintéticos, o raciocínio que orientará a redação. Não é rascunho; é um esqueleto argumentativo (*skeleton-of-thought*).

Com base nos encaminhamentos confirmados, a skill elabora um plano por controvérsia, seguindo a estrutura lógico-argumentativa padrão:

```
→ Apresentação das controvérsias
→ [para cada controvérsia]:
    → Apresentação das normas, precedentes e institutos jurídicos aplicáveis
    → Aplicação no caso concreto
    → Refutação de argumentos contrários
    → Conclusão parcial
→ Conclusão geral
```

Cada tópico representa um bloco argumentativo da redação final. O plano é enxuto — frases de até duas linhas por tópico.

Antes de apresentar o plano, a skill realiza uma **autorreflexão** verificando se o plano está condizente com as deliberações do usuário na Etapa 1 e com a estrutura lógica padrão. Caso não esteja, realiza os ajustes necessários (máximo de duas rodadas).

> **Checkpoint obrigatório**: a skill aguarda validação explícita do usuário antes de iniciar qualquer redação. O usuário pode aceitar o plano, solicitar edições pontuais ou rejeitar e pedir reconstrução total.

---

### Etapa 3 — Redação

**Objetivo**: redigir a fundamentação completa, observando o template aplicável, as regras de estilo e o plano de argumentação aprovado.

A skill:

1. Carrega e lê as regras de estilo (`references/regras-de-estilo.md`), as instruções dinâmicas de `estilo` (`references/instrucoes-dinamicas.yaml`) e o template correspondente ao tipo de decisão.
2. Segue a estrutura do template, preenchendo cada bloco conforme as instruções nele contidas.
3. Utiliza o plano de argumentação como guia parágrafo a parágrafo, sem citá-lo como fonte no texto final.
4. Realiza uma **reflexão silenciosa** antes de entregar o texto, verificando conformidade com as regras de estilo, o plano de argumentação, as regras negativas e as restrições da skill. Realiza ajustes se necessário.

O texto é entregue em prosa corrida, **pronto para incorporação à minuta**, sem marcações de template, comentários ou instruções internas.

---

## 4. Tipos de Decisão e Templates

| Tipo de Decisão | Template | Características principais |
|---|---|---|
| **Sentença** | `assets/template-sentenca.md` | Prevê seção de julgamento antecipado (quando cabível), questões prefaciais e mérito, com abertura de tópicos por controvérsia quando necessário. |
| **Tutela Provisória** | `assets/template-tutela-provisoria.md` | Inclui parágrafos-padrão para tutela de urgência, tutela de evidência e procedimentos especiais. A análise do *periculum in mora* precede o exame do *fumus boni iuris* por padrão. |
| **Decisão Interlocutória** | `assets/template-decisao-interlocutoria.md` | Aplicação subsidiária em relação aos demais tipos. Estrutura flexível para questões incidentais, com abertura de tópicos quando há mais de uma questão pendente. |

---

## 5. Regras de Estilo

As regras de estilo estão integralmente definidas em `references/regras-de-estilo.md` e complementadas pelas instruções dinâmicas de `estilo` em `references/instrucoes-dinamicas.yaml`. Os principais critérios são:

**Tom e linguagem**
- Formal, autoritativo, em voz ativa e impessoal.
- Sem arcaísmos ou juridiquês excessivo; rigor técnico com viés informativo.
- Não referenciar o juízo prolator em primeira pessoa.

**Formatação**
- Nomes das partes em **MAIÚSCULO**; funções processuais em minúsculo.
- Valores monetários e prazos: numeral seguido da forma por extenso entre parênteses. Exceção: datas são escritas apenas em numeral.
- Listas com marcadores em numerais romanos minúsculos entre parênteses: `(i) ...; (ii) ...`.
- Referências a documentos processuais sempre com o respectivo **Id.**.

**Citações**

| Fonte | Formato |
|---|---|
| Legislação | `art. [x]`, `inc. [x]`, `alínea [x]`, `§ 1º` |
| Jurisprudência | `([TRIBUNAL]. [Órgão]. [Recurso/Ação], [Relator], [DJ] - [Tema, se houver])` |
| Doutrina | `([Autor], *[Nome da obra]*, [edição], [página])` |

**Vedações expressas**
- Jurisprudência e doutrina são, em regra, **vedadas**, salvo quando fornecidas no template, em modelos ou pelo próprio usuário. Não utilizar jurisprudência ou doutrina referenciada nas petições do processo.
- **Nunca inventar ou inferir** conteúdo, numeração ou artigos de leis ou diplomas normativos. Em caso de dúvida objetiva, pesquisar no portal oficial `planalto.gov.br`; só citar havendo correspondência exata.
- Na dúvida, perguntar ao usuário.

---

## 6. Instruções Dinâmicas

O arquivo `references/instrucoes-dinamicas.yaml` contém instruções de **precedência máxima**, sobrepondo-se a todas as demais em caso de conflito. É estruturado em três seções:

| Seção | Quando é lida | Função |
|---|---|---|
| `sistema` | Fase 00 — Preparação | Instruções gerais de execução, incluindo a verificação de integridade dos documentos. |
| `analise` | Etapa 1 — Análise | Diretrizes específicas para a fase analítica (atualmente sem instruções adicionais além das do `SKILL.md`). |
| `estilo` | Etapa 3 — Redação | Regras de estilo que complementam ou prevalecem sobre as de `regras-de-estilo.md`. |

O arquivo é editável pelo usuário para inclusão de instruções pontuais aplicáveis a um contexto específico, sem necessidade de alteração do `SKILL.md`.

---

## 7. Como Usar

### Ativação

A skill é ativada automaticamente ao se solicitar a fundamentação de uma decisão judicial. Exemplos de comandos que a disparam:

- "Fundamente a decisão."
- "Redija a fundamentação da sentença."
- "Desenvolva a argumentação para a tutela provisória."
- "Elabore os fundamentos da decisão interlocutória."

### Documentos a fornecer

Forneça os documentos do processo relevantes para a fundamentação: petições, contestações, laudos periciais, atas de audiência, documentos probatórios, decisões anteriores etc. Os documentos devem estar legíveis e identificáveis.

### Fluxo típico de interação

```
Usuário: fornece documentos + solicita fundamentação
  ↓
[Etapa 1] Skill apresenta análise das controvérsias e encaminhamentos propostos
  ↓
Usuário: confirma, ajusta ou rejeita os encaminhamentos
  ↓
[Etapa 2] Skill apresenta o plano de argumentação
  ↓
Usuário: aprova, edita ou rejeita o plano
  ↓
[Etapa 3] Skill redige a fundamentação completa
  ↓
Usuário: recebe o texto pronto para incorporação à minuta
```

### Personalizações durante a execução

- **Esqueleto de pensamento próprio**: o usuário pode fornecer uma estrutura argumentativa própria, que será incorporada ao plano da Etapa 2 sem ser citada como fonte e sem ser convertida em tópicos numerados na redação final.
- **Controvérsias com premissa comum**: quando todas as controvérsias admitem análise conjunta, a skill as reúne em bloco único para evitar redundâncias.
- **Questões prefaciais**: gratuidade da justiça, emenda à inicial e equivalentes são tratadas antes do mérito, conforme previsto nos templates.

---

## 8. Restrições e Limites

| Restrição | Descrição |
|---|---|
| Embargos de declaração | A skill não cobre fundamentação de decisões sobre embargos de declaração, que possui skill específica. |
| Invenção de legislação | É expressamente vedado inventar ou inferir artigos, incisos ou numeração de leis. |
| Jurisprudência e doutrina externas | Vedadas, salvo quando fornecidas pelo usuário ou previstas nos templates. |
| Avanço sem checkpoint | A skill não avança da Etapa 1 para a 2, nem da 2 para a 3, sem validação explícita do usuário. |
| Documentos ilegíveis | A execução é abortada quando os documentos fornecidos estiverem corrompidos ou ilegíveis. |
