---
name: fundamentacao-judicial
description: Redige a fundamentação de decisões judiciais (decisões interlocutórias, sentenças e tutelas provisórias). Use esta skill sempre que o usuário pedir para redigir, desenvolver ou elaborar a fundamentação de uma decisão ou sentença judicial, inclusive quando usar termos como "fundamentos", "razões de decidir", "fundamente", "redija a fundamentação", "desenvolva a argumentação" ou equivalentes. VEDADA a utilização para fundamentação de decisão sobre EMBARGOS DE DECLARAÇÃO, que possui skill própria.
license: GPL-3.0
---

# Skill: Fundamentação Judicial

Esta skill conduz a elaboração da fundamentação de sentenças e decisões judiciais, de acordo com templates e regras de estilo especificadas.

## Instruções Dinâmicas

O arquivo `/references/instrucoes-dinamicas.yaml` contém instruções importantíssimas de sistema, análise e de estilo. Sua observância é absoluta, sobrepondo-se a todas as demais no caso de conflito.

---

## FASE 00 - PREPARAÇÃO

Ao iniciar:
1. Leia atentamente as instruções dinâmicas em `sistema` e `analise` em `/references/instrucoes-dinamicas.yaml`.
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

1. Leia os documentos do processo fornecidos pelo usuário (petições, decisões, laudos, atas de audiência etc.).
2. Identifique as controvérsias relevantes para a fundamentação, separando-as por questão ou tópico.
3. Apresente a análise de cada controvérsia no formato abaixo.
4. Ao final, apresente a tabela-resumo e aguarde o checkpoint do usuário.

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

**STOP**: Após apresentar o Plano de Argumentação no formato da Etapa 2, **aguarde validação explícita do usuário antes de qualquer avanço para a Etapa 3**.

O usuário pode:
- Aceitar o plano integralmente (por exemplo: "Aprove o plano" ou "Prossiga para redação").
- Solicitar edições no plano (indique quais tópicos alterar, como reformular, ou adicione novos desdobramentos).
- Rejeitar o plano e solicitar reconstrução total.

IMPORTANTE: **Você não avança para a Etapa 3 (Redação) sem autorização expressa do usuário.** Este é um checkpoint obrigatório.

---

## Etapa 3 — Redação

**Objetivo**: redigir a fundamentação completa, observando o template aplicável, as regras de estilo e o plano de argumentação aprovado.

### Mapeamento de Templates

| Tipo de Decisão | Arquivo de Template |
|---|---|
| Sentença | `assets/template-sentenca.md` |
| Decisão Interlocutória | `assets/template-decisao-interlocutoria.md` |
| Tutela Provisória | `assets/template-tutela-provisoria.md` |

Orientações:

1. Antes de iniciar a redação, carregue e leia atentamente as regras de estilo definidas em `/references/regras-de-estilo.md`, as instruções dinâmicas de `estilo` no arquivo `/references/instrucoes-dinamicas.yaml`, e o template correspondente ao tipo de decisão (ver mapeamento acima).

2. Siga a estrutura do template, preenchendo cada bloco conforme as instruções nele contidas, observando as regras de estilo e o plano de argumentação aprovado na Etapa 2, utilizando-o como guia para cada parágrafo, sem citá-lo como fonte.

9. Antes de entregar a resposta ao usuário, faça uma reflexão silenciosa, certificando-se de que a redação obedeceu as regras de estilo e o plano de argumentação, bem como as regras negativas e as restrições da skill. Caso não tenha obedecido, faça os ajustes necessários.

Produza o texto da fundamentação em prosa corrida, conforme o template. Não inclua marcações de template, comentários ou instruções do SKILL.md na saída final. O texto deverá ser entregue  pronto para incorporação à minuta.

---

## Notas de Comportamento

- IMPORTANTE: as instruções dinamicas (`/references/instrucoes-dinamicas`) têm prevalência sobre todas as demais. Leia-as atentamente de acordo com as etapas de execução.
- Se o usuário fornecer um "esqueleto de pensamento", arquivo-modelo ou estrutura argumentativa própria, incorpore-a ao plano (Etapa 2) sem citá-la como fonte e sem transformá-la em tópicos numerados na redação.
- Se todas as controvérsias compartilharem a mesma solução ou premissa fático-jurídica, reúna-as em bloco único para evitar redundâncias, desde que não haja prejuízo à estrutura lógica.
- Questões prefaciais (gratuidade da justiça, emenda à inicial etc.) devem ser tratadas antes do mérito ou do pedido de tutela, conforme previsto nos templates.