# Cross Validation (K-Fold)

A otimização de hiperparâmetros que utilizamos nos nossos modelos de machine learning, em especial nos casos de redes neurais, representa um grande desafio na rotina do cientista de dados. Elas têm muitos hiperparâmetros, além de levarem muito tempo para serem treinadas.
O processo GridSearchCV constrói e avalia um modelo para cada combinação de parâmetros. GridSearchCV é o processo de realização de ajuste de hiperparâmetros para determinar os valores ideais para um determinado modelo. Conforme mencionado acima, o desempenho de um modelo depende significativamente do valor dos hiperparâmetros. Observe que não há como saber antecipadamente os melhores valores para os hiperparâmetros, portanto, idealmente, precisamos tentar todos os valores possíveis para saber os valores ideais. Fazer isso manualmente pode consumir uma quantidade considerável de tempo e recursos e, portanto, usamos GridSearchCV para automatizar o ajuste de hiperparâmetros. 
A validação cruzada é usada para avaliar os modelos evitando overfitting, e tem um número padrão de 3 vezes, podendo ser configurado um valor diferente, no parâmetro cv, também dentro do construtor da classe GridSearchCV.

## O Que é K-fold?
K-fold consiste em dividir a base de dados de forma aleatória em K subconjuntos (em que K é definido previamente) com aproximadamente a mesma quantidade de amostras em cada um deles. A cada iteração, treino e teste, um conjunto formado por K-1 subconjuntos são utilizados para treinamento e o subconjunto restante será utilizado para teste gerando um resultado de métrica para avaliação (ex: acurácia). Esse processo garante que cada subconjunto será utilizado para teste em algum momento da avaliação do modelo.

![Screenshot from 2023-11-13 14-29-08](https://github.com/luddias/DeepLearning-About/assets/92104501/2cd44cb9-fc2d-4b26-a530-55a3258d6f9a)

Passo-a-passo:
- Escolha um número de dobras – k. Normalmente, k é 5 ou 10, mas você pode escolher qualquer número menor que o comprimento do conjunto de dados.
- Divida o conjunto de dados em k partes iguais (se possível) (elas são chamadas de dobras)
- Escolha k – 1 dobras como conjunto de treinamento. A dobra restante será o conjunto de teste
- Treine o modelo no conjunto de treinamento. Em cada iteração de validação cruzada, você deve treinar um novo modelo independentemente do modelo treinado na iteração anterior
- Validar no conjunto de testes
- Salve o resultado da validação
- Repita as etapas 3 – 6 k vezes. Cada vez use a dobra restante como conjunto de teste. No final, você deverá ter validado o modelo em cada dobra que possui.
- Para obter a pontuação final, calcule a média dos resultados obtidos na etapa 6.

## Referências

[1] RABELLO, E. B. Cross Validation: Avaliando seu modelo de Machine Learning. <br>Disponível em: <https://medium.com/@edubrazrabello/cross-validation-avaliando-seu-modelo-de-machine-learning-1fb70df15b78>.


‌‌[2]LYASHENKO, V.; JHA, A. Cross-Validation in Machine Learning: How to Do It Right. <br>Disponível em: <https://neptune.ai/blog/cross-validation-in-machine-learning-how-to-do-it-right>.
