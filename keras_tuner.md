# Keras Tuner

 O Keras Tuner é uma biblioteca que ajuda você a escolher o conjunto ideal de hiperparâmetros para seu programa TensorFlow. O processo de selecionar o conjunto certo de hiperparâmetros para seu aplicativo de aprendizado de máquina (ML) é chamado de ajuste de hiperparâmetro ou hypertuning .

Os hiperparâmetros são as variáveis ​​que governam o processo de treinamento e a topologia de um modelo de ML. Essas variáveis ​​permanecem constantes ao longo do processo de treinamento e impactam diretamente no desempenho do seu programa de ML. Os hiperparâmetros são de dois tipos:

- **Hiperparâmetros do modelo** que influenciam a seleção do modelo, como o número e a largura das camadas ocultas
- **Hiperparâmetros do algoritmo** que influenciam a velocidade e a qualidade do algoritmo de aprendizado, como a taxa de aprendizado para Stochastic Gradient Descent (SGD) e o número de vizinhos mais próximos para o classificador ak Nearest Neighbors (KNN)

## Configuração

```
pip install -q -U keras-tuner
```

``` python
import keras_tuner as kt
```

## Próximos passos
Instancie o sintonizador para realizar o hypertuning. O Keras Tuner tem quatro sintonizadores disponíveis - RandomSearch , Hyperband , BayesianOptimization e Sklearn. Para instanciar o sintonizador Hyperband, você deve especificar o hipermodelo, o objective a ser otimizado e o número máximo de épocas para treinar ( max_epochs ).

```python
tuner = kt.Hyperband(model_builder,
                     objective='val_accuracy',
                     max_epochs=10,
                     factor=3,
                     directory='my_dir',
                     project_name='intro_to_kt')
```

Crie um retorno de chamada para interromper o treinamento antes de atingir um determinado valor para a perda de validação.

```python
stop_early = tf.keras.callbacks.EarlyStopping(monitor='val_loss', patience=5)
```

Execute a pesquisa de hiperparâmetros. Os argumentos para o método de pesquisa são os mesmos usados ​​para tf.keras.model.fit , além do retorno de chamada acima.

```ṕython
tuner.search(img_train, label_train, epochs=50, validation_split=0.2, callbacks=[stop_early])

# Get the optimal hyperparameters
best_hps=tuner.get_best_hyperparameters(num_trials=1)[0]

print(f"""
The hyperparameter search is complete. The optimal number of units in the first densely-connected
layer is {best_hps.get('units')} and the optimal learning rate for the optimizer
is {best_hps.get('learning_rate')}.
""")

```

Encontre o número ótimo de épocas para treinar o modelo com os hiperparâmetros obtidos na busca.

```python
# Build the model with the optimal hyperparameters and train it on the data for 50 epochs
model = tuner.hypermodel.build(best_hps)
history = model.fit(img_train, label_train, epochs=50, validation_split=0.2)

val_acc_per_epoch = history.history['val_accuracy']
best_epoch = val_acc_per_epoch.index(max(val_acc_per_epoch)) + 1
print('Best epoch: %d' % (best_epoch,))

```

Reinstanciar o hipermodelo e treiná-lo com o número ideal de épocas de cima.

```python
hypermodel = tuner.hypermodel.build(best_hps)

# Retrain the model
hypermodel.fit(img_train, label_train, epochs=best_epoch, validation_split=0.2)


```



## Fonte Bibliográfica

Introdução ao sintonizador Keras | TensorFlow Core.
<br>Disponível em: <https://www.tensorflow.org/tutorials/keras/keras_tuner?hl=pt-br>. 

‌
