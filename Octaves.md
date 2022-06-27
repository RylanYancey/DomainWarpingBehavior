# How Octave change impacts FBM wave behavior. 

To start, let's create a Simplex Noise Configuration with these paramters:

```cpp
Fractal fractal (5 /*octaves*/,0.01 /*freq*/,1.5 /*lac*/,0.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
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

# Pitfall of Octaves

As Octaves increases, the distribution of values goes toward the center of the range. For example, if your range is 0-255, and you have 1 octave, your distribution will be uniform. If your range is 0-255, and you have 10 octaves, a majority of your values will be around 127.5. You can see this in the images, since the image of 15 octaves is mostly gray, while the one with 1 octave is mostly black and white. 
