#### Keras is the simplest ML library, so I hope you enjoy it

```
from keras.models import Sequential
from keras.layers import Dense

model = Sequential()

model.add(Dense(units=1, activation='relu', input_dim=1))
model.add(Dense(units=1))

model.compile(
    loss='mean_squared_error',
    optimizer='sgd',
    metrics=['accuracy']
)
```
1. first, we created a `sequential model`
2. then, we added two `dense layer(actually neural network)` for it. the first layer has one neural node, the second has one neural node, too.
3. sgd = Stochastic gradient descent

___

#### After that, let us feed data into our model

```

```