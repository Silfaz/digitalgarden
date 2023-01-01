---
title: "The Nature of Code"
---

## Perlin noise
https://www.youtube.com/watch?v=Qf4dIN99e2w&list=PLRqwX-V7Uu6ZV4yEcW3uDwOgGXKUUsPOM&index=3


`random` and `noise` functions in p5. The `noise` function refers to Perlin noise, which was originally developed for procedural textures of 3D objects. 


Perlin noise gives "smooth random" numbers. The previous number is related to the next one, and that one to the next, etc. In true randomness on the other hand, the numbers are completely unrelated. 


`random(min, max)` --> a new random value every time it's run

`noise(xoff)` --> same value between 0 and 1 until it's refresehd. To get different values, change xoff (e.g. xoff += 0.01). 



### 1-dimensional Perlin noise
