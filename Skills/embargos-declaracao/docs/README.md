# embargos-declaracao

> Skill para elaboração assistida de minuta de decisão em embargos de declaração, conduzida em quatro etapas sequenciais com checkpoint do usuário.

**Versão**: 1.0.0  
**Licença**: [GPL 3.0](https://www.gnu.org/licenses/gpl-3.0.html)

---

## Sumário

1. [Visão geral](#visão-geral)
2. [Pré-requisitos](#pré-requisitos)
3. [Como acionar](#como-acionar)
4. [Fluxo de trabalho](#fluxo-de-trabalho)
   - [Etapa 1 — Relatório](#etapa-1--relatório)
   - [Etapa 2 — Análise](#etapa-2--análise)
   - [Etapa 3 — Plano de Argumentação](#etapa-3--plano-de-argumentação)
   - [Etapa 4 — Redação da Fundamentação](#etapa-4--redação-da-fundamentação)
5. [Estrutura de arquivos](#estrutura-de-arquivos)
6. [Templates de referência](#templates-de-referência)
7. [Regras de estilo](#regras-de-estilo)
8. [Limitações absolutas](#limitações-absolutas)
9. [Licença](#licença)

---

## Visão geral

Esta skill automatiza, com supervisão humana obrigatória, o processo de elaboração de minutas de decisão em **embargos de declaração** no âmbito da Justiça Federal.

O modelo atua como juiz federal experiente, técnico e prudente, especialista em direito processual civil. A produção da minuta é decomposta em quatro etapas sequenciais — relatório, análise, plano e redação —, cada uma entregue separadamente para revisão e aprovação antes de prosseguir.

**Princípio central**: o modelo nunca avança de etapa sem confirmação expressa do usuário. A intervenção humana não é opcional — é parte do fluxo.

---

## Pré-requisitos

Antes de acionar a skill, providencie os seguintes documentos:

| Documento | Obrigatoriedade |
|---|---|
| Decisão ou sentença embargada (com Id. do sistema) | Obrigatório |
| Petição de embargos de declaração (com Id.) | Obrigatório |
| Contrarrazões aos embargos (com Id.) | Facultativo |

Os documentos podem ser anexados diretamente ao chat ou transcritos pelo usuário. **A skill não inicia sem que ao menos os dois primeiros estejam disponíveis.**

---

## Como acionar

A skill é acionada automaticamente quando o usuário solicitar expressamente a análise, julgamento ou redação de decisão ou minuta de **embargos de declaração**.

> Exemplos de solicitações que acionam a skill:
> - "Analise e minute os embargos de declaração em anexo."
> - "Elabore a minuta de decisão para esses embargos de declaração."
> - "Julgue os embargos opostos contra a sentença Id. 000002."

Esta skill **substitui integralmente** as skills `relatorio-judicial` e `fundamentacao-judicial` quando o recurso for embargos de declaração. Não acione aquelas em paralelo.

---

## Fluxo de trabalho

```
[Usuário fornece peças]
        │
        ▼
  ┌─────────────┐
  │  Etapa 1    │  Relatório → artefato
  │  Relatório  │
  └──────┬──────┘
         │ confirmação expressa
         ▼
  ┌─────────────┐
  │  Etapa 2    │  Análise → chat
  │  Análise    │
  └──────┬──────┘
         │ confirmação + deliberações
         ▼
  ┌─────────────┐
  │  Etapa 3    │  Plano → chat
  │  Plano      │
  └──────┬──────┘
         │ confirmação expressa
         ▼
  ┌─────────────┐
  │  Etapa 4    │  Fundamentação → artefato
  │  Redação    │
  └─────────────┘
```

---

### Etapa 1 — Relatório

**Objetivo**: narrar a decisão embargada, os fundamentos dos embargos e, se houver, as contrarrazões.

**Entrega**: artefato.

O relatório segue uma estrutura narrativa interna de quatro fases (definida em `assets/template-relatorio.md`), mas é redigido em texto corrido, sem headers, seções ou marcações estruturais visíveis no produto final:

1. **Identificação do ato embargado** — tipo de ato (decisão interlocutória, sentença, acórdão), conteúdo essencial e Id. do documento.
2. **Razões dos embargos** — vícios apontados pelo embargante e fundamentos de cada alegação, com referência ao Id. dos embargos.
3. **Contrarrazões** — argumentos da parte contrária, com Id. do documento. Omitida se não houver contrarrazões.
4. **Encerramento** — frase padrão: *"Vieram os autos conclusos."*

Ao final da etapa, o modelo pergunta se o usuário deseja ajustes antes de prosseguir.

---

### Etapa 2 — Análise

**Objetivo**: verificar a admissibilidade e analisar, vício a vício, a pertinência dos embargos.

**Entrega**: chat (formato de tópicos).

A análise é estruturada em dois blocos fixos:

**2.1. Admissibilidade**
- **Tempestividade**: exame do prazo de oposição. Na ausência de informação suficiente, presume-se tempestivo.
- **Indicação de vício**: verificação se o embargante indicou, ao menos abstratamente, algum dos vícios previstos no art. 1.022 do CPC.

**2.2. Mérito**
Para cada vício alegado:
- **Alegação**: síntese do que o embargante afirma.
- **Decisão embargada**: o que a decisão disse ou deixou de dizer sobre o ponto.
- **Análise**: raciocínio ponto a ponto, com conclusão (vício existente / vício inexistente / interpretação A ou B).

Quando a existência ou ausência de vício não estiver clara — por exemplo, quando a decisão embargada for ambígua —, o modelo apresenta as interpretações possíveis e **solicita deliberação do usuário** antes de prosseguir. As escolhas feitas nesta etapa vinculam o plano e a redação subsequentes.

Ao final, o modelo solicita validação da análise.

---

### Etapa 3 — Plano de Argumentação

**Objetivo**: estruturar, em tópicos sintéticos (*skeleton-of-thought*), o raciocínio que orientará a redação da fundamentação.

**Entrega**: chat (formato de tópicos).

O plano segue a estrutura argumentativa padrão:

```
1. Admissibilidade → [tempestividade + indicação de vício]
2. Parágrafo padrão (art. 1.022 do CPC + jurisprudência do template)
3. Para cada vício alegado:
   a. Exposição da alegação do embargante
   b. Análise em face da decisão embargada [com indicação de citação direta, se aplicável]
   c. Conclusão parcial (acolhimento ou rejeição)
4. Conclusão geral
5. Dispositivo
```

O plano incorpora as deliberações tomadas pelo usuário na Etapa 2. Cada tópico corresponde a um parágrafo ou bloco na redação final.

Ao final, o modelo pergunta se o usuário deseja ajustes antes de redigir.

---

### Etapa 4 — Redação da Fundamentação

**Objetivo**: redigir a fundamentação completa da decisão com base no plano aprovado.

**Entrega**: artefato.

A fundamentação é um texto único, coeso e sem divisão em seções ou capítulos. Sua estrutura interna segue os cinco blocos definidos em `assets/template-fundamentacao.md`:

| Bloco | Conteúdo | Observação |
|---|---|---|
| 1 — Admissibilidade | Tempestividade e indicação de vício | Se os embargos não forem admitidos, o dispositivo encerra aqui |
| 2 — Parágrafo padrão | Texto fixo sobre o cabimento e os limites dos embargos (art. 1.022 do CPC) | Reprodução literal obrigatória; conteúdo imutável |
| 3 — Análise dos vícios | Um bloco por vício; citações diretas quando aplicáveis | Somente se os embargos forem admitidos |
| 4 — Conclusão | Síntese do resultado, com indicação de modificação ou manutenção do resultado anterior | Somente se os embargos forem admitidos |
| 5 — Dispositivo | `REJEITO` / `ACOLHO` / `NÃO CONHEÇO`, sob o header `## **DELIBERAÇÃO JUDICIAL**` | — |

**Citações diretas da decisão embargada**: para rejeitar alegações de omissão ou contradição, o modelo cita literal e diretamente os trechos da decisão embargada que refutam o vício, em citação destacada (recuo ou aspas), mantidos eventuais erros do original.

Antes de entregar o artefato, o modelo verifica internamente — sem exibir ao usuário — se: (a) a redação obedeceu ao plano aprovado; (b) as citações diretas são fidedignas ao texto original. Se identificar inconsistência, corrige antes de entregar.

---

## Estrutura de arquivos

```
embargos-declaracao/
├── SKILL.md                        # Definição da skill (instruções ao modelo)
├── README.md                       # Esta documentação
└── assets/
    ├── template-relatorio.md       # Template e exemplo de relatório
    └── template-fundamentacao.md   # Template de fundamentação, parágrafo padrão e dispositivos
```

---

## Templates de referência

### `assets/template-relatorio.md`

Define as quatro fases narrativas internas do relatório e fornece um exemplo completo de relatório. O modelo lê este arquivo antes de redigir a Etapa 1.

### `assets/template-fundamentacao.md`

Define os cinco blocos da fundamentação. Contém:

- **Exemplos de admissibilidade** (positiva, negativa por intempestividade e negativa por ausência de indicação de vício) com jurisprudência de referência.
- **Parágrafo padrão do art. 1.022 do CPC** (Bloco 2) — texto fixo, reproduzido literalmente em toda decisão que conheça dos embargos.
- **Modelos de dispositivo** para os quatro resultados possíveis: rejeição, acolhimento sem modificação do resultado, acolhimento com modificação do resultado e não conhecimento.

O modelo lê este arquivo antes de redigir a Etapa 4.

---

## Regras de estilo

As regras abaixo aplicam-se tanto ao relatório (Etapa 1) quanto à fundamentação (Etapa 4).

| Elemento | Regra |
|---|---|
| Nome das partes | Sempre em MAIÚSCULO |
| Função das partes | Sempre em minúsculo |
| Valores monetários e prazos | Numeral + extenso entre parênteses. Ex.: `R$ 1,00 (um real)` / `10 (dez) dias` |
| Referência a peças processuais | Citar sempre o Id. do documento. Ex.: `(Id. 000001)` |
| Citação de dispositivo legal | `art. [x]`, `inc. [x]`, `alínea [x]`, `§ 1º`, `§§ 2º e 3º` |
| Tom da fundamentação | Formal, autoritativo, voz ativa e impessoal |
| Referência ao juízo prolator | Nunca em primeira pessoa; usar formas impessoais: `"a sentença considerou que..."` |
| Parágrafos da fundamentação | Cada parágrafo = uma unidade argumentativa plena |
| Frases | Ordem direta |
| Jurisprudência e doutrina | Vedadas, salvo as previstas nos templates ou expressamente fornecidas pelo usuário |

---

## Limitações absolutas

- O modelo **não inventa, extrapola ou parafraseia** informações além do que foi fornecido.
- O modelo **não inicia** enquanto o usuário não fornecer a decisão embargada e os embargos (por anexo ou transcrição).
- O modelo **não avança** de uma etapa para outra sem confirmação expressa do usuário.
- O modelo **não cita jurisprudência ou doutrina** que não esteja prevista nos templates ou fornecida pelo usuário.
- O parágrafo padrão do art. 1.022 do CPC (Bloco 2 do template de fundamentação) é **imutável**: seu conteúdo e sua jurisprudência não podem ser alterados.

---

## Licença

Copyright (C) 2026

Este programa é software livre: você pode redistribuí-lo e/ou modificá-lo sob os termos da **GNU General Public License**, conforme publicada pela Free Software Foundation, na versão 3 da Licença, ou (a seu critério) em qualquer versão posterior.

Este programa é distribuído na esperança de que seja útil, mas **sem qualquer garantia**; sem mesmo a garantia implícita de **comerciabilidade** ou **adequação a uma finalidade específica**. Consulte a GNU General Public License para mais detalhes.

Você deve ter recebido uma cópia da GNU General Public License junto com este programa. Se não, veja <https://www.gnu.org/licenses/>.
