# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Este projeto tem como objetivo construir um modelo de previsão de estoque utilizando o Amazon SageMaker Canvas, bem como analisar as métricas de performance do modelo.
## Importância das variáveis
A variável resposta ou *target* do nosso modelo foi a variável *stock_level (indica a quantidade de produtos em estoque)*.

Inicialmente, 4 variáveis foram utilizadas como *features*, sendo elas:
* X<sub>1</sub> - units_sold (unidades vendidas)
* X<sub>2</sub> - day_of_week (dia da semana)
* X<sub>3</sub> - holiday (feriado, sendo 1 = feriado, 0 = não feriado)
* X<sub>4</sub> - promotion (promoção, 1 = produto em promoção, 0 = preço normal)

O modelo utilizado concluiu que apenas as variáveis X<sub>1</sub> e X<sub>2</sub> tiveram impacto no modelo, sendo:
* X<sub>1</sub> - 31,67% de impacto
* X<sub>2</sub> - 3,5% de impacto

## Indicadores de Performance
MAPE: 1.642

O valor do MAPE obtido, significa que o nosso modelo tende a errar em 164,2% os valores reais do estoque.


RMSE: 30,304

O valor no RMSE obtido, nos mostra que em média, tendemos a errar em 30 unidades os valores dos produtos. 

## O modelo é satisfatório?
Como o valor do MAPE é alto e o RMSE também (visto que a média de estoque dos produtos é 46,65), podemos dizer que o nosso modelo não é satisfatório e deveríamos buscar técnicas diferentes ou então melhores *features* para ajustar o nosso modelo, uma *feature* interessante poderia ser o valor de venda ou então o valor de compra, já que seria mais simples para a empresa manter valores de baixo custo no estoque, deixando assim menos "dinheiro parado", outra possibilidade seria as dimensões do produto, já que produtos de maiores dimensões geram mais custos.

O indicador MASE tem um valor de 0,855, o que nos mostra que apesar do modelo não ser satisfatório é melhor que o modelo simples, ou seja, o nosso modelo é melhor do que simplesmente utilizar o valor anterior (do dia anterior) para controlar o nosso estoque.

## Previsões
A previsão de estoque para 5 dias do produto 1 é: 
![single_prediction_results](https://github.com/user-attachments/assets/37724298-77b6-42b2-84f5-5f3e96a01f0c)

A previsão de estoque para 5 dias do produto 2 é: 
![single_prediction_results (1)](https://github.com/user-attachments/assets/2b993b12-443a-46ec-b1df-f4706a42a1e5)

A previsão de estoque para 5 dias do produto 3 é: 
![single_prediction_results (2)](https://github.com/user-attachments/assets/0a1caa1c-ef37-4092-8429-bc1384092612)
