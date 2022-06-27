# How Octave change impacts Simplex Noise wave behavior. 

To start, let's create a Simplex Noise Configuration with these paramters:

```cpp
Fractal fractal (5 /*octaves*/,0.01 /*freq*/,0.05 /*amp*/,1.5 /*lac*/,0.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
```

This is a very basic Configuration, and creates an image like this:
