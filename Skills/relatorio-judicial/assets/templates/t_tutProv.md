# TEMPLATE DE RELATÓRIO PARA TUTELAS PROVISÓRIAS

<t_tutProv>

## **RELATÓRIO**

[AUTOR] ajuizou ação contra [RÉU], visando... 
// Síntese do objeto da ação.

Narrou, em síntese, que: ...
// Lista apenas a narrativa fática; não há, aqui, interpretação jurídica dos fatos. Listar os argumentos de fato em blocos narrativos detalhados (cada um correspondente a uma unidade contextual) em lista em números romanos com quebra de linha. Ex: (i) ... \n(ii) ... \n. Utilizar técnica de storytelling (mantendo a formalidade) para melhor esclarecimento do contexto fático da ação.

<exemplo-narrativa>
"""
Narrou, em síntese, que:

(i) em março de 2021, comprou um imóvel junto a FULANO DE TAL, localizado na ..., objeto da matrícula ...;

(ii) contudo, em julho de 2024, ao tentar celebrar um contrato de hipoteca com o banco..., descobriu que...;
...
"""
</exemplo-narrativa>

// ATENÇÃO: cada bloco narrativo deve continuar a frase inicial "narra a autora, em síntese, que ...". Não deve iniciar com verbos ou com outro "que". 

Argumentou que... 
// Síntese dos argumentos jurídicos, *preferencialmente em um único parágrafo, em texto corrido. Não utilize listas*. EXCEÇÃO: Caso haja um número elevado de argumentos (> 3), apresentar os argumentos jurídicos também em lista em números romanos, da mesma forma que os blocos narrativos.

<exemplo-output-padrao>
"""
Argumentou que a conduta do requerido afronta a boa-fé objetiva, em sua vertente da proibição do comportamento contraditório... Sustentou, ademais, que restou caracterizada a responsabilidade civil nos termos do art. 927 do Código Civil...
"""
</exemplo-output-padrao>

<exemplo-output-muitos-argumentos>
"""
Argumentou que:

(i) a conduta do requerido afronta a boa-fé objetiva, em sua vertente da proibição do comportamento contraditório...;

(ii) a Lei 10.100/2030 permite a comercialização de equipamentos para ... sem necessidade de autorização de qualquer órgão ou entidade da administração;

(iii) a jurisprudência do Supremo Tribunal Federal já se pacificou no sentido de que...

...

(x) Por fim, restou caracterizada a responsabilidade civil nos termos do art. 927 do Código Civil...
"""
</exemplo-output-muitos-argumentos>

Ao final, requer...
// Síntese, em um único parágrafo, em texto corrido e orgânico, dos pedidos principais (focar nos pedidos principais; ignorar pedido de citação, produção de prova, etc.), com foco no pedido de tutela provisória.

Deu à causa o valor de ...
// Valor da causa

Juntou documentos.
// Não é necessário especificar

<loop para="cada outro ato processual">
// Fazer uma síntese do ato, mantendo o estilo narrativo.
</loop>

Vieram os autos conclusos para decisão.

</t_tutProv>