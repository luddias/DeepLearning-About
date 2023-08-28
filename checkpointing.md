# Checkpointing Modelos de Redes Neurais

Nesta abordagem, um marcador de estado do sistema é obtido em caso de falha.  Se houver um problema, nem tudo estará perdido.  O ponto de verificação pode ser usado diretamente ou como ponto de partida para uma nova corrida, continuando de onde parou.
O ModelCheckpoint também permite que seja definido onde o ponto deve marcar os pesos (wights), o nome do arquivo, e embaixo de quais circunstância ele deve realizar isso.
