# Checkpointing Modelos de Redes Neurais

Nesta abordagem, um marcador de estado do sistema é obtido em caso de falha.  Se houver um problema, nem tudo estará perdido.  O ponto de verificação pode ser usado diretamente ou como ponto de partida para uma nova corrida, continuando de onde parou.
O ModelCheckpoint também permite que seja definido onde o ponto deve marcar os pesos (weights), o nome do arquivo, e embaixo de quais circunstância ele deve realizar isso.

Exemplo prático:

```python
# checkpoint
filepath="weights-improvement-{epoch:02d}-{val_accuracy:.2f}.hdf5"
checkpoint = ModelCheckpoint(filepath, monitor='val_accuracy', verbose=1, save_best_only=True, mode='max')
callbacks_list = [checkpoint]
# Fit the model
model.fit(X, Y, validation_split=0.33, epochs=150, batch_size=10, callbacks=callbacks_list, verbose=0)
```
## Referências

How to use the ModelCheckpoint callback with Keras and TensorFlow.
<br>Disponível em: <https://pyimagesearch.com/2021/06/30/how-to-use-the-modelcheckpoint-callback-with-keras-and-tensorflow/>.

‌
