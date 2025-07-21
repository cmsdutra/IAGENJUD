# TEMPLATE RELATÓRIO - SENTENÇA

<template_sent_m.1_relatorio>

<!-- Confirmação de leitura dos documentos -->
<reading>

Antes de iniciar a escrita do relatório, certifique-se de que todos os documentos anexados foram **lidos integralmente**, sem qualquer truncamento. 
    - Durante essa leitura prévia, mapeie cada documento pelo respectivo Id, natureza (petição, despacho, laudo etc.) e conteúdo essencial. 
    - A análise de cada documento deve ocorrer apenas após sua leitura completa, sem antecipações nem inferências sobre trechos ainda não processados.
IMPORTANTE: Se houver truncamento da leitura dos documentos, pare imediatamente a execução e solicite ao usuário que apresente em fragmentos menores, a fim de garantir a leitura integral.

<checkpoint id=geral> 
Só prossiga para as fases posteriores após certificada a leitura integral dos documentos.
Registre ao usuário, em bloco de código:
```txt
Confirmação de leitura dos documentos: [sim/não]
[Justifique, caso a resposta seja "não"].
```
</checkpoint>
</reading>

<!-- Certificada a leitura integral dos documentos, conforme fase <reading>...</reading>, inicie a fase de redação <writing>...</writing> -->

<writing>

### RELATÓRIO

<fase id=postulatória>
<!-- A narrativa deve seguir estritamente a ordem cronológica dos atos, salvo exceções justificadas no próprio template (ex: decisões posteriores que repercutem no ato anterior) -->

`AUTOR` ajuizou ação contra `RÉU`, visando... `síntese do objeto da ação`.

```
Apresente os blocos narrativos detalhados (cada um correspondente a uma unidade contextual completa) em lista em números romanos, com quebra de linha.  
    - Inicie com "Narrou [o autor/a autora ...], em síntese, que:"
    - Aplicar técnicas de storytelling formal, especialmente para a conexão entre os blocos narrativos e destaque do conflito.
    - Listar apenas os fatos puros; não apresente, neste momento, os argumentos jurídicos (interpretação jurídica dos fatos). 
<exemplo descicao="blocos narrativos">
Narrou o autor, em síntese, que:
(i) em 20 de janeiro de 2020, prestou concurso público para o cargo de... e, ao final, ficou classificado em 2º lugar. \n <!-- unidade contextual completa → da prestação do concurso ao resultado -->
(ii) ocorre que, em março de 2021, soube da nomeação do candidato aprovado em 3º lugar, sem que ele, o autor, tivesse sido convocado; \n. <!-- idem -->
...
</exemplo>
```
<!-- argumentos jurídicos da inicial -->
Argumentou que... `síntese dos argumentos jurídicos (interpretação jurídica dos fatos), em um mesmo parágrafo, em texto corrido e coeso (storytelling formal).`

<exemplo descricao="argumentos jurídicos">
...
Argumentou que o fato apresentado caracteriza preterição indevida de candidato, fazendo surgir seu direito líquido e certo à nomeação, conforme jurisprudência do Supremo Tribunal Federal (...).
</exemplo>

Ao final, requereu... `enumeração dos pedidos principais (ignorar pedido de citação, produção de prova, etc.), em um mesmo parágrafo`.  

Deu à causa o valor de R$ ... ([valor por extenso])  

Juntou documentos. <!-- não é necessário especificar os documentos juntados -->   

<!-- atos intercorrentes na fase postulatória -->
```
SE (houver decisão inicial) → enumere as deliberações, em um único parágrafo, em texto corrido. Inicie com: "A decisão de Id. XXXXX (deliberações)...". Ignore determinações meramente processuais, como citação, intimação etc.
    SE (houver recurso) → indicar a interposição/oposição do recurso, o número e, se for o caso, o resultado apresentado. Apresente o resultado do recurso neste momento, ainda que a informação esteja adiante no processo <!-- exceção à ordem cronológica do fluxo narrativo principal -->

SE (houver ata de audiência de conciliação) → informe, resumidamente, o resultado da audiência. Ex: "Tentativa de conciliação restou infrutífera (Id. [ID da ata])" ou "As partes chegaram em um acordo, nos seguintes termos: ...". Se houve acordo, resumir os atos de cumprimento ou descumprimento.
```
<para (cada contestação)>

Em contestação (Id. ...), o réu alega, em síntese, que...
```
Síntese dos argumentos de fato e de direito da contestação, em um único parágrafo, em texto corrido, se houver até 2 argumentos. **Se a contestação for extensa (mais de dois argumentos), utilize lista numerada, com quebra de linha**.
Sempre apresente os fundamentos da contestação na seguinte ordem: incompetência → preliminares → prejudiciais → fatos extintivos ou impeditivos → defesa direta → fatos modificativos. 
<exemplo descricao="contestação concisa (≤ 2 argumentos)">
Em contestação (Id. 100005), o réu alega, em síntese, que a pretensão de cobrança já está extinta pela prescrição, tendo em vista que... <!-- prejudicial -->. Ademais, ainda que não estivesse extinta, não há provas do inadimplemento imputado ao defendente... <!-- defesa direta -->
</exemplo>
<exemplo descricao="contestação extensa (> 2 argumentos)">
Em contestação (Id. 100006), o réu alega, em síntese, que:  
(i) o Juizado Especial Federal é incompetente para o julgamento do feito, visto que, a despeito de o valor da causa ser inferior a 60 salários-mínimos, a pretensão envolve o cancelamento de ato administrativo...;  <!-- exceção de incompetência -->
(ii) é parte ilegítima para compor o polo passivo, visto que ...;  <!-- prelimianr -->
(iii) a pretensão de cobrança já está extinta pela prescrição, tendo em vista que...;  <!-- prejudicial -->
(iv) embora o autor não tenha mencionado, houve novação da dívida por meio da celebração de acordo extrajudicial...;  <!-- fato extintivo -->
(v) não há provas do inadimplemento imputado ao defendente...;  <!-- defesa direta -->
(vi) ainda que se reconheça o débito e a situação de inadimplência, deve-se considerar que...;   <!-- fato modificativo -->
...
</exemplo>
```
Ao final, requer `síntese dos pedidos do réu, em um parágrafo, em texto corrido (ordem: incompetência → preliminares → prejudiciais → fatos extintivos ou impeditivos → defesa direta → fatos modificativos)`.

`Não mencionar, por ora, eventual reconvenção. Eventuais reconvenções serão narradas adiante, em estrutura própria, dada sua natureza jurídica de ação.`
</para>

<se (houver réplica(s))> Apresentada(s) réplica(s) à(s) contestação(ões) (Id. ... [; ...]), em que o autor... `breve síntese dos argumentos` </se>

<!-- fluxo de reconvenção -->
<se (houver reconvenção(ões))>

```
Considerando que a reconvenção é uma espécie de ação autônoma ajuizada pelo réu em face do autor no mesmo processo da ação original, o fluxo narrativo da(s) reconvenção(ões) apresentada(s) seguirá o mesmo da fase postulatória, apenas ajustando os termos.
<exemplo descricao="reconvenção">
Além de contestar o pedido autoral, o réu ajuizou reconvenção (Id ...), visando... <!-- mesma estrutura da PETIÇÃO INICIAL -->
...
Deu à reconvenção o valor de R$ ... ([valor por extenso]).
...
Intimado, o autor contestou o pedido reconvencional (Id ...), arguindo, em síntese, que... <!-- mesma estrutura da CONTESTAÇÃO -->
...
O réu apresentou réplica em relação à reconvenção (Id. ...).
</exemplo>
```
</se>

```
Inserir eventuais atos processuais não previstos neste template na ordem cronológica, mantendo o fluxo narrativo.
```
<!-- --------------- ENCERRAMENTO DA FASE POSTULATÓRIA --------------- -->
<checkpoint id=postulatória> 
    Certifique-se de que todas as petições da fase postulatória (petição inicial, contestação, réplica, reconvenção e incidentais) e decisões iniciais (tutela provisória etc.) foram integralmente lidas, processadas e relatadas antes de prosseguir para os atos de saneamento. ATENÇÃO: Caso haja alguma inconsistência, corrija antes de prosseguir.
</checkpoint>
</fase>

<especificacao_provas>

```
Verificar se, nas petições anteriores (durante todo a fase postulatória), as partes especificaram provas a produzir (além da prova documental). Ex: oitiva de testemunhas, laudo pericial, etc. 
    - EM CASO POSITIVO → apresentar uma breve síntese: "Durante a fase postulatória, houve o pedido de produção das seguintes provas, além das provas documentais: (i)...; (ii)...; ..."
    - EM CASO NEGATIVO, apenas relatar: "As partes não especificaram outras provas a produzir, além das que já compõem os autos."

ATENÇÃO: **não são** especificações de prova:
    - Protestos genéricos (Ex: "protesta provar o alegado por todo meio de prova em direito admitido" ou frase similar)
    - Pedidos de juntada de documento.
```
</especificacao_provas>

<!-- ---------------- FASE DE SANEAMENTO ---------------- -->
<fase id=saneamento>
<se (houver decisão de saneamento)>

```
Neste ponto, resumir todas as deliberações realizadas em decisão de saneamento e organização do processo (solução de questões processuais pendentes, delimitação das controvérsias de fato e de direito, distribuição do ônus da prova, provas admitidas, nomeações de perito, designações de audiência etc.). Inicie por: "Em decisão de saneamento (Id. ...), ..."

Informar, de forma breve, eventuais detalhes adicionais, como a realização de audiência prévia, pedidos de ajustes, etc., mantendo o fluxo narrativo.
```
</se>

<!-- ----- ENCERRAMENTO DA FASE SANEADORA ----- -->
<checkpoint id=saneamento> 
Verifique se todas as decisões e manifestações relacionadas ao saneamento (inclusive delimitação de controvérsias, ônus da prova e designação de audiência) foram analisadas antes de passar à instrução. Caso haja alguma inconsistência ou omissão, corrija antes de prosseguir.
</checkpoint>
</fase>

<!-- --------------- FASE DE INSTRUÇÃO --------------- -->
<fase id=instrução>
<se (houver produção de provas não documental - perícia, oitiva de testemunhas etc.)>

```
Relate detalhadamente as provas produzidas durante a fase instrutória, como oitiva de testemunhas, perícias, inspeções etc., indicando os respectivos Id. Exemplo: "Em audiência realizada no dia 19/02/2025 (Id. [ID da ata]), foram ouvidas as testemunhas JOÃO, ALICE e MARIA.", "Realizada a perícia, o laudo foi apresentado aos autos no dia 19/02/2025 (Id. [ID do laudo]). A conclusão do exame pericial foi no sentido de que...".

Informar se houve alegações finais, indicando, se for o caso, o respectivo Id. Exemplo: "As partes apresentaram alegações finais (Id. ...; ...)."
```
</se>

<!-- ----- ENCERRAMENTO DA FASE INSTRUTÓRIA ----- -->
<checkpoint id=instrução> 
Certifique-se de que todos os atos de instrução (provas produzidas, laudos, audiências, manifestações complementares) foram processados e relatados antes de encerrar o relatório. Caso haja alguma inconsistência ou omissão, corrija antes de prosseguir.
</checkpoint>
</fase>

<!-- Conclusão -->
Vieram os autos conclusos para julgamento.
É o relatório. **Passo a decidir**.

<checkpoint id=final> 
Certifique-se de que todas as fases foram corretamente processadas (postulatória, saneamento, instrução) e que não restam pendências narrativas antes de encerrar o relatório. 
</checkpoint>

</writing>
</template_sent_m.1_relatorio>