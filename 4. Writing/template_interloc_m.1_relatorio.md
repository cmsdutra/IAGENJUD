# RELATÓRIO PARA DECISÃO INTERLOCUTÓRIA

<template_interloc_m.1_relatorio>

### RELATÓRIO

<!-- introdução -->
<se (disponível informação sobre o objeto da ação)>
    Cuida-se de ... `descrever a ação, as partes e o objeto principal, com uma breve síntese dos fundamentos apresentados`
</se>

<!-- iteração -->
<para (cada petição/ato judicial/certidão/parecer/laudo/documento/outro apresentado)>

    ```
    Em ordem cronológica, faça uma síntese objetiva da peça processual ou do documento, indicando quem juntou, o Id. e o conteúdo. Se for petição, detalhar os fundamentos e pedidos; se for ato judicial, detalhar as deliberações e fundamentos. Escreva em ordem cronológica, de forma orgânica, em texto fluído, com técnicas de storytelling (mantendo a formalidade), e observando as regras de estilo do projeto (em especial o campo `regras_para_relatorio`).
    ```
    <exemplo id=1>
        """
        Cuida-se de ação movida por JOÃO DA SILVA em face de JOSÉ DA SILVA, visando à condenação do requerido ao pagamento de indenização por danos morais, no valor de R$ 10.000,00 (dez mil reais).  

        Após a apresentação de contestação pelo requerido (Id. ...), o autor veio aos autos pleitear o compartilhamento da prova produzida em ação semelhante na 2ª Vara Federal desta Seção Judiciária (Autos ...). Argumenta, para tanto, que o compartilhamento de provas é permitido pelo CPC (art. ...) e prestigia a celeridade e economia processual, além de não afrontar a ampla defesa e contraditório, tendo em vista que a parte ré é a mesma nesta e naquela ação (Id. ...).  

        Intimado, o réu não se opôs ao pedido, ressaltando, contudo, a necessidade de abertura de vista para manifestação (Id. ...).
        """
    </exemplo>

    <se (houver processamento paralelo)>
        ```
        Exemplos de processamento paralelo:
            - Atos de cumprimento de tutela provisória (bloqueio e desbloqueio de bens, deliberação sobre impenhorabilidade etc.)
            - Incidentes processuais destacados da questão principal (como IRDR, habilitação de herdeiros etc.)
        
        **Excepcionalmente**, na hipótese de processamento paralelo e **não havendo compometimento** da clareza da estrutura narrativa geral, utilize o critério tópico-cronológico, de modo a reunir em tópicos próprios, cada uma das estruturas narrativas paralelas.
        ```
        <exemplo id=2>
            """
            Cuida-se de ação movida por LUCAS SILVA em face da UNIÃO, do ESTADO DO TOCANTINS e do MUNICÍPIO DE PALMAS, visando à determinação para que os requeridos forneçam ao autor o medicamento FINGOLFIM, de acordo com prescrição de sua médica assistente.  

            Argumenta, em síntese, que o medicamento tem registro na AVISA, mas não foi incorporado ao SUS pela CONITEC. Contudo, trata-se de medicamento imprescindível para o tratamento de sua moléstia, conforme ressaltado nos documentos médicos que acompanham a inicial. Ademais, sustenta que o valor do medicamento - R$ .... - é incompatível com sua renda familiar, impondo-se ao Poder Público seu fornecimento, com fulcro no art. 196 da Constituição da República.  

            A tutela provisória foi deferida, com a determinação para que os requeridos fornecessem o medicamento no prazo de 10 (dez) dias (Id. 10000123).  

            Após apresentação de contestação pela UNIÃO (Id. 10000124), o autor veio aos autos pleitear o compartilhamento da prova produzida em ação semelhante na 2ª Vara Federal desta Seção Judiciária (Autos ...). Argumenta, para tanto, que o compartilhamento de provas é permitido pelo CPC (art. ...) e prestigia a celeridade e economia processual, além de não afrontar a ampla defesa e contraditório, tendo em vista que a parte ré é a mesma nesta e naquela ação (Id. ...).  

            ...  

            ##### *CUMPRIMENTO DA TUTELA PROVISÓRIA*  
            Como visto, foi concedida a tutela provisória, determinando que os requeridos fornecessem, em regime de solidariedade, o medicamento pleiteado pelo autor, no prazo de 10 (dez) dias (Id. 10000123).  

            Como não houve cumprimento espontâneo da tutela provisória, a decisão de Id. 10000145 determinou o bloqueio de valores nas contas bancárias dos requeridos, até o limite de ...  

            Houve o bloqueio via SISBAJUD (Id. ...) nos seguintes termos:  
            ...
            """
        </exemplo>
    </se> <!-- processamento paralelo -->
</para>

Vieram os autos conclusos.

</template_interloc_m.1_relatorio>