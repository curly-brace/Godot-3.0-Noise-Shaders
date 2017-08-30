# Different noise shaders For Godot Engine 3.0

A port of https://github.com/ashima/webgl-noise

You can use those noises in your gdscripts using the technique shown here:
https://github.com/curly-brace/Godot-Simplex

Consists of:
- worley 2d
- worley with 2x2 window instead of 3x3
- worley 3d
- worley 3d with 2x2x2 window instead of 3x3x3
- perlin 2d
- perlin 3d
- perlin 4d
- simplex 2d
- simplex 3d
- simplex 3d with analytic derivative gradient output
- simplex 4d
- and last is 'psrdnoise' monster with 4:
  - 2-D non-tiling simplex noise with rotating gradients, without the analytical derivative
  - 2-D non-tiling simplex noise with rotating gradients and analytical derivative
  - 2-D tiling simplex noise with rotating gradients, without the analytical derivative
  - 2-D tiling simplex noise with rotating gradients and analytical derivative
 
Analytical derivatives return vec3 with first element is a vector of the noise value. And 2nd and 3rd are x and y partial derivatives.

You can test any of the shaders by creating a Sprite node, creating new ImageTexture for it (size like 256x256 would be fine), creating new shader material for it and loading desired shader to it.

All shaders have offset and scale parameters. Set scale to something like 8 to see the noise better.
Worley shaders have jitter parameter that with 0 value will output perfect squares.

More info on original repo:
https://github.com/ashima/webgl-noise/wiki

#### Drawbacks:
godot does not support (currently) in shaders: constants, inline functions, defines, for loops, better swizzling. So code is not as efficient as it could be.
