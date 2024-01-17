# Renderer2D

Renderer2D is a lightweight 2D batch rendering API written in C++ that uses OpenGL which is intended to be used to make 2D games/applications.
It was developed as a learning exercise, drawing inspiration from LearnOpenGL.com and other sources such as Cherno's OpenGL series so it is fairly primitive. 
Renderer2D abstracts away OpenGL boiler plate and is designed to be a starting point where more features can be added on top as needed. 
It uses GLFW for window setup and user input, so knowing how to use GLFW will be helpful as the renderer will give you the GLFWwindow pointer for you to use.
Settings like the maximum quads per draw and max texture slots may need to be tweaked depending on your system.

To use the renderer (example given in SandBox.cpp):
- include Renderer.h.
- initialise a Renderer2D object.
- retrieve the GLFWwindow pointer with the GetWindow().
- use the GLFWwindow in your render loop as you would with any GLFW application.
- Start a batch with StartBatch().
- add either coloured or textured quads to the batch with AddQuad().
- when you are finished adding quads for that frame call SubmitBatch() to send the final draw call to the GPU.

There is a helper class SpriteSheet in utils which can be used to obtain the texture coordinates needed for AddQuad().
- after initialising a spritesheet you can obtain a particular sprite's coordinates with GetTexCoords(), you just have to give it the row and column indices (topleft corner) as well as how
  many tiles wide and high you want to grab. 
