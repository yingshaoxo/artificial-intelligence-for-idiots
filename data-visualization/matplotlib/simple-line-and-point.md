```
import pylab
import numpy as np

# draw x^2
x = np.linspace(-5, 5) 
y = np.power(x, 2)
pylab.plot(x, y, '-k')

# draw a point
pylab.plot(2, 4, 'bo')

pylab.show()
```

![](/assets/x^2.png)

___

