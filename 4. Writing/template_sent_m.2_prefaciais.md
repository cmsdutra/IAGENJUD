# TEMPLATE QUESTÕES PREFACIAIS - SENTENÇA

<template_sent_m.2_prefaciais>

<prefaciais>

### QUESTÕES PREFACIAIS

<checkpoint id="prefaciais_integral">
    Certifique-se de redigir integralmente as três subseções obrigatórias a seguir:  
    (i) Questões Preliminares: <preliminares />;  
    (ii) Prejudiciais de Mérito: <prejudiciais />;  
    (iii) Atividade Probatória: <atividade_probatoria />.
    Todas devem ser redigidas mesmo que apenas para declarar sua inexistência.
</checkpoint>




<!-- QUESTÕES PRELIMINARES -->
<preliminares>

#### QUESTÕES PRELIMINARES

<se (não houver preliminares a analisar)>

    Não há questões preliminares pendentes de apreciação. Estão presentes as condições da ação e os pressupostos de constituição e de desenvolvimento regular do processo.

<senão> <!-- se houver preliminares -->
    
    Pendem de deliberação a(s) seguinte(s) questão(ões) preliminar(es): `listar, em um parágrafo, em texto corrido, as preliminares suscitadas pelas partes e que estejam pendentes de apreciação`
    
    <para (cada preliminar pendente)> 
        <!-- A ordem de análise deve ser a seguinte: competência → pressupostos processuais de existência e de validade → condições da ação (legitimidade e interesse de agir) → demais questões preliminares -->

        ***[NOME DA PRELIMINAR 1 - Ex: INCOMPETÊNCIA DO JUÍZO]:***
        ```
        Apresentar fundamentação sobre a preliminar, de acordo com as orientações do usuário, seguindo a seguinte linha argumentativa padrão: (apresentação do instituto e normas jurídicas aplicáveis → aplicação no caso concreto → refutação de eventuais teses em contrário → conclusão parcial). 

        Se for pelo afastamento da preliminar, a fundamentação deve ser objetiva, em poucos parágrafos (em média, 3 parágrafos); Se for pelo acolhimento, com extinção do processo, a fundamentação deverá ser a mais completa possível, observando a linha argumentativa definida para fundamentação de mérito e as orientações do usuário.

        Não divida em novas subseções. Apresente um texto corrido, com argumentação completa, observadas as regras de estilo do projeto.
        ```

        <se (acolheu a preliminar e extinguiu o processo)>
            <!-- Se o acolhimento for parcial, e não houver extinção do processo, não é necessário seguir este fluxo condicional -->

            Diante do acolhimento da preliminar de [nome_da_preliminar], deve o feito ser extinto sem resolução do mérito, nos termos do art. 485, inc. [inciso_correspondente], do CPC.

            `BREAK: Interromper a execução do template de prefaciais.`
        <senão> <!-- rejeitou a preliminar ou acolheu sem extinguir o processo -->
            Assim, deve ser [rejeitada/acolhida] a preliminar arguida `se for acolhida, especificar`.
        </se>    
    </para>
</se>
</preliminares>




<prejudiciais>

#### PREJUDICIAIS DE MÉRITO

<se (não houver prejudiciais de mérito pendentes de apreciação)>

    Não há questões prejudiciais de mérito pendentes de apreciação.

<senão> <!-- se houver prejudicial pendente de análise -->
    
    <para (cada questão prejudicial pendente)> 
        <!-- A ordem de análise deve ser a seguinte: transação → renúncia a direito sobre o qual se funda a ação → fatores externos que impedem ou extinguem direito do autor → prescrição e decadência -->

        *[NOME DA PREJUDICIAL 1 - Ex: PRESCRIÇÃO]:***
        ``` 
        Apresentar fundamentação sobre a prejudicial, de acordo com as orientações do usuário, seguindo a seguinte linha argumentativa padrão: (apresentação do instituto e normas jurídicas aplicáveis → aplicação no caso concreto → refutação de eventuais teses em contrário → conclusão parcial). 

        Se for pelo afastamento da prejudicial, a fundamentação deve ser objetiva, em poucos parágrafos (em média, 3 parágrafos); Se for pelo acolhimento, com extinção do processo, a fundamentação deverá ser a mais completa possível, observando a linha argumentativa definida para fundamentação de mérito e as orientações do usuário.

        Não divida em novas subseções. Apresente um texto corrido, com argumentação completa, observadas as regras de estilo do projeto.
        ```

        <se (acolheu a prejudicial e extinguiu o processo)>
            <!-- Se o acolhimento for parcial, e não houver extinção do processo, não é necessário seguir este fluxo condicional -->

            Diante do acolhimento da prejudicial de [nome_da_prejudicial], deve o feito ser extinto com resolução do mérito, nos termos do art. 487, inc. [inciso_correspondente], do CPC.

            `BREAK: Interromper a execução do template de prefaciais.`
        <senão> <!-- se rejeitada a preliminar ou acolhida sem extinguir -->
            Assim, deve ser [rejeitada/acolhida] a prejudicial arguida `se for acolhida, especificar`.
        </se>
    </para>
</se>
</prejudiciais>




<atividade_probatoria>

#### ATIVIDADE PROBATÓRIA

<se (não houver pedido de produção de provas pendente de análise)>
    As partes não especificaram provas a produzir, tampouco entendo necessária, ou viável, a determinação de alguma diligência adicional de ofício, razão pela qual declaro encerrada a fase probatória e passo doravante ao exame antecipado de mérito, nos termos do art. 355, inc. I, do Código de Processo Civil.
<senão> <!-- se houver pedido de produção de provas pendente de análise -->
    `Realizar a análise do pedido conforme orientação do usuário.`
</se> 

</atividade_probatoria>

</prefaciais>

</template_sent_m.2_prefaciais>
