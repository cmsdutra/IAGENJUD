# Template e Estilo — Relatório Judicial

## Tom e Estilo Geral

- Técnica de **storytelling jurídico**: ênfase no conflito e na controvérsia a ser apreciada.
- Linguagem técnica, sem dramatização ou adjetivação excessiva.
- Neutralidade descritiva rigorosa.
- Tom técnico-formal com uso preciso dos conceitos jurídicos pertinentes.
- Cada parágrafo deve conter uma unidade de ideia, com transição fluída em relação ao parágrafo anterior.
- Priorização da fidelidade factual aos documentos fornecidos.

---

## Formato do output

O relatório é **texto corrido**, e não se subdivide em seções ou com separador visual. 
Ressalvado o título do relatório ('# **RELATÓRIO**'), o modelo **não deve** inserir nenhum elemento de estrutura (como `##`, `###`, `---`, negrito em subtítulos, etc.) no texto final entregue ao usuário. 
Antes de redigir, consulte o **texto de exemplo** relacionado ao tipo de minuta para calibrar o nível de detalhe e o estilo narrativo esperados.

### Textos de Exemplo

Os textos de exemplo fornecidos são os seguintes:

| Nível de Detalhe | Tipos Comuns de Minuta (rol exemplificativo) | Arquivo de Referência |
| --- | --- | --- |
| Detalhado | Sentença, Saneamento, Tutela Provisória | `/assets/exemplos/ex-rel-completo.md` |
| Conciso | Interlocutórias comuns, despachos, decisão sobre incidentes processuais | `/assets/exemplos/ex-rel-conciso.md` |

Identifique o texto de exemplo utilizado de acordo com o tipo de minuta pretendido. Se houver dúvida, pergunte ao usuário antes de escolher. 

---

## Regras de Formatação

Status: IMPORTANTE. Se sobrepõem aos exemplos.

| Elemento | Regra |
|---|---|
| Nomes das partes | MAIÚSCULAS, sem negrito |
| Negrito | Vedado, salvo os previstos nos templates |
| Itálico | Somente para palavras e expressões estrangeiras |
| Números e valores | Numeral seguido do extenso entre parênteses — Ex.: `12 (doze) anos`, `R$ 2,00 (dois reais)`, `15% (quinze por cento)` |
| **Exceção** ao extenso | Datas e valores inseridos em estruturas complexas (tabelas) dispensam o extenso |
| Citações | Somente indiretas, incorporadas ao argumento (*inline*), sem aspas. Citação direta é vedada. |
| Id. dos atos | Todo ato processual citado (exceto petição inicial) deve ter o número de Id. indicado, mesmo em citação indireta |

---

## Template Estrutural

Selecione o template na pasta `/assets/templates/` que melhor se relacione com o caso em questão, observando o seguinte:

| Tipo de Minuta | Template |
| --- | --- |
| Sentença ou Saneamento | `t_sentenca.md` |
| Tutela provisória | `t_tutProv.md` |
| Interlocutória Geral | `t_interlocutoria.md` |

Selecione o template com maior correspondência se o tipo de minuta no caso concreto não corresponder exatamente a nenhum dos tipos de minuta pré-definidos acima.

Ao ler o template, assuma que:
- O texto iniciado com "//" são blocos de instrução. Leia-os atentamente e não os reproduza na resposta. 
- o template utiliza tags pseudo-xml para instruções estruturais específicas (como <loop/>) e delimitação de contexto (como <exemplo/>). Não as exiba no texto final.