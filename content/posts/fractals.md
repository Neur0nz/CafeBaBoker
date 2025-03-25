---
title: "Fractals: Where Mathematics Meets Art"
date: 2024-03-22
draft: false
tags: ["mathematics", "fractals", "geometry"]
categories: ["mathematics"]
math: true
---
Fractals are fascinating mathematical objects that exhibit self-similarity at different scales. They appear in nature, art, and mathematics, creating beautiful and complex patterns from simple rules.

## The Mandelbrot Set

One of the most famous fractals is the Mandelbrot set, defined by the iteration:

$$
z_{n+1} = z_n^2 + c
$$

where z₀ = 0 and c is a complex number.

![Mandelbrot Set](/images/mandelbrot.jpg)

## Fractal Dimension

Unlike regular geometric shapes, fractals often have non-integer dimensions. The Hausdorff dimension D of a fractal can be calculated using:

$$
D = \frac{\log(N)}{\log(1/r)}
$$

where N is the number of self-similar pieces and r is the scaling factor.

## Famous Fractals

### The Koch Snowflake

Starting with an equilateral triangle, each side is divided into three segments. The middle segment is replaced with two segments forming an equilateral triangle:

![Koch Snowflake](/images/koch-snowflake.jpg)

### The Sierpinski Triangle

Created by repeatedly removing triangular sections from a larger triangle:

![Sierpinski Triangle](/images/sierpinski.jpg)

## Applications

Fractals have practical applications in:
1. Computer graphics
2. Antenna design
3. Data compression
4. Natural phenomena modeling

## Creating Fractals

Here's a simple Python code to generate the Mandelbrot set:

```python
import numpy as np
import matplotlib.pyplot as plt

def mandelbrot(h, w, max_iter):
    y, x = np.ogrid[-1.4:1.4:h*1j, -2:0.8:w*1j]
    c = x + y*1j
    z = c
    divtime = max_iter + np.zeros(z.shape, dtype=int)
    
    for i in range(max_iter):
        z = z**2 + c
        diverge = z*np.conj(z) > 2**2
        div_now = diverge & (divtime == max_iter)
        divtime[div_now] = i
        z[diverge] = 2
    
    return divtime

plt.imshow(mandelbrot(400, 400, 50))
plt.axis('off')
plt.show()
```

## Conclusion

Fractals demonstrate how simple mathematical rules can create complex and beautiful patterns. They bridge the gap between mathematics and art, showing that beauty can emerge from pure mathematical principles. 