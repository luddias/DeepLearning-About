# Batch Normalization
*"A normalização de lote é uma técnica para treinar redes neurais muito profundas que padroniza as entradas em uma camada para cada minilote. Isto tem o efeito de estabilizar o processo de aprendizagem e reduzir drasticamente o número de épocas de treinamento necessárias para treinar redes profundas."*
<br> ***- Jason Brownlee***

A normalização de lote pode ser implementada durante o treinamento calculando a média e o desvio padrão de cada variável de entrada para uma camada por minilote e usando essas estatísticas para realizar a padronização.

Formalmente, o algoritmo de normalização de lote [1] é definido como: 

<img src="https://github.com/luddias/DeepLearning-About/assets/92104501/189300df-9996-4ee3-80cb-30e326f94ecd" width=400>

## Referências
[1] CHEN, B. Batch Normalization in practice: an example with Keras and TensorFlow 2.0. Disponível em: <https://towardsdatascience.com/batch-normalization-in-practice-an-example-with-keras-and-tensorflow-2-0-b1ec28bde96f>. Acesso em: 29 ago. 2023.
[2] IOFFE, S.; SZEGEDY, C. Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift.
<br>Disponível em: <https://arxiv.org/abs/1502.03167v3>.

‌
‌
