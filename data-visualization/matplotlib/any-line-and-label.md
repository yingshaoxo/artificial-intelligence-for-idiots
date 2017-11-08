```
import pylab
import numpy as np

def draw_a_line(formula, x_range, label=''):  
    x = np.array(x_range)  
    y = eval(formula)
    pylab.plot(x, y, '-', label=label)

# draw -x^2
x = np.linspace(-5, 1.5)
y = np.negative(np.power(x, 2))
pylab.plot(x, y, '-k', label = r'$y = -x^2$')

# draw two lines
draw_a_line('2*x + 1', range(-5, 3))
draw_a_line('(2/5)*(x + 1/5) - 1/25', range(-5, 3))

# draw a point
pylab.plot(-1, -1, 'bo', label = r'$y^\prime(1) = -2$')
pylab.plot(-0.2, -1/25, 'ro', label = r'$y^\prime(-\frac{1}{2}) = -\frac{1}{25}$')

pylab.legend(loc='lower right')
pylab.show()

```

![](/assets/negative_x^2.png)