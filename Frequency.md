# How change in Frequency impacts FBM Wave behavior

To start, let's create a Simplex Noise Configuration with these paramters:

```cpp
Fractal fractal (5 /*octaves*/,0.01 /*freq*/,1.5 /*lac*/,0.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
```

This is a very basic configuration, and creates an image like this:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/Screenshot_20220627_132919.png" width="300" height="300">

Take note of how "Zoomed In" we are on this image. In this particular one, we are not zoomed in very much. Note how our "Frequency" variable is set to 0.01. If we change this variable to be smaller, we will zoom in more. 

Frequency of 0.009:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/freq0.09.png" width="300" height="300">

You can already see that decreasing the frequency by 0.001 has already drastically impacted the image. The image retains the features of the original, but is zoomed in with respect to the top-left corner (which is 0, 0)

Frequency of 0.005:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/0.005Freq.png" width="300" height="300">

We continue to zoom in closer and closer to the top-left, but the size of the image is still the same and we still have the features of the original image. 

You can see where this is going, eventually all we will be able to see is a single color. 

# Pitfall of Frequency:

If the frequency is too high, the resulting noise will appear to be static, or "random"

Frequency of 0.9:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/frequency0.9.png" width="300" height="300">

# >1 Frequency Behavior:

Generally speaking, >1 frequencies are pointless and will appear as static. However, in some circumstances, it can create images like this:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/positive%20freq.png" width="300" height="300">

To generate this, you need a >1 frequency, <1 lacunarity, >1 persistence, <1 amplitude:

```cpp
Fractal fractal (5 /*octaves*/,1.5 /*freq*/,0.5 /*amp*/,0.01 /*lac*/,1.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
```

It's useless, but kind of interesting. It occurs because the noise starts of as static but transitions into usable noise. 
