# ShaderMagic

# What is a Shader?
A shader is a code running on your GPU to manipulate an image before rendering it to the screen.

## Triangle
A triangle is made up of 3 points which we call vertices. \
Each vertex has a position in 3 directions(x, y, z) in the world space.

## Projecting a Triangle
To render a triangle to a 2D screen requires two steps.
- First, the vertices of a triangle should be positioned in the world space.
- Second, the triangle needs to be colored. This could be by simply filling all pixels inside the triangle vertices with a simple color.

## Unity Shaders
Unity provides shaders to echo this process.
- Vertex Shader: Moves the vertices from model coordinates to the screen.
- Fragment Shader: Calls for each pixel. The output of this shader is in RGBA format. Each channel of RGBA format has a value between 0 and 1.

## Z-Buffering
In a 3D space, an object in front of another object will override the pixel color. Z-Buffering handles this process.
Z-Buffering holds the distance of a pixel from the camera of the previous shader and handles the rendering. \
So, when creating a shader, we should only consider what the current shader will do with the given vertices and color the pixels.

## Parallel Processing
When a shader colors the pixels on the screen in Unity, it is done by parallel processing. This means each pixel doesn't know the color information of other pixels because it is calculated simultaneously. 