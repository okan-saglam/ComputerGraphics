# Computer Graphics Assignments – CENG477

## Group Members
- Okan Sağlam
- Ahmet Yasin Ocak

---

## Assignment 1: Ray Tracer

This assignment involves building a basic ray tracer from scratch using C/C++. The main objective is to simulate the propagation of light in a 3D scene and generate a 2D image using ray tracing techniques.

### Key Features
- Simulates geometric optics and light propagation.
- Supports multiple camera configurations defined via XML input.
- Outputs images in the PPM format.
- Implements Blinn-Phong shading for specular highlights.
- Supports ambient and point light sources with inverse-square law attenuation.
- Optional back-face culling for performance improvements.
- Reflection support using recursive ray tracing with `MaxRecursionDepth`.
- Robust shadow computation using `ShadowRayEpsilon` to avoid self-intersections.

### Input
- Scene configuration is provided in an XML file.
- The XML format defines objects (spheres, triangles, meshes), materials, lights, and cameras.

### Sample Output

Below is a sample render output showing multiple shaded spheres with light reflection:

![Raytracer Output – Marbles](./marbles.png)

### Implementation Notes
- Executable name: `raytracer`
- Usage: `./raytracer scene.xml`

---

## Assignment 2: Software Rasterizer with Forward Rendering Pipeline

In this task, we implemented a full forward rendering pipeline including transformations and rasterization. The output is a 2D image generated from 3D mesh data using projection and rasterization algorithms.

### Key Features
- Full implementation of the **forward rendering pipeline**:
  - Modeling Transformation
  - Viewing Transformation
  - Projection Transformation
  - Rasterization
- Triangle rendering in both **wireframe** and **solid** modes.
- Backface culling support (can be enabled/disabled via input).
- Depth buffer implementation to handle visibility.
- Interpolated vertex coloring using barycentric coordinates.
- **Line drawing** using the midpoint algorithm.
- **Triangle rasterization** with color interpolation.
- **Clipping algorithm** (Cohen-Sutherland or Liang-Barsky) for wireframe mode.

### Input
- XML-based scene description file including:
  - Vertex data
  - Mesh definitions
  - Camera configurations
  - Transformations (translation, rotation, scaling)
  - Rendering mode and culling configuration

### Sample Output

Below is a rasterized scene including a horse, a mug, and a shaded cube:

![Rasterizer Output – Horse and Mug](./input_outputs/culling_enabled_outputs/horse_and_mug/horse_and_mug_2_ce.ppm.png)

### ⚙️ Technical Details
- Executable name: `rasterizer`
- Usage: `./rasterizer input.xml`
- Implemented in C++ using provided helper functions for parsing and math operations.

---

## Assignment 3: 3D Tetris-like Game Implementation

This project was a full implementation of a 3D interactive game built using OpenGL (or similar libraries). It simulates a Tetris-like block stacking game in a 3D grid.

### Game Features
- **Game Area**: 9x15x9 3D grid
- **Shapes**:
  - 3x3x3 Cube
  - 1x3x1 Column
  - 3x1x3 Row
- **Special Block**:
  - 30% chance to spawn
  - Explodes and removes blocks below it
  - Grants 10 points per block removed
- **Game Speed**:
  - Increases over time (from 0.25s to 1.5s per drop)
- **Pause Functionality**: Press `P` to pause/resume
- **Game Over**: Triggered when blocks reach the bottom layer
- **Animations**:
  - Filled layers blink 6 times before disappearing
- **Key Feedback**:
  - Last key pressed is shown on screen for 1 second
- **Visuals**:
  - Real-time score display
  - Game grid with colored blocks
  - Game area rotates on command

### Controls
- `W` – Move block forward  
- `S` – Move block backward  
- `A` – Move block left  
- `D` – Move block right  
- `P` – Pause/resume game  
- `H` – Rotate game area 90° left  
- `K` – Rotate game area 90° right  

### ⚙️ Technical Stack
- Language: C++  
- Libraries: OpenGL (GLFW/GLUT), standard math and graphics libraries  
- Modular code with clear separation of rendering, input handling, and game logic

### Sample Screenshots

Initial state of the game with a cube block:

![Tetris Start – Cube Block](./oyun1.png)

Mid-game screenshot with various stacked blocks and score display:

![Tetris Progress](./oyun2.png)

---

