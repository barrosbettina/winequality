# Análise exploratória para avaliar a consistência dos dados e identificar possíveis variáveis que impactam na qualidade do vinho.

## a. Como foi a definição da sua estratégia de modelagem?

O primeiro passo foi conhecer os dados e procurar por inconsistências. Após, foi feita uma análise exploratória básica, olhando para os histogramas e correlações entre as variáveis, onde não tivemos indicação de uma forte relação linear nos dados, confirmada pela análise das componentes principais. Dois algoritmos foram utilizados para construir regressores com objetivo de explicar a qualidade dos vinhos com base nas demais variáveis. Por fim, buscamos observar quais variáveis tiveram maior impacto.

## b. Como foi definida a função de custo utilizada?

A função de custo é dada pelo MSE, do inglês 'mean square error', que penaliza quadraticamente o erro de cada amostra.

## c. Qual foi o critério utilizado na seleção do modelo final?

A escolha do modelo final foi feita através de uma análise da média e desvio padrão dos erros médios quadráticos na validação cruzada para cada algoritmo e combinação de parâmetros. Foi tomado o devido cuidado para não obter um modelo sem generalização do conjunto de validação para o conjunto de teste.

## d. Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar
este método?

Após a escolha do algoritmo e parâmetros a serem utilizados, foi feito um retreinamento com o conjunto de treino e validação juntos e o modelo foi avaliado no conjunto de teste, que ainda não havia sido utilizado. O resultado do MSE do conjunto de teste confirma o resultado da validação cruzada, e assim temos uma boa generalização.

##e. Quais evidências você possui de que seu modelo é suficientemente bom?

Apesar do MSE ser relativamente alto, 0.367, quando passamos a olhar a qualidade do vinho como números inteiros, arredondando os valores resultantes do regressor, temos uma taxa de acerto acima de 67%, sendo que cerca de 29% tem erro de apenas 1 ponto de qualidade, o que é bastante razoável dada a complexidade do problema.
