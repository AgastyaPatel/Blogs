---
tags:
  - GPU
---

### What is OpenGL ?
OpenGL is specification just like C++ standard specification

### Where to download OpenGL?
There's no code/library as it is specification. The code is being written by the GPU manufactures by suppling the drivers which contains the code.
- It's not open-source.
- Cross-Platform compatibility

## Different parts of openGL
1.  Setting Up OpenGL:

    -   Install the necessary OpenGL libraries and drivers for your platform.
    -   Choose a programming language that supports OpenGL, such as C++, Python (with libraries like PyOpenGL), or Java (with libraries like LWJGL or JOGL).
2.  Creating a Window:
    
    -   Use a windowing system library (e.g., GLFW, SDL, or FreeGLUT) to create a window where you can render OpenGL graphics.
3.  Context and Initialization:
    
    -   Create an OpenGL context within the window to initialize the OpenGL state.
    -   Retrieve function pointers for the OpenGL functions using a library like GLEW or GLAD.
4.  Rendering Loop:
    
    -   Set up a loop that will execute continuously to update and redraw the graphics.
    -   Within the loop, clear the frame buffer using `glClear()` to prepare for drawing new content.
5.  Coordinate Systems:
    
    -   Understand the coordinate system used in OpenGL: the viewport, which is a 2D or 3D space where your graphics will be displayed.
    -   Define your objects' positions and sizes in this coordinate system.
6.  Creating and Binding Buffers:
    
    -   Use buffer objects (`glGenBuffers()`, `glBindBuffer()`) to store vertex data, such as positions, colors, and texture coordinates.
    -   Buffer objects are typically used with vertex arrays (`glVertexAttribPointer()`) to describe the format and layout of the vertex data.
7.  Shaders and Shader Programs:
    
    -   Use shaders (vertex and fragment shaders) to define the behavior and appearance of your objects.
    -   Compile and link shaders into a shader program (`glCreateShader()`, `glCreateProgram()`, `glAttachShader()`, `glLinkProgram()`) to be used during rendering.
8.  Drawing:
    
    -   Use `glDrawArrays()` or `glDrawElements()` to issue draw calls, specifying the primitive type (points, lines, triangles), vertex count, and indices (if using indices).
9.  Transformation and Projection Matrices:
    
    -   Apply transformations (translations, rotations, scaling) to your objects using transformation matrices (`glTranslate()`, `glRotate()`, `glScale()`).
    -   Use projection matrices (`gluPerspective()`, `glOrtho()`) to define the perspective or orthographic projection of your scene.
10.  Handling User Input:
       -   Use libraries or system functions to handle user input, such as keyboard and mouse events, to interact with your OpenGL application.
11. 
	-   Clean up resources: Properly release any allocated resources, such as shaders, buffers, and the OpenGL context, when your application exits.

## Context/Window Toolkits
Creating window in windows in Window's OS uses win32 api...similarly creating window is very much platform specific and uses its own api.

### GLFW Library aka Window_GUI_Creator
GLFW is a lightweight library which helps us to create windows with cross compatibility by supplying
- appropriate platform layout
- open source in nature

## OpenGL Function Extractor
### GLEW/GLAD Libraries aka Extractor
GLEW/GLAD libraries is used to retrieve the openGL functions which are present in binary form in Graphics driver. The retrieving these function is platform specific.
- access driver dll files 
- access function pointers (function definition)
- provides header files (function declaration)

>glew.h provides opengl function declaration
>.cpp file is used to extract the function definition from drivers 

What is shader?
A program which is running on GPU which gives output.

---------------------

# Cherno's OpenGL (GLEW)
```C
#include <GL/glew.h>
#include <GLFW/glfw3.h>
#include <iostream>


int main()
{
	GLFWwindow* window;

	if (!glfwInit())
	{
		return -1;
	}

	window = glfwCreateWindow(800, 800, "Modern OpenGL using glew", NULL, NULL);

	// window creation failcheck 
	if (!window)
	{
		glfwTerminate();
		return -1;
	}

	// Make the window's context current
	glfwMakeContextCurrent(window);

	// Initializing glew (Modern OpenGL)
	if (glewInit() != GLEW_OK)
		std::cout << "Error!" << std::endl;

	// Printing out OpenGL Version
	std::cout << glGetString(GL_VERSION) << std::endl;

	// Run loop untill window is open
	while (!glfwWindowShouldClose(window))
	{
		glClear(GL_COLOR_BUFFER_BIT);

		// define GL triangle
		glBegin(GL_TRIANGLES);
		glVertex2f(-0.05f, 0.0f);
		glVertex2f(0.0f, 0.05f);
		glVertex2f(0.05f, 0.0f);
		glEnd();

		glfwSwapBuffers(window);

		// Process poll events
		glfwPollEvents();
	}
	glfwTerminate();
	return 0;
}
```

What is Buffer?
- Memory buffer or array in openGL aka memory in VRAM (GPU)
- Rasterizing that vram data or buffer to draw the data on screen. This program is shader.
- Shader is a program which runs on the GPU 

OpenGL is state machine
- it needs to select the buffer like GL_TRIANGLE
- it needs to select the shader 
- it uses 

-----------------------

# VictorGordan_LearnOpenGL (GLAD)
- GLFW for Windows Context Creation
- GLAD to retrieve openGL function

GLFW building using CMAKE and VS. 
1. CMAKE is used to build sln/workplace files which is required for the VS project
2. Using .sln file open GLFW solution and build the glfw.lib file.
3. Import/copy the library file to OpenGL project directory.

### GLFW Template
```cpp
#include <iostream>
#include <glad/glad.h>
#include <GLFW/glfw3.h>

int main()
{
	glfwInit();					//Intialising GLFW (OpenGL extractor)
	
	//Hinting the version
	glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);	
	glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
	glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);	//Hinting the profile(CORE(modern)/COMPACTability(legacy)

	GLFWwindow* window = glfwCreateWindow(800, 800, "VictorGordan_Opengl", NULL, NULL);

	if (window == NULL)			//Terminating GLFW if fails to create window
	{
		std::cout << "Failed to create GLFW window" << std::endl;
		glfwTerminate();
		return -1;
	}
	glfwMakeContextCurrent(window);

	//Closing Window only on userCloseEvent
	while (!glfwWindowShouldClose(window))
	{
		glfwPollEvents();		//Process Poll Events
	}

	glfwDestroyWindow(window);	//destroying GLFW window
	glfwTerminate();			//Terminating GLFW
	return 0;
}
```


## What is Buffer?
Changing of pixel from top of the screen to bottom. 
New image data is know as Front Buffer whereas the screen image on which the current data is being overwritten with Front Buffer is known as Back Buffer

```cpp
//Adding background with the help of GLAD and buffer
#include <iostream>
#include <glad/glad.h>
#include <GLFW/glfw3.h>

int main()
{
	glfwInit();					//Intialising GLFW (OpenGL extractor)
	
	//Hinting the version of OPENGL to glfw
	glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);	
	glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
	glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);	//Hinting the profile(CORE(modern)/COMPACTability(legacy)

	GLFWwindow* window = glfwCreateWindow(800, 800, "VictorGordan_Opengl", NULL, NULL);

	if (window == NULL)			//Error check if window fails to create then terminating GLFW 
	{
		std::cout << "Failed to create GLFW window" << std::endl;
		glfwTerminate();
		return -1;
	}

	//introduce the window to current context
	glfwMakeContextCurrent(window);

	//Load GLAD (OpenGL extractor)
	gladLoadGL();

	glViewport(0, 0, 800, 800);
	
	glClearColor(0.07f, 0.13f, 0.17f, 1.0f);	//specify the color of background
	glClear(GL_COLOR_BUFFER_BIT);				//clean the back buffer and assign the new color to it
	glfwSwapBuffers(window);					//swap the back buffer with the front buffer

	//Closing Window only on userCloseEvent
	while (!glfwWindowShouldClose(window))
	{
		glfwPollEvents();		//Process Poll Events
	}

	glfwDestroyWindow(window);	//destroying GLFW window
	glfwTerminate();			//Terminating GLFW
	return 0;
}
```

## Graphics a pipeline
Graphics pipeline is made up of series of functions which takes input like vertex data and sends the output.
1. Vertex Shader
2. Shape Assembly
3. Geometry Shader

