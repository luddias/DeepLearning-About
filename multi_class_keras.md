# Classificação multiclass com Keras
Não inicado ainda

<img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*iAK5uMoOlX1gZu-cSh1nZw.png"  width="400">

Exemplo prático:

``` python
# checkpoint
filepath="weights.best.hdf5"
checkpoint = ModelCheckpoint(filepath, monitor='val_accuracy', verbose=1, save_best_only=True, mode='max')
es = EarlyStopping(monitor='val_accuracy', patience=5)
callbacks_list = [checkpoint, es]
# Fit the model
model.fit(X, Y, validation_split=0.33, epochs=150, batch_size=10, callbacks=callbacks_list, verbose=0)
```

## Referências

[1] BROWNLEE, J. Multi-Class Classification Tutorial with the Keras Deep Learning Library.
<br> Disponível em: <https://machinelearningmastery.com/multi-class-classification-tutorial-keras-deep-learning-library/>.

‌
