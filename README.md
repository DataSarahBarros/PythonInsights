## Python Insights - Analisando Dados com Python

## Case - Cancelamento de Clientes

Uma empresa com mais de 800 mil clientes para um projeto de Dados. Recentemente a empresa percebeu que da sua base total de clientes, a maioria são clientes inativos, ou seja, que já cancelaram o serviço.

É necessário seu resultado ela quer conseguir entender os principais motivos desses cancelamentos e quais as ações mais eficientes para reduzir esse número.

## Análise das causas dos cancelamentos dos clientes, encontrando parâmetros para identificar pontos em comum em clientes que cancelaram.

*Olhando para o cadastro dos clientes, pode-se identificar um padrão de cancelamento por diferentes aspectos como por exemplo idade e sexo.*

*Podemos fazer uma análise preditiva pelo tempo de uso do produto, a frequência de uso, o tipo de assinatura. *

*Pensando nos eventos que antecederam o cancelamento:*

*Quantas ligações foram feitas para o call center?*
*Quantos meses da última interação com o site até que o pedido de cancelamento fosse solicitado?* 
*Quantos dias de atraso no pagamento vs duração do contrato?* 
*Qual a relação do total gasto pelo cliente com o custo até que o cliente cancela-se de fato?*

## Considerações levantamento das principais causas de cancelamento

**Gráfico Duração do contrato**
    *problema*: clientes do contrato mensal cancelaram.
    *solução*: campanha com desconto nos contratos anuais e trimestrais:
    
*Duração do contrato não pode ser mensal*
tabela = tabela[tabela["duracao_contrato"]!="Montly"]

**Gráfico Dias de atraso para pagamento**
    *problema*: clientes com mais de 20 dias de atraso cancelaram o serviço.
    *solução*: Criar sistema de cobrança dos clientes que, com dez dias de atraso entrar em contato pra regularizar:

*Atrasos só podem ser de até 20 dias*
tabela = tabela[tabela["dias_atraso"]<=20]

**Gráfico Ligações Call Center**
    *problema*: clientes que ligaram mais de quatro vezes para o call center cancelaram.
    *solução*: criar alerta para os clientes que ligarem mais de duas vezes:

*Ligações no call centes só pode ser de até quatro dias*
tabela = tabela[tabela["ligacoes_callcenter"]<=4]
