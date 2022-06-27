# How change in Persistence impacts FBM Wave behavior:

To start, lets create a very simple Configuration:
```cpp
Fractal fractal (5 /*octaves*/,0.01 /*freq*/,0.05 /*amp*/,1.5 /*lac*/,0.5 /*pers*/,255.0 /*max*/,0.0 /*min*/);
```
This configuration is very basic, and creates an image like this:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/Screenshot_20220627_132919.png" width="300" height="300">

Take note of the Persistence variable, which is 0.5 for this example.
If we decrease the persistence to be 0.1:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/persistence0.1.png" width="300" height="300">

We get this very boring image. This is because the persistence is the rate of change of the amplitude, or in the context of the code:
```cpp
for (int i = 0; i < octaves; i++) {
     output += (amplitude * gen(x, y));
     amplitude *= persistence;
}
```
Persistence is the direction in which output values grow. (i don't fully understand either tbh)

If we increase the persistence, we get something very interesting. 
Persistence of 0.9:\
<img src="https://github.com/RylanYancey/DomainWarpingBehavior/blob/main/images/persistence0.9.png" width="300" height="300">

The image is broken up, similar to lacunarity. However, Lacunarity and Persistence function in very different ways, and they impact each other. Learning to use Lac and Pers is not easy. 
