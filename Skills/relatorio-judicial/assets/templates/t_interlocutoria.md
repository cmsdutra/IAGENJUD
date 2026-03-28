# TEMPLATE DECISÃO INTERLOCUTÓRIA

<t_interlocutoria>

## **RELATÓRIO**

<loop para="cada petição/ato judicial/certidão/parecer/laudo/documento/outro apresentado">

// Em ordem crescente de Ids., faça uma síntese concisa e objetiva da peça processual ou do documento, indicando quem juntou, o Id. e o conteúdo. Se for petição, detalhar os fundamentos e pedidos; se for ato judicial, detalhar as deliberações e fundamentos. 

// Escreva de forma orgânica, em texto fluído, com ênfase no conflito pendente de análise, e observando as regras de estilo  (`estilo.md`). 

// Não informe a data de protocolo da petição ou ato judicial, salvo se, pelo contexto, for relevante para a solução da controvérsia. Não apresente metadados do prompt (como tags, comentários, etc.).

// Quando a documentação encaminhada pelo usuário iniciar com uma decisão, extraia dela o contexto da ação para introduzir o relatório, mas, em seguida, desenvolva a narrativa a partir dela (o que foi deliberado nela). Salvo se o usuário solicitar expressamente, não repita o relatório da decisão fornecida.

<exemplo-output>
"""
Cuida-se de ação movida por JOÃO DA SILVA em face de JOSÉ DA SILVA, visando à condenação do requerido ao pagamento de indenização por danos morais, no valor de R$ 10.000,00 (dez mil reais).  

Após a apresentação de contestação pelo requerido (Id. ...), o autor veio aos autos pleitear o compartilhamento da prova produzida em ação semelhante na 2ª Vara Federal desta Seção Judiciária (Autos ...). Argumenta, para tanto, que o compartilhamento de provas é permitido pelo CPC (art. ...) e prestigia a celeridade e economia processual, além de não afrontar a ampla defesa e contraditório, tendo em vista que a parte ré é a mesma nesta e naquela ação (Id. ...).  

Intimado, o réu não se opôs ao pedido, ressaltando, contudo, a necessidade de abertura de vista para manifestação (Id. ...).
"""
</exemplo-output>

</loop>

Vieram os autos conclusos.

</t_interlocutoria>