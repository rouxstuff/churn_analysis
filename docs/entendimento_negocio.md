# EDA - Telecom Costumer Churn

A empresa atua no setor de telecomunicações, oferecendo serviços de internet (DSL e Fibra Óptica), telefonia e serviços adicionais (suporte técnico, segurança online, streaming, entre outros), com diferentes modalidades de contrato e métodos de pagamento.

## Problema
Uma parcela significativa da base de clientes está cancelando o serviço (churn). Atualmente, não está claro quais fatores levam um cliente a cancelar, o que dificulta a criação de ações de retenção direcionadas e eficazes. Sem entender o perfil e os motivos por trás do churn, a empresa corre o risco de:

* Perder receita de forma contínua e crescente;
* Investir em ações de retenção genéricas e pouco eficazes;
* Não identificar clientes em risco a tempo de intervir.

## Objetivo
Realizar uma análise exploratória de dados (EDA) da base de clientes para:

* Entender o comportamento geral da base (volume, qualidade e distribuição dos dados);
* Identificar os principais fatores associados ao cancelamento de clientes;
* Traçar o perfil do cliente com maior probabilidade de churn;
* Gerar insights que suportem ações estratégicas de retenção.

Este entendimento servirá como base para etapas futuras, como a construção de um modelo preditivo de churn.

## Perguntas de Negócio

A análise busca responder às seguintes perguntas:

* Qual a proporção de clientes que cancelaram o serviço em relação aos que permaneceram?
* O tipo de contrato influencia a taxa de churn?
* O tipo de serviço de internet contratado está relacionado ao cancelamento?
* A presença de serviços de suporte reduz a probabilidade de churn?
* O cliente ter ou não dependentes tem relação com a fidelização?
* O método de pagamento utilizado pelo cliente influencia sua propensão a cancelar?
* Existe relação entre o valor cobrado e a decisão de cancelamento?

## Insights
* Maior parte dos clientes tem o plano de Month-to-month.
* Uma parcela significativa de clientes cancelou o serviço logo no inicio do relacionamento com a empresa.
* Maior parte dos clientes escolheu Fiber Optic.

## Hipóteses Norteadoras
Para guiar a investigação dessas perguntas, foram levantadas três hipóteses principais:
* Hipótese 1: O tipo de contrato influencia no churn?
* Hipótese 2: O serviço oferecido influencia no churn?
* Hipótese 3: O método de pagamento e as cobranças influenciam no churn?

## Bibliotecas Utilizadas
* Pandas
* Numpy 
* Matplotlib
* Seaborn

## Dataset
- [Telco Costumer Churn - IBM](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

## Hipótese 1: O tipo de contrato influencia no churn?
Para testar essa hipótese, comparamos a distribuição de cancelamentos entre os diferentes tipos de contrato. 

Utilizamos um gráfico de contagem para visualizar a quantidade de clientes que cancelaram ou não em cada tipo de contrato, além de uma tabela de proporções para avaliar a taxa de churn relativa dentro de cada grupo.

Foi constatado que clientes com contratos mensais têm a maior taxa de cancelamento, indicando que clientes com contratos flexíveis de curto prazo têm maior probabilidade de sair. E clientes com contratos de um e dois anos mostram uma rotatividade significativamente menor, sugerindo que contratos com maior tempo de compromisso ajudam na retenção.

## Hipótese 2: O serviço oferecido influencia no churn?
Após confirmar que o tipo de contrato influencia fortemente o churn, investigamos se o serviço oferecido ao cliente também tem um papel importante, considerando o tipo de internet contratada, a presença de suporte técnico e se o cliente possui dependentes. A ideia é entender se a qualidade e abrangência do serviço prestado afetam a decisão do cliente de permanecer ou cancelar.

Foi constatado que clientes com **Fibra Óptica** apresentam a maior taxa de cancelamento entre os tipos de internet, enquanto clientes sem serviço de internet têm a menor taxa. Esse padrão se conecta ao observado na Hipótese 1: clientes com contrato mensal são majoritariamente usuários de Fibra Óptica, reforçando que os dois fatores atuam em conjunto.

Além disso, clientes **sem suporte técnico** apresentam uma taxa de churn muito maior do que clientes com suporte técnico contratado, sugerindo que problemas não resolvidos podem levar à frustração e ao cancelamento.

Por fim, clientes **sem dependentes** também apresentam maior propensão ao churn em comparação com clientes que possuem dependentes, indicando que o perfil familiar do cliente também está relacionado à sua fidelização.

## Hipótese 3: O método de pagamento e as cobranças influenciam no churn?
Investigamos se a forma como o cliente paga e os valores cobrados também têm relação com o cancelamento, testando se métodos de pagamento mais manuais e cobranças mais altas tornam o cliente mais propenso a sair.

Foi constatado que clientes que utilizam **electronic check** apresentam a maior taxa de cancelamento entre os métodos de pagamento, enquanto métodos automáticos (débito ou cartão em recorrência) apresentam taxas de churn bem menores.

Também observamos que clientes que cancelaram pagam, em mediana, valores mensais mais altos (~R$80) do que os que permaneceram (~R$65), sugerindo que cobranças mais elevadas, combinadas com pagamentos manuais, reduzem o comprometimento do cliente e aumentam o risco de churn.

## Conclusão
Cruzando as três hipóteses, identificamos que o perfil de cliente com **maior risco de churn** combina: **contrato mensal**, **ausência de suporte técnico** e **pagamento via electronic check**,frequentemente associado também ao uso de **fibra óptica** e à **ausência de dependentes**. Esse achado sugere que ações de retenção devem ser priorizadas para esse segmento específico de clientes, por meio de suporte técnico proativo, incentivo à migração para pagamento automático e benefícios para adesão a contratos mais longos.