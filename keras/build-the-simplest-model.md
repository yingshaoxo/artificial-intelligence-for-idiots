#### Keras is the simplest ML library, so I hope you enjoy it

```
from keras.models import Sequential
model = Sequential()

from keras.layers import Dense
model.add(Dense(units=1, activation='relu', input_dim=1))
model.add(Dense(units=1))
model.compile(
    loss='mean_squared_error',
    optimizer='sgd',
    metrics=['accuracy'])
```