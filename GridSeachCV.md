# Grid Search

A otimização de hiperparâmetros que utilizamos nos nossos modelos de machine learning, em especial nos casos de redes neurais, representa um grande desafio na rotina do cientista de dados. Elas têm muitos hiperparâmetros, além de levarem muito tempo para serem treinadas.
O processo GridSearchCV constrói e avalia um modelo para cada combinação de parâmetros. GridSearchCV é o processo de realização de ajuste de hiperparâmetros para determinar os valores ideais para um determinado modelo. Conforme mencionado acima, o desempenho de um modelo depende significativamente do valor dos hiperparâmetros. Observe que não há como saber antecipadamente os melhores valores para os hiperparâmetros, portanto, idealmente, precisamos tentar todos os valores possíveis para saber os valores ideais. Fazer isso manualmente pode consumir uma quantidade considerável de tempo e recursos e, portanto, usamos GridSearchCV para automatizar o ajuste de hiperparâmetros. 
A validação cruzada é usada para avaliar os modelos evitando overfitting, e tem um número padrão de 3 vezes, podendo ser configurado um valor diferente, no parâmetro cv, também dentro do construtor da classe GridSearchCV.

## Como usar o Grid Search?
Esses são so principais parâmetros que podem ser utilizados:

1. estimador  : passe a instância do modelo para a qual deseja verificar os hiperparâmetros. 
2. params_grid  : o objeto de dicionário que contém os hiperparâmetros que você deseja testar 
3. scoring  : métrica de avaliação que você deseja usar, você pode simplesmente passar uma string/objeto válido da métrica de avaliação 
4. cv  : número de validação cruzada que você deve tentar para cada conjunto selecionado de hiperparâmetros 
5. verbose  : você pode configurá-lo como 1 para obter a impressão detalhada enquanto ajusta os dados ao GridSearchCV 
6. n_jobs  : número de processos que você deseja executar em paralelo para esta tarefa, se for -1 usará todos os processadores disponíveis. 


## Referências

[1] How to find optimal parameters using GridSearchCV in ML in python.<br>Disponível em: <https://www.projectpro.io/recipes/find-optimal-parameters-using-gridsearchcv>.

‌‌[2] Otimização com Grid Search.<br>Disponível em: <https://www.linkedin.com/pulse/otimiza%C3%A7%C3%A3o-com-grid-search-gabriel-constantin/?originalSubdomain=pt>.

‌
