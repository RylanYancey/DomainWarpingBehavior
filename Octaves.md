# How Octave change impacts Simplex Noise wave behavior. 

To start, let's create a Simplex Noise Configuration with these paramters:

```cpp
Fractal fractal (5 /*octaves*/,0.01 /*freq*/,0.05 /*amp*/,1.5 /*lac*/,0.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
```

This is a very basic Configuration, and creates an image like this:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/Screenshot_20220627_132919.png" width="300" height="300">

You can see that this image has alot of "detail". It does not have smooth edges. This is because we have a high FBM. By decreasing the FBM, we can see that the detail will decrease. 

4 Octaves:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/octaves4.png" width="300" height="300">

3 Octaves:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/octave3.png" width="300" height="300">

2 Octaves:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/octave2.png" width="300" height="300">

1 Octave:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/octave1.png" width="300" height="300">

You can see the stark difference between these octave levels. The higher the octave, the more stronger this "Detail" effect becomes. There is a diminishing returns, however.\
15 Octaves:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/15octaves.png" width="300" height="300">
