# Multiclass Loss Functions

## Categorical Focal Crossentropy [1]
Use esta função de perda de entropia cruzada quando houver duas ou mais classes de rótulos e se desejar lidar com o desequilíbrio de classes sem usar class_weights. Esperamos que os rótulos sejam fornecidos em uma one_hot representação.

De acordo com [Lin et al., 2018](https://arxiv.org/pdf/1708.02002.pdf), ajuda aplicar um fator focal para reduzir o peso dos exemplos fáceis e focar mais nos exemplos difíceis. A fórmula geral para a perda focal (FL) é a seguinte:

**FL(p_t) = (1 − p_t)^gamma * log(p_t)**

onde p_té definido da seguinte forma: **p_t = output if y_true == 1, else 1 - output**

**(1 − p_t)^gamma** é o modulating_factor, onde gamma é um parâmetro de foco. Quando gamma= 0, não há efeito focal na entropia cruzada. gammareduz a importância dada a exemplos simples de maneira suave.

Os autores usam variante alfa-balanceada de perda focal (FL) no artigo: **FL(p_t) = −alpha * (1 − p_t)^gamma * log(p_t)**

onde alphaestá o fator de peso para as classes. Se alpha= 1, a perda não será capaz de lidar adequadamente com o desequilíbrio de classes, pois todas as classes terão o mesmo peso. Pode ser uma constante ou uma lista de constantes. Se alfa for uma lista, deve ter o mesmo comprimento que o número de classes.

A fórmula acima pode ser generalizada para: **FL(p_t) = alpha * (1 − p_t)^gamma * CrossEntropy(y_true, y_pred)**

de onde vem o menos **CrossEntropy(y_true, y_pred)(CE)**.

Estender isso para casos multiclasse é simples: **FL(p_t) = alpha * (1 − p_t)^gamma * CategoricalCE(y_true, y_pred)**

## Tversky [2]
A perda de Tversky é uma função de perda usada no contexto de tarefas de segmentação de imagens, particularmente em análise de imagens médicas e visão computacional. Ele foi projetado para medir a dissimilaridade entre dois conjuntos, como máscaras binárias previstas e verdadeiras usadas na segmentação. A perda de Tversky foi introduzida como uma extensão do amplamente utilizado índice Jaccard (também conhecido como Intersection over Union, IoU) e da pontuação F1.

A perda de Tversky é definida pela seguinte fórmula:

$$Perda Tversky = (|Interseção|) / (|Interseção| + α * |FP| + β * |FN|)$$

|Interseção| : A cardinalidade (número de elementos) da interseção entre os pixels positivos previstos e os pixels positivos da verdade fundamental.
|PF| : A cardinalidade do conjunto de pixels falsos positivos (pixels classificados incorretamente como positivos na previsão).
|FN| : A cardinalidade do conjunto de pixels falsos negativos (pixels classificados incorretamente como negativos na previsão).
α e β são parâmetros de peso que controlam o trade-off entre falsos positivos (α) e falsos negativos (β). Eles permitem personalizar a sensibilidade da perda a diferentes tipos de erros.
A perda de Tversky pode ser usada para treinar modelos de aprendizado de máquina, particularmente redes neurais profundas, para tarefas de segmentação de imagens. Ao ajustar os parâmetros α e β, você pode controlar como a função de perda penaliza diferentes tipos de erros de segmentação. Por exemplo, definir α > β dará mais ênfase à redução de falsos positivos, enquanto definir β > α focará na redução de falsos negativos.

A perda de Tversky é uma função de perda flexível que permite ajustar a compensação entre precisão e recall em seu modelo de segmentação. É especialmente útil nos casos em que o custo de falsos positivos e falsos negativos difere significativamente e você deseja ajustar o comportamento do modelo de acordo.


## Referências Bibliográficas
[1] tf.keras.losses.CategoricalFocalCrossentropy | TensorFlow v2.14.0. Disponível em: <https://www.tensorflow.org/api_docs/python/tf/keras/losses/CategoricalFocalCrossentropy>. Acesso em: 23 nov. 2023.

[2] HESARAKI, S. Tversky loss. Disponível em: <https://medium.com/@saba99/tversky-loss-902f5f8cc35f>. Acesso em: 23 nov. 2023.

‌
