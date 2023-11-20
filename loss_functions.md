# Loss Functions

## Cross Entropy Loss
A perda de entropia cruzada, também chamada de perda logarítmica ou perda logística, é uma função de perda amplamente utilizada em tarefas de classificação para medir quão bem as probabilidades previstas correspondem às probabilidades verdadeiras. Mede a diferença entre duas distribuições de probabilidade, normalmente entre a distribuição verdadeira e uma distribuição prevista ou estimada. A perda de entropia cruzada é empregada para atualizar os pesos do modelo durante o treinamento, com o objetivo de minimizar a perda. Uma perda menor indica um desempenho superior do modelo e uma perda de entropia cruzada de 0 representa perfeição.

A perda de entropia cruzada, também chamada de perda logarítmica ou perda logística, é uma função de perda amplamente utilizada em tarefas de classificação para medir quão bem as probabilidades previstas correspondem às probabilidades verdadeiras. Mede a diferença entre duas distribuições de probabilidade, normalmente entre a distribuição verdadeira e uma distribuição prevista ou estimada. A perda de entropia cruzada é empregada para atualizar os pesos do modelo durante o treinamento, com o objetivo de minimizar a perda. Uma perda menor indica um desempenho superior do modelo e uma perda de entropia cruzada de 0 representa perfeição.

Casos em que a perda de entropia cruzada não funciona bem:

- O desequilíbrio de classe pode introduzir preconceitos no processo. Quando os exemplos da classe majoritária dominam a função de perda e a descida do gradiente, o modelo tende a se tornar mais confiante na previsão da classe majoritária enquanto negligencia as classes minoritárias. Para resolver esse problema, a perda de entropia cruzada balanceada pode ser usada.

- A perda de entropia cruzada não consegue diferenciar entre exemplos fáceis e difíceis. Exemplos difíceis são aqueles em que o modelo comete erros significativos, enquanto exemplos fáceis são fáceis de classificar. Como resultado, a perda de entropia cruzada não dá mais atenção às amostras duras.

## Balanced Cross Entropy Loss
Para mitigar os desafios colocados pelo desequilíbrio de classes, a entropia cruzada balanceada adiciona um hiperparâmetro ou fator de ponderação a cada classe e é representada por α[0,1]. α é a frequência da classe inversa ou um hiperparâmetro que é determinado por validação cruzada. α substitui o termo do rótulo real na equação de entropia cruzada. Para aumentar a clareza na notação, estabelecemos uma definição paralela para α, semelhante à forma como definimos p_t. Consequentemente, denotamos a perda de entropia cruzada balanceada α da seguinte forma:
O problema do desequilíbrio de classes é resolvido pela entropia cruzada equilibrada, mas não consegue distinguir entre os exemplos difíceis e os fáceis. Este problema é resolvido pela perda focal.


## Focal Loss

A perda focal visa melhorar o desempenho do modelo em exemplos difíceis, concentrando-se nos seus erros, em vez de confiar apenas no seu nível de confiança ao prever exemplos fáceis. Ele melhora o tratamento de exemplos difíceis pelo modelo, priorizando seus erros, em vez de confiar apenas na confiança na previsão de exemplos fáceis. Isto é conseguido através da redução de peso, uma técnica que reduz o impacto de exemplos fáceis na função de perda, enfatizando assim a atenção em exemplos difíceis. A redução de peso é aplicada introduzindo um fator modulante (1 − pt) ^γ à perda de entropia cruzada, com parâmetro de foco ajustável γ ≥ 0 .

## α-Balanced Focal Loss

Esta variante combina as características do fator de pesagem α (das ideias de perda de entropia cruzada balanceada) e do parâmetro de focagem γ , o que resulta ainda em maior precisão em relação à forma não balanceada. A perda focal balanceada α lida com o desequilíbrio de classe introduzindo dois componentes de perda focal e o fator de ponderação α . A perda focal reduz a contribuição de perda de exemplos bem classificados, o que permite que o modelo se concentre em exemplos difíceis de classificar. O parâmetro de foco γ ajusta suavemente a taxa na qual exemplos fáceis são reduzidos. α é usado para ajustar os pesos atribuídos às diferentes classes. Na prática, α pode ser definido pela frequência de classe inversa ou tratado como um hiperparâmetro a ser definido por validação cruzada. O valor α dimensiona e equilibra a função de perda e produz uma precisão ligeiramente melhorada em relação à forma não balanceada α.
