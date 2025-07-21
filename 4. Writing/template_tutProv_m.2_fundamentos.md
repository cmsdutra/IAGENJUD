# TEMPLATE FUNDAMENTAÇÃO - TUTELA PROVISÓRIA

<template_tutProv_m.2_fundamentos>

### FUNDAMENTAÇÃO

<se (houver questões prefaciais ao pedido de tutela - como recebimento de emenda, deliberação sobre gratuidade da justiça etc.)>
    
    Pendem de decisão as seguintes questões: `lista das questões pendentes, no mesmo parágrafo. Exemplo: "Pendem de decisão as seguintes questões; (i) o pedido de gratuidade da justiça; (ii) recebimento de emenda; e (iii) o pedido de tutela provisória"`

    <para (cada questão prefacial)>        
        ***[TÍTULO DA QUESTÃO PREFACIAL (MÁX. 4 PALAVRAS) - EX: GRATUIDADE DA JUSTIÇA]*** `Atenção: não inicie com "DA" ou "DO". Seja direto.`

        ``` 
        Fundamentos sobre a questão prefacial, conforme orientação do usuário e observando as regras de estilo do projeto.
        ```

        <exemplo>
        Não há elementos que infirmem a presunção de veracidade da autodeclaração de hipossuficiência econômica apresentada pela parte autora (art. 99, § 3º, CPC), razão pela qual devem lhe ser deferidos os benefícios da gratuidade da justiça.        
        </exemplo>
    </para>

    ***TUTELA PROVISÓRIA*** <!-- Atenção: o título deve ser inserido apenas se preenchida a condicional -->
</se>

Conforme relatado, a parte autora requer tutela provisória de [urgência/evidência], objetivando `descrever o provimento jurisdicional provisório pleiteado. Exemplo: "... a determinação para que a ré se abstenha de promover atos de cobrança relacionados ao título ..."`.

<switch ({tipo_tutela})> 
<!-- seleciona a fundamentação de acordo com o tipo de tutela provisória pleiteada -->
    
<case valor="urgencia")>

<!-- parágrafo introdutório padrão - tutela de urgência -->
Nos termos do art. 300 do Código de Processo Civil, a concessão da tutela provisória de urgência exige a presença, cumulativa, de elementos que evidenciem a probabilidade do direito vindicado pela parte (*fumus boni iuris*) e o perigo de dano ou risco ao resultado útil do processo (*periculum in mora*). Ademais, em regra, exige-se que a medida pleiteada seja reversível, caso haja posterior revogação da tutela provisória (§ 3º).

```
Analisar o requisito da urgência (perigo de dano ou risco ao resultado útil do processo), de acordo com as seguintes diretrizes:
- A parte autora narra situação concreta de urgência ou se trata apenas de alegação genérica?
- Ainda que haja urgência na medida, trata-se de dano iminente ou é possível a composição do contraditório e a instrução (média de 1 ano de aguardo)?
```
<!-- ATENÇÃO: a análise do requisito da urgência precede à análise da probabilidade do direito -->
<se (urgência=presente)>
    Presente o requisito da urgênica, observo ["contudo, que não"/"que também"] está presente o requisito da probabilidade do direito (*fumus boni iuris*).
    ```
    Fundamentar, em texto fluído e com estrutura lógica-argumentativa (normas e institutos aplicáveis → enquadramento do caso concreto → refutação de eventuais teses em contrário → conclusão), a presença, ou não, da probabilidade do direito, de acordo com as orientações a serem passadas pelo usuário.
    ```
<senão> <!-- se não houver urgência -->
    ```
    verificar se é caso de tutela de evidência, art. 311 do CPC: I - abuso de direito de defesa ou propósito protelatório; II - prova documental + precedente vinculante; III - ação de depósito; IV - prova documental sem contraprova que gere dúvida razoável. 
    
    - Se for caso de tutela de evidência: fazer uma análise subuntiva do caso concreto a algum dos incisos, de forma concisa, em 2 ou 3 parágrafos.
    - Se NÃO for caso de tutela de evidência: Apenas escreva: 
    """
    Não preenchido o requisito da urgência, e não sendo o caso de apreciação do pedido na forma de tutela de evidência (art. 311, CPC), a tutela deve ser indeferida sem incursão, ainda que superficial, no mérito.
    """
    ```
</se>
</case>

<case valor="evidencia">

<!-- parágrafo introdutório padrão - tutela de evidência -->
Nos termos do art. 311 do Código de Processo Civil, a tutela de evidência será concedida, independentemente da demonstração de perigo de dano ou de risco ao resultado útil do processo, quando: (i) ficar caracterizado abuso do direito de defesa ou manifesto propósito protelatório da parte contrária; (ii) as alegações de fato puderem ser comprovadas apenas documentalmente e houver tese firmada em julgamento de casos repetitivos ou em súmula vinculante; (iii) se tratar de pedido reipersecutório fundado em prova documental adequada do contrato de depósito; e (iv) a petição inicial for instruída com prova documental suficiente dos fatos constitutivos do direito do autor, a que o réu não oponha prova capaz de gerar dúvida razoável.

```
Fundamentar, de acordo com as orientações do usuário, fazendo a subsunção do caso concreto a alguma(s) da(s) hipótese(s) de concessão da tutela de evidência, observando as regras de estilo do projeto e a estrutura argumentativa progressiva e linear.
```


<default> <!-- outro tipo de tutela -->
```
**Aplicação**: liminares em MS; Ação civil pública; Tutela antecipada requerida em caráter antecedente; Indisponibilidade de bens em ação por improbidade administrativa; etc.

<levantamento_normativo>
<!-- Resumo: Faz um levantamento das normas aplicáveis para a análise da tutela provisória pleiteada -->
Ative a ferramenta `web_search` e faça um levantamento das normas relacionadas à tutela provisória requerida. Observe a atualidade da norma (verifique se não foi revogada), a relevância da fonte (preferencialmente url: "\*.gov.br", "\*.jus.br", "\*.leg.br") e a correspondência ao caso concreto. Limite-se às normas mais relevantes para a análise dos requisitos da tutela provisória (não é sobre o mérito do pedido). Armazene a resposta à consulta no placeholder {normas_aplicaveis}.

ATENÇÃO: A ativação da ferramenta `web_search` é excepcional e deve se limitar ao caso previsto neste levantamento normativo. Para o restante do template, a ferramenta deve permanecer inativa.
</levantamento_normativo>


```
Desenvolva o parágrafo inicial considerando as normas inseridas em {normas_aplicaveis}.

Em seguida, desenvolva a fundamentação de acordo com as especificidades do caso, observando as regras de estilo do projeto e a estrutura argumentativa progressiva e linear (apresentação do instituto e das normas aplicáveis → aplicação das normas no caso concreto → refutação de eventual tese em contrário → conclusão parcial).
```
<exemplo>
Nos termos do art. 7º, inc III, da Lei 12.016/2009, é possível a concessão de medida liminar em sede de mandado de segurança, sempre que relevantes os fundamentos do impetrante e haja risco de ineficácia da ordem, caso venha a ser concedida apenas ao final.  

No caso concreto, os documentos trazidos aos autos demonstram, em sede perfunctória, que ...  

...  

Não se identificam, por ora, elementos que contraindiquem a concessão da liminar, razão pela qual se reputa adequada, neste momento, a tutela provisória postulada.
</exemplo>

</default>

</switch> <!-- tipo tutela -->

<!-- Parágrafo de conclusão/síntese -->
<se (houver questões prefaciais ao pedido de tutela)>
    ***CONCLUSÃO***
    ```
    Fazer uma síntese, em até 3 parágrafos, das deliberações tomadas na decisão. Atenção: Não se trata do dispositivo da decisão; é apenas uma síntese, em texto corrido, do que foi deliberado, a fim de facilitar a compreensão da decisão pelo leitor. 
    Escreva em linguagem simples, de forma didática, mas mantenha a formalidade própria do texto jurídico.
    ```
    <exemplo>
        ***CONCLUSÃO***

        Em resumo, devem ser concedidos os benefícios da gratuidade da justiça em favor da parte autora, visto que, inexistentes elementos em sentido contrário, prevalece a presunção de veracidade da autodeclaração de hipossuficiência econômica, nos termos do art. 99, § 3º, do Código de Processo Civil. 

        Por outro lado, a tutela provisória pleiteada deve ser indeferida, pois, embora se evidencie a urgência da medida, não foram apresentados elementos suficientes para convencer, em juízo perfunctório, da probabilidade do direito vindicado na ação.         
    </exemplo>
</se>

</template_tutProv_m.2_fundamentos>