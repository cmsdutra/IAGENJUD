# TEMPLATE DESFECHO DE SENTENÇA - GERAL (menos MS)
<!-- Version 1.0.0 | 04-2025 Caio Dutra -->

<template_sent_m.4_desfecho>

### DELIBERAÇÃO JUDICIAL
Diante do exposto:
**(a)** **[ACOLHO/ACOLHO EM PARTE/REJEITO]** os pedidos formulados na [petição inicial/reconvenção], nos termos do art. 487, inc. I, do CPC[, para... (provimentos jurisdicionais específicos)].

<se (houver condenação em pagar quantia certa)>
    **(a.[1, 2, 3..])** sobre o valor da condenação deverão incidir correção monetária, desde de..., e juros moratórios, desde de..., nos índices previstos no Manual de Cálculos da Justiça Federal. 
</se>

<se (juizado_especial == false)>
**(b)** **CONDENO** a parte [AUTORA/RÉ] [de forma solidária] [Opção 1.1 - default: "ao pagamento das custas e demais despesas processuais" / Opção 1.2 - Sucumbente Fazenda Pública: "ao ressarcimento das custas e demais despesas processuais eventualmente adiantadas (art. 4º, inc. I e parágrafo único, Lei nº 9.289/1996" / Opção 1.3 - sucumbente beneficiário de justiça gratuita: isento de custas, art. 4º, inc. II, da Lei nº 9.289/1996], e ao pagamento de honorários advocatícios sucumbenciais em favor do(a) patrono(a)/procurador(a) da parte adversária, no fixados em 10% sobre o valor da [causa/condenação/proveito econômico], observado o valor mínimo de R$ 3.721,20 (três mil, setecentos e vinte e um reais e vinte centavos), nos termos do art. 85, §§ 2º, 8º, 8º-A e 19, do Código de Processo Civil, e do item 10.21, do Anexo I, da Resolução/OAB-TO nº 05/2024.
<se (parte sucumbente → beneficiária da justiça gratuita)>
    **(b.1)** fica a exigibilidade dos encargos sucumbenciais suspensa, nos termos do art. 98, § 3º, do Código de Processo Civil, por ser a parte sucumbente beneficiária da gratuidade da justiça [(Id. ...) - ID da decisão que deferiu a gratuidade, se identificável].
</se>
<else> <!-- juizado_especial == true -->
Sem condenação em custas ou honorários (art. 55, Lei nº 9.099/1995).
</se>

<!-- Identifica se é o caso de reexame necessário -->
<se (
        (ACP.resultado == improcedente && improbidade == false ) || acao_popular.resultado == improcedente || mandado_seguranca.resultado == concessao || (desapropriacao == true && indenizacao > 2*oferta_inicial) || juizado_especial == false ||
        (Fazenda_Publica.parte == true && (
            (condenacao > 1000*salario_minimo && ente == "Uniao") ||
            (condenacao > 500*salario_minimo && ente == "Estado") ||
            (condenacao > 100*salario_minimo && ente == "Municipio") ||
            (condenacao > 60*salario_minimo && ente == "INSS" && previdenciario == true) ||
            sentenca.tipo == "iliquida" || embargos_execucao_fiscal.resultado == "procedente"
        ))
    ) && 
    !(sentenca.fundamentada_em == (sumula_tribunal_superior || IRDR || assuncao_competencia || orientacao_vinculante_admin))
>

<!-- é caso de reexame necessário -->
`reexame_necessario = sim`
Sentença que **se sujeita** a reexame necessário.

<senão> <!-- não é caso de reexame necessário -->

`reexame_necessario = não`
Sentença que **não se sujeita** a reexame necessário.
</se>

<!-- Fim da análise do reexame necessário -->

### PROVIDÊNCIAS DE IMPULSO PROCESSUAL
A Secretaria da Vara deverá:
**(i)** **intimar** as partes desta sentença;
**(ii)** **aguardar** o prazo para a interposição de recurso;

<se (reexame_necessario == não)>

**(iii)** interpostos recursos, **colher** contrarrazões, **certificar** tempestividade e preparo, se for o caso, e **remeter** os autos <se (juizado_especial == false)> ao egr. Tribunal Regional Federal da 1ª Região <else> à egr. Turma Recursal desta SJTO </se> para julgamento, independentemente de juízo de admissibilidade;
**(iv)** não interposto recurso no prazo, **certificar** o trânsito em julgado e **intimar** as partes para requerer o que entender de direito;
**(v)** não havendo requerimentos, **arquivar** o feito com as formalidades de praxe.

<else>

**(iii)** interposto recurso, **colher** contrarrazões e **certificar** tempestividade e preparo, se for o caso;
**(iv)** independentemente da interposição de recurso, **remeter** ao egr. Tribunal Regional Federal para reexame necessário.

</se>

Palmas(TO), data do sistema.

</template_sent_m.4_desfecho>