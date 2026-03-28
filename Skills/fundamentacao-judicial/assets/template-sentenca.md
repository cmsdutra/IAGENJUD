# TEMPLATE - FUNDAMENTAÇÃO SENTENÇA

ATENÇÃO:
- Linhas iniciadas com "//" são instruções importantes. Leia-as atentamente.
- Tags pseudo-XML, como <se/>, <loop/>, <exemplo-output>, devem ser interepretadas como meta-instruções específicas - delimitação contextual, iteração, execução condicional, entre outras. Não as interprete como texto final.

<template-sentenca>

## **FUNDAMENTAÇÃO**

<se condição="não houve dilação probatória">

### *JULGAMENTO ANTECIPADO DE MÉRITO*

// desenvolva a fundamentação de indeferimento de provas pleiteadas, de acordo com as orientações do usuário (sempre citar, neste caso, o art. 370, parágrafo único, do CPC). 
// indeferidas as provas ou não havendo especificação de provas pelas partes, transcrever parágrafo padrão:

Não havendo provas a produzir e não sendo o caso de designação de alguma diligência de ofício, declaro encerrada a instrução e passo, doravante, ao julgamento antecipado de mérito, nos termos do art. 355, inc. I, do Código de Processo Civil.

</se>

### *QUESTÕES PREFACIAIS*

// seção em que serão deliberadas eventuais questões prefaciais, na seguinte ordem: questões preliminares, questões prejudiciais e questões processuais incidentais, de acordo com as orientações passadas ou validadas pelo usuário.

Não havendo questões prefaciais pendentes de apreciação, tenho por presentes as condições da ação e os pressupostos de constituição e de desenvolvimento regular do processo.

### *MÉRITO*

Extrai-se do conjunto postulatório as seguintes controvérsias de mérito: ...

// listar, em um único parágrafo, a(s) principal(is) questão(ões) de mérito controvertida(s) - Exemplo: verificar a existência de responsabilidade civil da parte ré pelos danos alegados pela parte autora e, em caso positivo, mensurar a indenização devida`.

<loop para="cada questão de mérito ou reconvenção">

<se condição="todas as questões de mérito admitem análise conjunta">
// Redija em bloco único, sem subdivisões, observando o fluxo argumentativo.
</se>

<se condição="há mais de uma questão de mérito não analisável em conjunto">
// Abra um tópico para cada questão, com título sintético de até 5 palavras, sem iniciar com "Da" ou "Do", no seguinte formato: "***[Tópico da Controvérsia - Ex: Responsabilidade Civil]***"
</se>

// Redija a fundamentação conforme orientações dadas ou validadas pelo usuário, observando as regras de estilo.

<exemplo-output>
Nos termos do art. 627 do Código Civil, "pelo contrato de depósito recebe o depositário um objeto móvel, para guardar, até que o depositante o reclame". Abrangido no conceito de guarda, inclui-se também o dever de conservação, com "o cuidado e diligência que costuma com o que lhe pertence" (art. 629), sob pena de pagamento ao depositante das equivalentes perdas e danos (art. 652), ressalvados os casos de caso fortuito ou força maior, devidamente comprovados (art. 642).

No campo específico do depósito de bens apreendidos decorrentes de fiscalização ambiental, a Lei nº 9.605/1998 sustenta que, "tratando-se de produtos perecíveis ou madeiras, serão estes avaliados e doados a instituições científicas, culturais e educacionais" (art. 25, § 3º). Ou seja, o depósito a terceiros, conquanto possível, deve ser tratado como excepcional e temporário, a fim de se evitar a deterioração natural - e previsível - do bem. 

É nesse sentido o disposto no Decreto nº 6.514/2008, que destaca a excepcionalidade do depósito do material apreendido a fiel depositário, no curso do processo administrativo, e a necessidade de destinação em tempo hábil dos materiais perecíveis.

No caso dos autos, como já adiantado na decisão que indeferiu a tutela provisória (Id. 2190008833), a madeira apreendida pelo IBAMA permaneceu sob a guarda da requerida por período superior a 17 anos, submetida a natural e deteriorização em razão da exposição ao tempo e à ação de cupins e fungos, sem que tenha havido a devida destinação definitiva do bem pelo órgão ambiental. Não há dúvida de que tal omissão contribuiu de forma decisiva para a perda do bem depositado. 

E não procede o argumento de que a requerida deveria ter comunicado previamente o risco de deterioração ou adotado medida diversa. Isso, porque o art. 25, § 3º, da Lei nº 9.605/1998, e os arts. 105 a 107 do Decreto nº 6.514/2008 constituem normas especiais que instituem um dever de diligência à administração pública, aliviando o encargo imposto ao depositário. 

Destarte, considerando as circunstâncias do caso concreto, a pretensão reipersecutória, bem como a de recebimento do valor correspondente, deve ser afastada.
</exemplo-output>

</loop> 

// Fim da fundamentação. Não avançar para o dispositivo, salvo se o usuário expressamente solicitar.

</template-sentenca>