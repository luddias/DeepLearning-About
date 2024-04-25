# Recurrent Neural Network (RNN – Rede neural recorrente) 
A imagem a seguir mostra um diagrama de uma RNN.
![RNN graph](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2017/10/06/intro-gluon-1.gif)

As RNNs são feitas de neurônios: nós de processamento de dados que trabalham juntos para realizar tarefas complexas. Os neurônios são organizados como camadas de entrada, saída e ocultas. A camada de entrada recebe as informações a serem processadas e a camada de saída fornece o resultado. O processamento, a análise e a previsão de dados ocorrem na camada oculta. 

## Camada oculta
As RNNs funcionam passando os dados sequenciais que recebem para as camadas ocultas, uma etapa de cada vez. No entanto, eles também têm um fluxo de trabalho em loop automático ou recorrente: a camada oculta pode lembrar e usar entradas anteriores para previsões futuras em um componente de memória de curto prazo. Ele usa a entrada atual e a memória armazenada para prever a próxima sequência. 

Por exemplo, considere a sequência: Apple is red. Você quer que a RNN preveja o red ao receber a sequência de entrada Apple is. Quando a camada oculta processa a palavra Apple, ela armazena uma cópia em sua memória. Em seguida, quando vê a palavra is, ele lembra a Apple de sua memória e entende a sequência completa: Apple is para contextualizar. Em seguida, ele pode prever o red para melhorar a precisão. Isso torna as RNNs úteis em reconhecimento de fala, tradução automática e outras tarefas de modelagem de idiomas.


## Treinamento
Os engenheiros de machine learning (ML) treinam redes neurais profundas, como RNNs, alimentando o modelo com dados de treinamento e refinando sua performance. No machine learning, os pesos do neurônio são sinais para determinar a influência das informações aprendidas durante o treinamento ao prever a saída. Cada camada em uma RNN compartilha o mesmo peso. 

Os engenheiros de ML ajustam os pesos para melhorar a precisão da previsão. Eles usam uma técnica chamada retropropagação ao longo do tempo (BPTT) para calcular o erro do modelo e ajustar seu peso adequadamente. O BPTT reverte a saída para a etapa de tempo anterior e recalcula a taxa de erro. Dessa forma, ele pode identificar qual estado oculto na sequência está causando um erro significativo e reajustar o peso para reduzir a margem de erro.

## Tipos
- Um para muitos
Esse tipo de RNN canaliza uma entrada para várias saídas. Ele permite aplicações linguísticas, como legendas de imagens, gerando uma frase a partir de uma única palavra-chave.

- Muitos para muitos
O modelo usa várias entradas para prever várias saídas. Por exemplo, você pode criar um tradutor de idiomas com uma RNN, que analisa uma frase e estrutura corretamente as palavras em um idioma diferente. 

- Muitos para um
Várias entradas são mapeadas para uma saída. Isso é útil em aplicações como análise de sentimentos, em que o modelo prevê os sentimentos dos clientes, como positivos, negativos e neutros, a partir de depoimentos recebidos.

## Comparação com outras redes profundas

- Rede neural recorrente versus rede neural de feedback direto
Assim como as RNNs, as redes neurais feed-forward são redes neurais artificiais que transmitem informações de uma extremidade à outra extremidade da arquitetura. Uma rede neural de feedback direto pode realizar tarefas simples de classificação, regressão ou reconhecimento, mas não consegue se lembrar da entrada anterior que processou. Por exemplo, ele esquece a Apple quando seu neurônio processa a palavra is. A RNN supera essa limitação de memória ao incluir um estado de memória oculta no neurônio.

- Rede neural recorrente versus redes neurais convolucionais
As redes neurais convolucionais são redes neurais artificiais projetadas para processar dados temporais. Você pode usar redes neurais convolucionais para extrair informações espaciais de vídeos e imagens, passando-as por uma série de camadas convolucionais e agrupadas na rede neural. As RNNs são projetadas para capturar dependências de longo prazo em dados sequenciais

## Quais são as limitações das redes neurais recorrentes?
Desde a introdução da RNN, os engenheiros de ML fizeram um progresso significativo em aplicações de processamento de linguagem natural (PLN) com RNNs e suas variantes. No entanto, a família de modelos de RNN tem várias limitações.

- Gradiente em explosão
Uma RNN pode prever erroneamente a saída no treinamento inicial. Você precisa de várias iterações para ajustar os parâmetros do modelo e reduzir a taxa de erro. Você pode descrever a sensibilidade da taxa de erro correspondente ao parâmetro do modelo como um gradiente. Você pode imaginar um gradiente como uma inclinação que você usa para descer de uma colina. Um gradiente mais acentuado permite que o modelo aprenda mais rápido, e um gradiente raso diminui a taxa de aprendizado.

O gradiente explosivo acontece quando o gradiente aumenta exponencialmente até que a RNN se torne instável. Quando os gradientes se tornam infinitamente grandes, a RNN se comporta de forma irregular, resultando em problemas de performance, como sobreajuste. O sobreajuste é um fenômeno em que o modelo pode prever com precisão com dados de treinamento, mas não pode fazer o mesmo com dados do mundo real. 

- Gradiente de desaparecimento
O problema do gradiente de desaparecimento é uma condição em que o gradiente do modelo se aproxima de zero no treinamento. Quando o gradiente desaparece, a RNN falha em aprender de forma eficaz com os dados de treinamento, resultando em um ajuste insuficiente. Um modelo subajustado não pode funcionar bem em aplicações reais porque seus pesos não foram ajustados adequadamente. As RNNs correm o risco de desaparecer e explodir problemas de gradiente ao processar longas sequências de dados. 

- Tempo de treinamento lento
Uma RNN processa dados sequencialmente, o que limita sua capacidade de processar um grande número de textos com eficiência. Por exemplo, um modelo de RNN pode analisar o sentimento de um comprador a partir de algumas frases. No entanto, é necessário um enorme poder de computação, espaço de memória e tempo para resumir uma página de um ensaio.

## Referências Bibliográficas
[1] O que é RNN? — Explicação sobre redes neurais recorrentes — AWS. Disponível em: <https://aws.amazon.com/pt/what-is/recurrent-neural-network/>. Acesso em: 25 abr. 2024.

‌
