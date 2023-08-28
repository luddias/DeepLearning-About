# Early Stoping
A Parada Antecipada é uma maneira muito diferente de regularizar o modelo de aprendizado de máquina.  A forma como isso acontece é interromper o treinamento assim que o erro de validação atingir o mínimo.  A figura abaixo mostra um modelo sendo treinado.
O EarlyStoping monitora o desempenho do modelo para cada época em um conjunto de validação retido durante o treinamento e encerra o treinamento condicional ao desempenho da validação [2].

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

[1] CHEN, B. A Practical Introduction to Early Stopping in Machine Learning.
<br>Disponível em: <https://towardsdatascience.com/a-practical-introduction-to-early-stopping-in-machine-learning-550ac88bc8fd>.

[2] AURÉLIEN GÉRON. Hands-on machine learning with Scikit-Learn and TensorFlow concepts, tools, and techniques to build intelligent systems. 2. ed. [s.l.] O’Reilly Media, Inc., 2019.

‌[3] BROWNLEE, J. How to Check-Point Deep Learning Models in Keras.
<br>Disponível em: <https://machinelearningmastery.com/check-point-deep-learning-models-keras/>.

‌


‌
