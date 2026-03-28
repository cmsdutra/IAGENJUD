# TEMPLATE - FUNDAMENTAÇÃO DE DECISÃO INTERLOCUTÓRIA

ATENÇÃO:
- Linhas iniciadas com "//" são instruções importantes. Leia-as atentamente.
- Tags pseudo-XML, como <loop /> e <se />, são, respectivamente, para iteração e execução condicional do bloco de instruções que estão nela contidas. Não as interprete como texto final.

<template-decisao-interlocutoria>

## **FUNDAMENTAÇÃO**

// Resumo inicial das questões pendentes de análise  
Pende[m] de decisão a[s] seguinte[s] questão[ões]:  
// Lista das questões pendentes, no mesmo parágrafo, com marcação por numerais romanos em minúsculo, entre parênteses. Exemplos: "(i) pedido de repetição da perícia judicial, ao fundamento de ... (Id. ...); (ii) pedido de juntada de prova emprestada (Id. ...); (ii) o pedido de Id. ... , formulado por ..., para cancelamento da penhora".  
// ATENÇÃO → Questões que podem ser analisadas sob os mesmos fundamentos, ou seja, mesma premissa fático-jurídica, devem ser reunidas em apenas um tópico, a fim de evitar redundâncias, desde que não haja perda para a estrutura lógica do raciocínio

<loop para="cada questão pendente">

<se condição="houver mais de uma questão pendente">
*[TÍTULO QUE SINTETIZA A QUESTÃO A SER DECIDIDA (MÁX 5 PALAVRAS)]*  
// Não inicie o título da seção com "DA" ou "DO". Seja direto. Exemplo: "*REPETIÇÃO DA PERÍCIA JUDICIAL*".
</se> 

// Deliberação sobre a questão, de acordo com as orientações do usuário e as regras de estilo, observando a estrutura lógica de argumentação.

// Sempre que referenciar algum documento dos autos, ainda que de forma indireta, mencione o respectivo Id. . Observe, como parâmetro, as regras de citação indireta da ABNT. Observe o exemplo abaixo.

<exemplo-output>
Os documentos acostados nos autos demonstram que o autor se aposentou em 2008 (Id. 90490490) e foi contratado pelo réu no ano seguinte (Id. 9049491).

Ademais, em audiência (Id. 1000001), ficou demonstrado que a contratação ocorreu com a ciência da aposentadoria do autor, o que revela possível conduta fraudulenta.
</exemplo-output>
</loop>

</template-decisao-interlocutoria>