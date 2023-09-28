# Métricas de Avaliação de Desempenho
*Redes de Segmentação Semântica Multiclasse*
- **IoU (Intersection over Union):** O IoU, também conhecido como Jaccard Index, é uma métrica fundamental para a segmentação semântica. Ele mede a sobreposição entre a máscara de segmentação prevista pelo modelo e a máscara de segmentação verdadeira. Quanto maior o IoU, melhor a sobreposição e, portanto, melhor o desempenho do modelo.

- **Dice Coefficient:** O coeficiente de Dice é outra métrica que avalia a sobreposição entre as máscaras de segmentação previstas e verdadeiras. É calculado como o dobro da interseção dividido pela soma das áreas das máscaras. Valores mais altos indicam uma segmentação mais precisa.

- **Pixel Accuracy:** Esta métrica mede a proporção de pixels classificados corretamente em relação ao número total de pixels na imagem. É uma métrica simples que fornece uma visão geral do desempenho do modelo.

- **Média da Interseção sobre União (Mean IoU):** Em problemas de segmentação multiclasse, você pode calcular o IoU para cada classe individualmente e, em seguida, tirar a média desses valores para obter a média da Interseção sobre União. Isso fornece uma avaliação geral do desempenho de todas as classes.

- **F1-Score:** O F1-Score é uma métrica que combina precisão e revocação (recall). Ele é calculado para cada classe e pode ser útil quando o equilíbrio entre falsos positivos e falsos negativos é importante.

- **Média da Precisão por Classe:** Calcula a precisão para cada classe e tira a média desses valores. Isso permite avaliar o desempenho do modelo em cada classe separadamente.

- **Média do Recall por Classe:** Semelhante à média da precisão por classe, essa métrica calcula o recall para cada classe e tira a média desses valores.

- **Frequência Ponderada do IoU (Weighted IoU):** Leva em consideração o desequilíbrio de classe atribuindo pesos diferentes às classes. Isso ajuda a lidar com cenários em que algumas classes são muito mais frequentes do que outras.

- **Tempo de Inferência:** Embora não seja uma métrica de desempenho diretamente relacionada à qualidade da segmentação, o tempo de inferência é importante em aplicações em tempo real, como veículos autônomos. Avalie quanto tempo a rede leva para segmentar uma imagem.

- **Curvas ROC por Classe:** Em algumas situações, pode ser útil calcular curvas ROC para cada classe para avaliar o desempenho em problemas de segmentação binária.


## Referências
RODRIGUES, V. Métricas de Avaliação: acurácia, precisão, recall… quais as diferenças? Disponível em: <https://vitorborbarodrigues.medium.com/m%C3%A9tricas-de-avalia%C3%A7%C3%A3o-acur%C3%A1cia-precis%C3%A3o-recall-quais-as-diferen%C3%A7as-c8f05e0a513c>.
<p>
Evaluating segmentation metrics — skimage 0.22.0rc0.dev0 documentation. 
Disponível em: https://scikit-image.org/docs/dev/auto_examples/segmentation/plot_metrics.html Acesso em: 28 set. 2023.
<p>
JORDAN, J. Evaluating image segmentation models. Disponível em: 
https://www.jeremyjordan.me/evaluating-image-segmentation-models.

‌
‌
‌
