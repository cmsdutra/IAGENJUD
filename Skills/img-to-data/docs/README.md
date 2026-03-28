# img-to-data

Skill para transcrição fiel de documentos escaneados ou fotografados, preservando grafia, formatação e erros originais.

## Versão

1.0.0 (2026-03-28)

## Descrição

Skill desenvolvida para transcrever o conteúdo de imagens de documentos físicos digitalizados — manuscritos, formulários, certidões, contratos, laudos, atos judiciais, entre outros. Atua como bibliotecário jurídico especializado em paleografia digital, com postura de preservação histórico-cultural: nenhuma correção, normalização ou inferência é introduzida no texto transcrito.

## Quando Usar

Acione esta skill sempre que o usuário enviar imagens de documentos e solicitar:

- Transcrição ou extração de texto
- Leitura do conteúdo de digitalização ou foto de papel
- OCR ou digitalização de acervo
- Preservação de documento em suporte físico

**Palavras-chave de ativação:** "escanear", "digitalizar", "transcrever imagem", "OCR", "leitura de documento" ou termos equivalentes.

**Não utilizar** para documentos já em formato digital editável (DOCX, PDF pesquisável, HTML).

## Fluxo de Execução

```
Passo 1 — Recebimento
    └─ Confirma o recebimento e conta quantas imagens foram enviadas

Passo 2 — Agrupamento (múltiplas imagens)        [STOP → aguarda usuário]
    └─ Pergunta se as imagens formam um documento contínuo ou documentos separados

Passo 3 — Processamento em lotes
    └─ Processa no máximo 3 imagens por vez; aguarda confirmação antes de cada lote

Passo 4 — Transcrição
    └─ Produz o texto em bloco plaintext, com marcadores inline de legibilidade

Passo 5 — Controle de qualidade
    └─ Apresenta relatório estruturado por categoria
```

## Estrutura de Arquivos

```
img-to-data/
└── SKILL.md    — Prompt principal da skill
```

## Marcadores de Legibilidade

Aplicados inline, palavra a palavra ou trecho a trecho:

| Situação | Marcador |
|---|---|
| Trecho completamente ilegível | `[ilegível]` |
| Parcialmente ilegível com pista | `[ilegível - possível início: 'Re']` |
| Leitura com dúvida | `[leitura incerta: 'carezip']` |
| Duas leituras igualmente plausíveis | `[leitura dupla: 'despacho' / 'des pacto']` |
| Rasura sobre texto | `[rasura]` |
| Sobreposição de texto | `[texto sobreposto]` |
| Abreviatura expandida | `[abrev.: 'off.o' = 'officio']` |

## Elementos Gráficos

| Elemento | Placeholder |
|---|---|
| Tabela | `[tabela]` |
| Carimbo legível | `[carimbo: RECEBIDO 12/03/2024]` |
| Carimbo ilegível | `[carimbo ilegível]` |
| Assinatura | `[assinatura]` |
| Rubrica | `[rubrica]` |
| Foto/ilustração | `[foto/ilustração localizada na {posição}: {descrição objetiva}]` |

## Relatório de Controle de Qualidade

Apresentado ao final de cada transcrição. Categorias omitidas quando sem ocorrências:

- **Leituras incertas** — localização e alternativa considerada
- **Topônimos e nomes próprios** — leitura segura ou incerta
- **Abreviaturas expandidas** — convencional ou inferida por contexto
- **Elementos gráficos descritos** — confirmação de cobertura visual
- **Recomendação geral:**
  - (a) Alta legibilidade — revisão pontual suficiente
  - (b) Legibilidade média — revisão linha a linha recomendada
  - (c) Baixa legibilidade — confronto com documento físico necessário

## Limitações Absolutas

- Não corrigir, adaptar, normalizar ou completar lacunas do texto original.
- Não interpretar cenas nem identificar pessoas em elementos gráficos.
- Não reproduzir, destacar ou comentar dados sensíveis além do necessário para a transcrição fiel.
- Não processar mais de 3 imagens por lote sem confirmação do usuário.

## Licença

GNU General Public License v3.0 (GPL-3.0)

Copyright (c) 2026

Este software é fornecido sob a licença GNU General Public License v3.0. Você é livre para usar, modificar e distribuir este software, desde que cumpra os termos da licença. Qualquer trabalho derivado deve ser distribuído sob a mesma licença GPL-3.0.

As principais obrigações são: manter o aviso de copyright e licença em todas as cópias e trabalhos derivados, divulgar o código-fonte quando distribuir o software, e garantir que qualquer modificação também seja licenciada sob GPL-3.0.

Para detalhes completos, visite https://www.gnu.org/licenses/gpl-3.0.pt-br.html

O SOFTWARE É FORNECIDO "COMO ESTÁ", SEM GARANTIA DE QUALQUER TIPO, EXPLÍCITA OU IMPLÍCITA. EM NENHUM CASO OS AUTORES OU DETENTORES DOS DIREITOS AUTORAIS SERÃO RESPONSÁVEIS POR QUALQUER RECLAMAÇÃO, DANOS OU OUTRA RESPONSABILIDADE DECORRENTE DO USO DESTE SOFTWARE.
