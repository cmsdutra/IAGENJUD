# Relatório Judicial

Skill para elaboração de relatórios de processos judiciais no padrão da Justiça Federal.

## Versão

1.1.0 (2026-03-07)

## Descrição

Skill desenvolvida para redigir relatórios que compõem a seção introdutória de decisões judiciais — sentenças, saneamentos, tutelas provisórias e decisões interlocutórias. O relatório apresenta narrativa estruturada dos fatos processuais, extraída das peças fornecidas pelo usuário, com postura de juiz federal da 1ª Região: prudente, técnico, minucioso e estritamente imparcial.

## Quando Usar

Acione esta skill ao solicitar a redação, elaboração ou produção de relatório judicial, relato de processo, narrativa processual ou qualquer seção introdutória de decisão interlocutória, tutela provisória ou sentença. Também é acionada quando o usuário fornece peças processuais (petição inicial, contestação, réplica, despachos, decisões anteriores) e pede que o conteúdo seja consolidado em um relatório.

**Exceção:** não utilizar para relatório de embargos de declaração.

## Fluxo de Execução

A skill segue três passos obrigatórios:

**Passo 1 — Identificar o tipo de minuta**
Antes de redigir qualquer conteúdo, a skill pergunta para qual tipo de minuta servirá o relatório:
1. Sentença ou Saneamento
2. Tutela provisória (urgência ou evidência)
3. Decisão interlocutória

A redação não se inicia sem resposta expressa do usuário.

**Passo 2 — Coletar o material processual**
A skill confirma quais peças foram fornecidas. Se faltar material essencial, avisa o usuário em vez de especular.

**Passo 3 — Redigir o relatório**
O relatório é produzido como texto corrido, sem headers, títulos de seção, separadores ou marcação estrutural visível — apenas o título `# **RELATÓRIO**` é mantido. Os templates e exemplos guiam o nível de detalhe, a ordem narrativa e o estilo.

## Estrutura de Arquivos

```
relatorio-judicial/
├── SKILL.md                         — Prompt principal da skill
├── README.md                        — Este arquivo
├── references/
│   └── estilo.md                    — Regras de estilo e formatação (leitura obrigatória antes de redigir)
└── assets/
    ├── templates/
    │   ├── t_sentenca.md            — Template: Sentença ou Saneamento
    │   ├── t_tutProv.md             — Template: Tutela provisória
    │   └── t_interlocutoria.md      — Template: Decisão interlocutória
    └── exemplos/
        ├── ex-rel-completo.md       — Exemplo detalhado (sentença, saneamento, tutela provisória)
        └── ex-rel-conciso.md        — Exemplo conciso (interlocutórias, despachos, incidentes)
```

## Templates

| Tipo de Minuta | Template |
|---|---|
| Sentença ou Saneamento | `t_sentenca.md` |
| Tutela provisória | `t_tutProv.md` |
| Interlocutória geral | `t_interlocutoria.md` |

O template com maior correspondência é selecionado quando o caso concreto não se enquadra exatamente em nenhum dos tipos pré-definidos. Os templates utilizam blocos de instrução `//` e tags pseudo-xml (`<fase>`, `<loop>`, `<se>`, `<checkpoint>`, `<exemplo>`) para estruturar a redação internamente — nenhum desses elementos é reproduzido no texto final.

## Exemplos de Referência

| Nível de Detalhe | Tipos Comuns de Minuta | Arquivo |
|---|---|---|
| Detalhado | Sentença, Saneamento, Tutela Provisória | `assets/exemplos/ex-rel-completo.md` |
| Conciso | Interlocutórias, despachos, incidentes processuais | `assets/exemplos/ex-rel-conciso.md` |

## Limitações Absolutas

- Não criar, extrapolar, parafrasear ou inventar informações além do que foi fornecido nas peças.
- Não realizar pesquisas externas de jurisprudência, doutrina ou legislação.
- Não citar jurisprudência salvo se o usuário forneceu o texto completo ou a identificação exata (número do processo, tribunal e ementa).
- Não inferir jurisprudência a partir de menções genéricas nas peças processuais.
- Não informar data de protocolo de petições ou atos judiciais, salvo se relevante para a solução da controvérsia.
- Não questionar o usuário sobre fundamentação ou dispositivo — o escopo da skill é exclusivamente o relatório.
- Não utilizar para relatório de embargos de declaração.

## Licença

GNU General Public License v3.0 (GPL-3.0)

Copyright (c) 2026

Este software é fornecido sob a licença GNU General Public License v3.0. Você é livre para usar, modificar e distribuir este software, desde que cumpra os termos da licença. Qualquer trabalho derivado deve ser distribuído sob a mesma licença GPL-3.0.

As principais obrigações são: manter o aviso de copyright e licença em todas as cópias e trabalhos derivados, divulgar o código-fonte quando distribuir o software, e garantir que qualquer modificação também seja licenciada sob GPL-3.0.

Para detalhes completos, visite https://www.gnu.org/licenses/gpl-3.0.pt-br.html

O SOFTWARE É FORNECIDO "COMO ESTÁ", SEM GARANTIA DE QUALQUER TIPO, EXPLÍCITA OU IMPLÍCITA. EM NENHUM CASO OS AUTORES OU DETENTORES DOS DIREITOS AUTORAIS SERÃO RESPONSÁVEIS POR QUALQUER RECLAMAÇÃO, DANOS OU OUTRA RESPONSABILIDADE DECORRENTE DO USO DESTE SOFTWARE.
