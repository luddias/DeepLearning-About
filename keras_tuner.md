# Keras Tuner

 O Keras Tuner é uma biblioteca que ajuda você a escolher o conjunto ideal de hiperparâmetros para seu programa TensorFlow. O processo de selecionar o conjunto certo de hiperparâmetros para seu aplicativo de aprendizado de máquina (ML) é chamado de ajuste de hiperparâmetro ou hypertuning .

Os hiperparâmetros são as variáveis ​​que governam o processo de treinamento e a topologia de um modelo de ML. Essas variáveis ​​permanecem constantes ao longo do processo de treinamento e impactam diretamente no desempenho do seu programa de ML. Os hiperparâmetros são de dois tipos:

- **Hiperparâmetros do modelo** que influenciam a seleção do modelo, como o número e a largura das camadas ocultas
- **Hiperparâmetros do algoritmo** que influenciam a velocidade e a qualidade do algoritmo de aprendizado, como a taxa de aprendizado para Stochastic Gradient Descent (SGD) e o número de vizinhos mais próximos para o classificador ak Nearest Neighbors (KNN)

## Configuração

``` bash
pip install -q -U keras-tuner
```

``` python
import keras_tuner as kt
```

## Referências

Introdução ao sintonizador Keras | TensorFlow Core.
<br>Disponível em: <https://www.tensorflow.org/tutorials/keras/keras_tuner?hl=pt-br>. 

‌
