# Unidade Linear Retificada - ReLU
A Unidade Linear Retificada é a função de ativação mais comumente utilizada em modelos de aprendizado profundo. A função retorna 0 se receber qualquer entrada negativa, mas para qualquer valor positivo  x , ela retorna esse valor de volta. Portanto, pode ser escrita como  f(x) = max(0, x) .

Graficamente, ela se parece com isto:

![Gráfico ReLU](https://i.imgur.com/gKA4kA9.jpg)

É surpreendente que uma função tão simples (e composta por duas partes lineares) possa permitir que seu modelo leve em consideração não linearidades e interações tão bem. Mas a função ReLU funciona muito bem na maioria das aplicações e é muito amplamente utilizada como resultado.

## Por que Funciona

Introduzindo Interações e Não-Linearidades
As funções de ativação servem a dois propósitos principais:

1) Ajudar um modelo a levar em consideração efeitos de interação.
O que é um efeito de interação? É quando uma variável A afeta uma previsão de forma diferente dependendo do valor de B. Por exemplo, se meu modelo quiser saber se um certo peso corporal indica um risco aumentado de diabetes, ele teria que saber a altura de um indivíduo. Alguns pesos indicam riscos elevados para pessoas baixas, enquanto indicam boa saúde para pessoas altas. Portanto, o efeito do peso corporal no risco de diabetes depende da altura, e diríamos que peso e altura têm um efeito de interação.

2) Ajudar um modelo a levar em consideração efeitos não-lineares. Isso apenas significa que se eu traçar uma variável no eixo horizontal e minhas previsões no eixo vertical, não será uma linha reta. Ou dito de outra forma, o efeito de aumentar o preditor em um é diferente em diferentes valores desse preditor.

Como ReLU Captura Interações e Não-Linearidades
Interações: Imagine um único nó em um modelo de rede neural. Para simplicidade, assuma que ele tem duas entradas, chamadas A e B. Os pesos de A e B para o nosso nó são 2 e 3, respectivamente. Portanto, a saída do nó é  f(2A+3B) . Usaremos a função ReLU para nosso f. Portanto, se  2A+3B  for positivo, o valor de saída do nosso nó também será  2A+3B . Se  2A+3B  for negativo, o valor de saída do nosso nó será 0.

Para concretizar, considere um caso em que A=1 e B=1. A saída é  2A+3B , e se A aumenta, então a saída aumenta também. Por outro lado, se B=-100 então a saída é 0, e se A aumenta moderadamente, a saída permanece 0. Então A pode aumentar nossa saída, ou não. Isso depende apenas do valor de B.

Este é um caso simples onde o nó capturou uma interação. À medida que você adiciona mais nós e mais camadas, a complexidade potencial das interações apenas aumenta. Mas agora você deve ver como a função de ativação ajudou a capturar uma interação.

- Não-Linearidades: Uma função é não-linear se a inclinação não for constante. Portanto, a função ReLU é não-linear em torno de 0, mas a inclinação é sempre ou 0 (para valores negativos) ou 1 (para valores positivos). Isso é um tipo muito limitado de não-linearidade.

Mas dois fatos sobre modelos de aprendizado profundo nos permitem criar muitos tipos diferentes de não-linearidades a partir de como combinamos os nós ReLU.

Primeiro, a maioria dos modelos inclui um termo de viés para cada nó. O termo de viés é apenas um número constante que é determinado durante o treinamento do modelo. Para simplicidade, considere um nó com uma única entrada chamada A e um viés. Se o termo de viés assumir um valor de 7, então a saída do nó é f(7+A). Neste caso, se A for menor que -7, a saída será 0 e a inclinação será 0. Se A for maior que -7, então a saída do nó será 7+A, e a inclinação será 1.

Portanto, o termo de viés nos permite mover onde a inclinação muda. Até agora, ainda parece que só podemos ter duas inclinações diferentes.

No entanto, os modelos reais têm muitos nós. Cada nó (mesmo dentro de uma única camada) pode ter um valor diferente para seu viés, então cada nó pode mudar de inclinação em diferentes valores para nossa entrada.

Quando somamos as funções resultantes, obtemos uma função combinada que muda de inclinação em muitos lugares.

Esses modelos têm a flexibilidade de produzir funções não lineares e levar em consideração interações de forma eficaz (se isso proporcionar previsões melhores). À medida que adicionamos mais nós em cada camada (ou mais convoluções se estivermos usando um modelo convolucional), o modelo obtém uma capacidade ainda maior de representar essas interações e não linearidades.

## Facilitando o Gradiente Descendente
Esta seção é mais técnica do que as anteriores. Se você achar difícil, lembre-se de que você pode ter muito sucesso usando aprendizado profundo mesmo sem esse conhecimento técnico.

Historicamente, os modelos de aprendizado profundo começaram com curvas em forma de S (como a função tangente hiperbólica abaixo):

[Imagem do Gráfico Tanh](Imagem do Gráfico Tanh)

O tangente hiperbólica pareceria ter algumas vantagens. Mesmo que se aproxime de uma superfície plana, nunca é completamente plano em nenhum lugar. Portanto, sua saída sempre reflete mudanças em sua entrada, o que poderíamos esperar que fosse uma coisa boa. Em segundo lugar, é não-linear (ou curvada em todos os lugares). Levar em consideração não-linearidades é um dos principais propósitos da função de ativação. Portanto, esperamos que uma função não linear funcione bem.

No entanto, os pesquisadores tiveram grande dificuldade em construir modelos com muitas camadas ao usar a função tangente hiperbólica. Ela é relativamente plana, exceto por uma faixa muito estreita (essa faixa sendo cerca de

## Referências Bibliográficas

[1] Rectified Linear Units (ReLU) in Deep Learning. Disponível em: <https://www.kaggle.com/code/dansbecker/rectified-linear-units-relu-in-deep-learning>.

‌
