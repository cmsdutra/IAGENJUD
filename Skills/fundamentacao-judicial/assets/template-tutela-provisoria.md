# TEMPLATE FUNDAMENTAÇÃO - TUTELA PROVISÓRIA

ATENÇÃO:
- Linhas iniciadas com "//" são instruções importantes. Leia-as atentamente.
- Tags pseudo-XML, como <se/>, <loop/>, <exemplo-output>, devem ser interepretadas como meta-instruções específicas - delimitação contextual, iteração, execução condicional, entre outras. Não as interprete como texto final.

<template-tutela-provisoria>

## **FUNDAMENTAÇÃO**

Pendem de decisão as seguintes questões: ... 
// lista das questões pendentes, no mesmo parágrafo, sem quebra de linha. Exemplo: "Pendem de decisão as seguintes questões: (i) o pedido de gratuidade da justiça; (ii) recebimento de emenda; e (iii) o pedido de tutela provisória."

<loop para="cada questão pendente"> 

<se condição="houver só uma questão ou todas as questões admitirem análise conjunta">
// Redija em bloco único, sem subdivisões, observando o fluxo argumentativo definido no arquivo de regras de estilo.
</se><senão>
// Abra um tópico para cada questão, com título sintético de até 5 palavras, sem iniciar com "Da" ou "Do", no seguinte formato: "### *[TÓPICO DA CONTROVÉRSIA - EX: "GRATUIDADE DA JUSTIÇA" ou "TUTELA PROVISÓRIA"]*".
</senão>

// ATENÇÃO para os seguintes parágrafos-padrão que devem inaugurar os seguintes tópicos **de tutela provisória**:

<paragrafo-padrao tipo="tutela de urgência">
Nos termos do art. 300 do Código de Processo Civil, a concessão da tutela provisória de urgência exige a presença, cumulativa, de elementos que evidenciem a probabilidade do direito vindicado pela parte (*fumus boni iuris*) e o perigo de dano ou risco ao resultado útil do processo (*periculum in mora*). Ademais, em regra, exige-se que a medida pleiteada seja reversível, caso haja posterior revogação da tutela provisória (§ 3º).
</paragrafo-padrao>

<paragrafo-padrao tipo="tutela de evidência">
Nos termos do art. 311 do Código de Processo Civil, a tutela de evidência será concedida, independentemente da demonstração de perigo de dano ou de risco ao resultado útil do processo, quando: (i) ficar caracterizado abuso do direito de defesa ou manifesto propósito protelatório da parte contrária; (ii) as alegações de fato puderem ser comprovadas apenas documentalmente e houver tese firmada em julgamento de casos repetitivos ou em súmula vinculante; (iii) se tratar de pedido reipersecutório fundado em prova documental adequada do contrato de depósito; e (iv) a petição inicial for instruída com prova documental suficiente dos fatos constitutivos do direito do autor, a que o réu não oponha prova capaz de gerar dúvida razoável.
</paragrafo-padrao>

<paragrafo-padrao tipo="tutela provisória em procedimento especial">
// Adaptar os parágrafos-padrão do procedimento comum para as especificidades do procedimento especial em questão. Ex: Liminar em Mandado de Segurança: "Nos termos do art. 7º, inc III, da Lei 12.016/2009, é possível a concessão de medida liminar em sede de mandado de segurança, sempre que relevantes os fundamentos do impetrante e haja risco de ineficácia da ordem, caso venha a ser concedida apenas ao final."
</paragrafo-padrao>

// Após, se for o caso, inserir o parágrafo-padrão, redija a fundamentação conforme orientações dadas ou validadas pelo usuário, observando as regras de estilo. 

// No caso da **Tutela Provisória de Urgência**, inicie a análise pelo *periculum in mora* e, só se este estiver presente, passe para o exame de mérito, salvo orientação diversa do usuário.

</loop>

<exemplo-output-1>
Nos termos do art. 300 do Código de Processo Civil, a concessão da tutela provisória de urgência exige a presença cumulativa de elementos que apontem perigo de dano ou risco ao resultado útil do processo (*periculum in mora*) e a probabilidade do direito invocado (*fumus boni iuris*). Ademais, exige-se, em regra, que a medida pleiteada seja reversível (§ 3º).

No caso, o contrato aponta que a renda dedicada ao cumprimento dos encargos contratuais é exclusivamente da autora, sendo declarada em R$ 7.900,83 (sete mil, novecentos reais e oitenta e três centavos). Sem olvidar dos naturais desgastes emocionais e materiais decorrentes da perda de um cônjuge, os elementos apresentados nos autos (em especial a renda declarada em face do valor da parcela) infirmam o argumento da petição inicial de que a demora na concessão da tutela jurisdicional implicaria em inevitável inadimplemento das obrigações e perda da moradia.

Ausente o requisito da urgência, fica prejudicado o exame da probabilidade do direito.
</exemplo-output-1>

<exemplo-output-2>
Nos termos do art. 300 do Código de Processo Civil, a concessão da tutela provisória de urgência exige a presença cumulativa de elementos que apontem perigo de dano ou risco ao resultado útil do processo (_periculum in mora_) e a probabilidade do direito invocado (_fumus boni iuris_). Ademais, exige-se, em regra, que a medida pleiteada seja reversível (§ 3º).

No caso, a situação narrada pela parte autora demonstra a urgência na concessão da tutela provisória, na medida em que, de acordo com a documentação fiscal apresentada, a empresa vem recolhendo os tributos federais em quantia superior ao que entende devida, impactando, naturalmente, seu fluxo de caixa (Id. 2235769578; Id. 2235769596).

Presente o requisito da urgência, também vislumbro a probabilidade do direito invocado na petição inicial.  

Nos termos do art. 15, *caput* e § 1º, inc. III, "a", e do art. 20, inc. III, ambos da Lei nº 9.249/1995, que tratam da apuração do IRPJ e da CSLL pelo lucro presumido, depreende-se que as pessoas jurídicas que explorem, dentre outros, atividades de serviços hospitalares e de auxílio diagnóstico e terapia, desde que sejam organizados sob a forma de sociedade empresária e atendam às normas da Agência Nacional de Vigilância Sanitária - ANVISA, estão sujeitas às alíquotas diferenciadas de 8% e 12%, respectivamente.

...

No caso concreto, a parte autora demonstrou, de forma suficiente para este momento processual, que presta serviços hospitalares (realização de procedimentos cirúrgicos e atos médicos intervencionistas em ambiente hospitalar de terceiros) como sociedade empresária (Id. 2235769662; 2235769708; 2235769743). Também há elementos que indicam a regularidade de seu funcionamento perante os órgãos de fiscalização sanitária e profissional (Id. 2235769636; 2235769652; 2235769681; 2235769708).

Por outro lado, o preenchimento, ou não, de requisitos estabelecidos exclusivamente em atos infralegais — como em instruções normativas da Receita Federal — se revela irrelevante, na medida em que tais regulamentações desbordam da balizas definidas em lei. 

Destarte, reputo presentes os requisitos para a concessão da tutela provisória de urgência, nos limites delineados.
</exemplo-output-2>

</template-tutela-provisoria>