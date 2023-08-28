# UNET - Rede de Segmentação Semântica

## Arquitetura UNET detalhada
<img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*yzbjioOqZDYbO6yHMVpXVQ.jpeg">

## De acordo com a imagem acima...
- Camadas 2@Conv significam que duas camadas de convolução consecutivas são aplicadas
- c1, c2,…. c9 são os tensores de saída das camadas convolucionais
- p1, p2, p3 e p4 são os tensores de saída de Max Pooling Layers
- u6, u7, u8 e u9 são os tensores de saída das camadas de amostragem ascendente (convolucional transposta)
- O lado esquerdo é o caminho de contração (Encoder) onde aplicamos convoluções regulares e camadas máximas de pooling.
- No Encoder, o tamanho da imagem diminui gradativamente enquanto a profundidade aumenta gradativamente. Começando de 128x128x3 a 8x8x256.
Isso significa que a rede aprende a informação "o que", entretanto perde a informação "onde". Para resolver isso temos o lado direito, que é o caminho da expansão (decodificador) onde se é aplicado convoluções transpostas junto com convoluções regulares.
No decodificador, o tamanho da imagem aumenta gradativamente e a profundidade diminui gradativamente. Intuitivamente o decodificador recupera a informação "onde", aplicando gradualmente up-sampling.

Para obter localizações mais precisas, em cada etapa do decodificador usamos conexões de salto concatenando a saída das camadas de convolução transpostas com os mapas de recursos do codificador no mesmo nível:
<br>u6 = u6 + c4
<br>u7 = u7 + c3
<br>u8 = u8 + c2
<br>u9 = u9 + c1
<br>Após cada concatenação aplicamos novamente duas convoluções regulares consecutivas para que o modelo possa aprender a montar uma saída mais precisa.

Isso dá à arquitetura um formato simétrico em formato de U, por isso o nome "U-net".

- Em um nível superior, temos o seguinte relacionamento:
Entrada (128x128x1) => Encoder =>(8x8x256) => Decodificador =>Ouput (128x128x1)

## Fonte Bibliográfica

HARSHALL LAMBA. Understanding Semantic Segmentation with UNET.
<br>Disponível em: <https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47>.

‌
