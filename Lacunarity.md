# How change in Lacunarity impacts behavior of FBM waves. 

Lacunarity represents the _rate of change of the frequency_. Or, in context of the code:
```cpp
// psuedocode time
for (int i = 0; i < octaves; i++) {
     value = gen(x * frequency, y * frequency);
     frequency *= lacunarity;
}
```
When lacunarity is high, the difference between octave 1 and octave x is greater, resulting in a "noisier" image. Take for example this very simple Configuration:
```cpp
Fractal fractal (5 /*octaves*/,0.01 /*freq*/,0.05 /*amp*/,1.5 /*lac*/,0.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
```
This configuration is very basic, and gives us this image:

<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/Screenshot_20220627_132919.png" width="300" height="300">

Take note of our Lacunarity, which is 1.5 in this example.\
Ramping up the lacunarity to 2.5:

<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/lacunarity2.5.png" width="300" height="300">

You can see the massive difference this has made to the image, while the image contains the same structure (very vaguely), the existing structures have been split up into more individual valleys and peaks. 

# <0 lacunarities

When the Lacunarity is set to be less than Zero, noise and detail will decrease. For example, if we set lacunarity to be 0.1:

<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/lacunarity0.1.png" width="300" height="300">
