# � CityFlow - A Day Night Cycle Animation

A comprehensive OpenGL-based interactive animation project showcasing a dynamic landscape with multiple animated objects, realistic lighting, and interactive controls. This project demonstrates advanced computer graphics techniques including transformations, lighting, particle effects, and real-time rendering with a complete day-night cycle.

**Project**: CityFlow - Interactive Day/Night Cycle Visualization  
**Course**: Computer Graphics (Fall 2021-22)  
**Status**: ✅ Fully Functional  
**Platforms**: Windows (Primary), macOS (Compatible), Linux (Compatible)

---

## 📋 Table of Contents
1. [Quick Start](#-quick-start)
2. [Project Overview](#-project-overview)
3. [Features](#-features)
4. [Controls](#-controls)
5. [Installation](#-installation)
6. [Build Instructions](#-build-instructions)
7. [Code Architecture](#-code-architecture)
8. [Technical Details](#-technical-details)
9. [Troubleshooting](#-troubleshooting)
10. [Contributing](#-contributing)
11. [License](#-license)

---

## ⚡ Quick Start

Get running in 5 minutes:

**Windows (MinGW)**:
```bash
cd CG-Fall21-22
g++ -o FinalProject main.cpp -lglut32 -lopengl32 -lglu32 -lwinmm
FinalProject.exe
```

**macOS**:
```bash
cd CG-Fall21-22
clang++ -DGL_SILENCE_DEPRECATION -framework GLUT -framework OpenGL main.cpp -o FinalProject
./FinalProject
```

**Linux (Ubuntu)**:
```bash
sudo apt-get install freeglut3-dev libglu1-mesa-dev
cd CG-Fall21-22
g++ -o FinalProject main.cpp -lglut -lGL -lGLU -lm
./FinalProject
```

---

## � What is CityFlow?

**CityFlow** brings a virtual city to life with a complete day-night cycle animation. Watch as the sun moves across the sky, illuminating a bustling urban landscape with cars, trains, ships, and planes. Control the vehicles in real-time, trigger weather effects, and experience dynamic lighting that transitions naturally from sunrise to sunset and into night.

This project is perfect for:
- **Learning OpenGL graphics programming**
- **Understanding animation and lighting systems**
- **Computer graphics portfolio projects**
- **Educational demonstrations of 3D graphics concepts**

---

## �🎬 Project Overview

**CityFlow** is a Group 9 Final Project for the Computer Graphics course. This application renders a complex, interactive 3D scene featuring a complete day-night cycle with realistic environmental transitions. Watch as the city transitions from day to night with dynamic lighting, weather effects, and autonomous vehicle movement.

The application showcases:

- **Dynamic Environment**: Realistic day/night cycle with sky color transitions
- **Interactive Vehicles**: 3 controllable cars with independent speed control
- **Transportation**: Animated train and ship with audio effects
- **Atmospheric Effects**: Clouds, rain, wind, and dynamic lighting that follows the sun
- **Architecture**: Buildings, windmills, towers, and trees creating an urban landscape
- **Water Bodies**: Rivers and boats with realistic movement
- **Aviation**: Animated airplane traversing the sky

### Project Statistics
| Metric | Value |
|--------|-------|
| **Code Size** | 2,941 lines |
| **Rendering Functions** | 40+ |
| **Controllable Objects** | 6 |
| **Static Objects** | 15+ |
| **Target FPS** | 60 |
| **Memory Usage** | ~50 MB |

---

## ✨ Features

### Visual Features

#### 🏙️ Urban Environment
- Multiple architectural structures (red/blue buildings, towers, houses, phone boxes)
- Railway tracks with proper alignment
- Multi-lane roads with separating lines
- Lamp posts on both sides of roads

#### 🌄 Natural Features
- Landscape: Fields, mountains, river
- Sky Elements: Clouds (2 independent), sun with arc path, stars (night mode)
- Vegetation: Trees, parks, windmills

#### 🚗 Transportation System
| Vehicle | Motion | Control |
|---------|--------|---------|
| Car 1 | Right→Left | A/a keys |
| Car 2 | Left→Right | B/b keys |
| Car 3 | Left→Right | C/c keys |
| Train | Left | T/t keys |
| Ship | Left | S/s keys |
| Boat | Auto (→) | - |
| Airplane | Auto (→) | - |

### 🌅 Time of Day System

| Sun Position | State | Characteristics |
|-------------|-------|-----------------|
| 0.90-1.00 | Early morning | Blue-light sky |
| 0.80-0.90 | Morning | Bright blue |
| 0.65-0.80 | Midday | Clear blue |
| 0.45-0.65 | Afternoon | Warming sky |
| 0.25-0.45 | Late afternoon | Orange tones |
| 0.10-0.25 | Sunset | Deep orange/red |
| Below 0.10 | Night | Dark |

**Dynamic Lighting**: Point light source follows sun, with ambient/diffuse/specular adjustments

### 🌧️ Weather Effects
- **Visual**: Particle-based rain animation
- **Audio**: Realistic rain sound (Windows)
- **Trigger**: Press 'R' key to toggle
- **Sky Integration**: Sky changes to gray during rain
- **Continuous Loop**: Rain loops seamlessly

### 🎨 Interactive Features
- **Immediate Response**: Controls take effect instantly
- **Simultaneous Control**: Operate multiple vehicles at once
- **Smooth Animation**: 60 FPS target framerate
- **Real-time Updates**: 20ms timer intervals

---

## 🎮 Controls

### Vehicle Control
```
A/a ........... Speed up/down Car 1
B/b ........... Speed up/down Car 2
C/c ........... Speed up/down Car 3
T/t ........... Speed up/down Train
S/s ........... Speed up/down Ship
R/r ........... Toggle Rain ON/OFF
```

### System Controls
```
↑ (Up Arrow) ... Activate all vehicles
↓ (Down Arrow) . EXIT application
ESC ............ EXIT application
```

### Try These:
1. Press 'A' repeatedly to speed up car 1
2. Press 'R' to toggle rain effect
3. Hold 'T' while pressing up arrow
4. Watch the lighting change with sun position
5. Try multiple keys simultaneously

---

## 📦 Installation

### Prerequisites

**Windows**:
- Visual Studio 2019+ OR MinGW compiler
- OpenGL libraries (usually included with graphics drivers)
- GLUT library (glut32)

**macOS**:
- Xcode Command Line Tools: `xcode-select --install`
- GLUT and OpenGL frameworks (built-in)

**Linux (Ubuntu/Debian)**:
```bash
sudo apt-get update
sudo apt-get install freeglut3-dev libglu1-mesa-dev build-essential
```

**Linux (Fedora/RHEL)**:
```bash
sudo dnf install freeglut-devel mesa-libGL-devel mesa-libGLU-devel gcc-c++ make
```

**Linux (Arch)**:
```bash
sudo pacman -S freeglut glu base-devel
```

---

## 🔨 Build Instructions

### Windows - MinGW

```bash
cd CG-Fall21-22
g++ -o FinalProject main.cpp -lglut32 -lopengl32 -lglu32 -lwinmm
FinalProject.exe
```

**Debug Build**:
```bash
g++ -g -o FinalProject_debug main.cpp -lglut32 -lopengl32 -lglu32 -lwinmm
```

**Release Build** (Optimized):
```bash
g++ -O2 -o FinalProject main.cpp -lglut32 -lopengl32 -lglu32 -lwinmm
```

### Windows - Visual Studio 2019+

1. Create new Empty Project
2. Add `main.cpp` to project
3. Project → Properties
4. VC++ Directories:
   - Include Directories: Add OpenGL/GLUT paths
   - Library Directories: Add library paths
5. Linker → Input → Additional Dependencies:
   - Add: `glut32.lib opengl32.lib glu32.lib winmm.lib`
6. Ctrl+Shift+B to build, F5 to run

### macOS - Command Line

```bash
cd CG-Fall21-22
clang++ -DGL_SILENCE_DEPRECATION -framework GLUT -framework OpenGL main.cpp -o FinalProject
./FinalProject
```

**Debug Build**:
```bash
clang++ -g -DGL_SILENCE_DEPRECATION -framework GLUT -framework OpenGL main.cpp -o FinalProject_debug
lldb ./FinalProject_debug
```

### macOS - Xcode

1. New → Project → Command Line Tool
2. Language: C++
3. Drag `main.cpp` into project
4. Select Project → Target → Build Phases
5. Link Binary with Libraries:
   - Add: GLUT.framework, OpenGL.framework
6. Product → Build (Cmd+B), Run (Cmd+R)

### macOS - Makefile

Create `Makefile`:
```makefile
CXX = clang++
CXXFLAGS = -DGL_SILENCE_DEPRECATION -framework GLUT -framework OpenGL
TARGET = FinalProject
SOURCES = main.cpp

all: $(TARGET)

$(TARGET): $(SOURCES)
	$(CXX) $(CXXFLAGS) -o $@ $^

clean:
	rm -f $(TARGET) *.o

run: $(TARGET)
	./$(TARGET)

.PHONY: all clean run
```

Then: `make` (build), `make run` (run), `make clean` (clean)

### Linux - GCC

```bash
cd CG-Fall21-22
g++ -o FinalProject main.cpp -lglut -lGL -lGLU -lm
./FinalProject
```

**Debug Build**:
```bash
g++ -g -o FinalProject_debug main.cpp -lglut -lGL -lGLU -lm
gdb ./FinalProject_debug
```

**Fedora/RHEL**:
```bash
g++ -o FinalProject main.cpp -lglut -lGL -lGLU -lm
```

**Makefile for Linux**:
```makefile
CXX = g++
CXXFLAGS = -Wall -O2
TARGET = FinalProject
SOURCES = main.cpp
LIBS = -lglut -lGL -lGLU -lm

all: $(TARGET)

$(TARGET): $(SOURCES)
	$(CXX) $(CXXFLAGS) -o $@ $^ $(LIBS)

clean:
	rm -f $(TARGET) *.o

run: $(TARGET)
	./$(TARGET)

.PHONY: all clean run
```

---

## 🏗️ Code Architecture

### Main Components

#### Animation System
```
update_car_1()       → Car 1 animation
update_car_2()       → Car 2 animation
update_car_3()       → Car 3 animation
update_train()       → Train animation
update_ship()        → Ship animation
update_sun()         → Sun movement (time of day)
update_cloud_1()     → Cloud 1 movement
update_cloud_2()     → Cloud 2 movement
update_boat()        → Boat animation
update_plane()       → Airplane animation
```

Each uses `glutTimerFunc()` for consistent 20ms updates

#### Rendering System
```
myDisplay()          → Main display callback
sky()                → Background rendering
sun()                → Sun and stars
field_1(), field_2() → Ground areas
buildings()          → Urban structures
vehicles()           → Cars, train, ship rendering
rain()               → Weather particles
```

#### Input Handling
```
keyboard()           → Alphanumeric keys (vehicle control)
specialKeys()        → Arrow keys (system control)
```

#### Lighting
```
PointLight()         → Dynamic light source
skyColoring()        → Adjusts lighting based on sun position
```

### Global Variables

```cpp
// Vehicle positions and speeds
float _move_car_1, _speed_car_1;      // Car 1
float _move_car_2, _speed_car_2;      // Car 2
float _move_car_3, _speed_car_3;      // Car 3
float _move_train, _speed_train;      // Train
float _move_ship, _speed_ship;        // Ship

// Natural elements
float _move_sun;                      // Sun position (time indicator)
float _move_cloud_1, _move_cloud_2;   // Cloud positions
float _move_boat;                     // Boat position
float position;                       // Airplane position

// State
bool isRain;                          // Rain effect toggle
```

### Project Structure

```
Computer_Graphics-Fall21-22/
├── README.md                      ← This file
├── CG-Fall21-22/
│   ├── main.cpp                   ← Main application
│   ├── FinalProject.cbp           ← Code::Blocks config
│   ├── FinalProject.depend        ← Dependencies
│   ├── bin/Debug/
│   │   ├── FinalProject.exe       ← Windows executable
│   │   └── rain.wav               ← Rain sound
│   └── sound/                     ← Secondary project
└── LICENSE                        ← MIT License
```

---

## 🔧 Technical Details

### Graphics Pipeline

```
Display Callback (myDisplay):
├─ Clear buffers (color + depth)
├─ Sky rendering with gradient
├─ Environment (fields, mountains)
├─ Infrastructure (roads, tracks)
├─ Vehicles (cars, train, ship)
├─ Natural elements (clouds, trees)
├─ Special effects (rain)
├─ Buffer swap (double buffering)
└─ Target: 60 FPS
```

### OpenGL Features Used

```cpp
// Core Rendering
glBegin(GL_QUADS) / glEnd()
glBegin(GL_TRIANGLES) / glEnd()
glBegin(GL_POLYGON) / glEnd()

// Colors and Properties
glColor3f(), glColor4f()
glScalef(), glTranslatef(), glRotatef()

// Matrix Operations
glPushMatrix(), glPopMatrix()
glLoadIdentity()

// Lighting
glLightfv(), glEnable(GL_LIGHTING)
glEnable(GL_LIGHT0)

// Depth Testing
glEnable(GL_DEPTH_TEST)

// Buffer Management
Double buffering, glutSwapBuffers()
```

### GLUT Integration

```cpp
glutInit()                  → Initialize GLUT
glutInitDisplayMode()       → Set display options
glutCreateWindow()          → Create window
glutDisplayFunc()           → Set display callback
glutKeyboardFunc()          → Set keyboard callback
glutSpecialFunc()           → Set special keys callback
glutTimerFunc()             → Set timer callback
glutMainLoop()              → Start event loop
```

### Performance Optimization

- **Double Buffering**: Eliminates flicker
- **Vertex Arrays**: Efficient polygon rendering
- **Culling**: Off-screen objects not rendered
- **Matrix Caching**: Reduce transformation overhead
- **Consistent Timing**: 20ms updates for smooth motion

### Lighting Model

**Point Light Source** with:
- Ambient component (background light)
- Diffuse component (main lighting)
- Specular component (highlights)

Adjusts dynamically based on sun position throughout day

---

## 🐛 Troubleshooting

### "glut.h: No such file or directory"

**Windows**:
```bash
# Verify MinGW includes
dir "C:\MinGW\include\GL"
# If missing, download GLUT from: http://www.xmission.com/~nate/glut.html
# Extract to C:\MinGW
```

**macOS**:
```bash
# Update Xcode tools
xcode-select --install
# Verify frameworks
ls /System/Library/Frameworks/ | grep -i glut
```

**Linux**:
```bash
# Ubuntu
sudo apt-get install freeglut3-dev

# Fedora
sudo dnf install freeglut-devel

# Arch
sudo pacman -S freeglut
```

### "undefined reference to 'glutInit'"

Missing linker flags. Use correct syntax for your OS:
- **Windows**: `-lglut32 -lopengl32 -lglu32 -lwinmm`
- **macOS**: `-framework GLUT -framework OpenGL`
- **Linux**: `-lglut -lGL -lGLU -lm`

### "cannot find -lglut"

**Solution**: Install development files
```bash
# Ubuntu
sudo apt-get install freeglut3-dev

# Fedora
sudo dnf install freeglut-devel

# macOS: Already available via frameworks
```

### Application window won't open

**macOS**:
```bash
./FinalProject &
# Or check: System Preferences → Mission Control
# Uncheck "Displays have separate spaces"
```

**Linux**:
```bash
# Check DISPLAY variable
echo $DISPLAY
export DISPLAY=:0
./FinalProject
```

**Windows**: Update graphics drivers

### Audio not working

- **Windows**: Verify `rain.wav` in same directory as exe
- **macOS/Linux**: Audio currently Windows-only in source code

### Compilation is slow

Use multiple cores:
```bash
# Linux/macOS
g++ -j$(nproc) main.cpp -o FinalProject ...

# Windows (PowerShell)
g++ -j4 main.cpp -o FinalProject ...
```

### Performance issues (flickering, lag)

- Ensure you have 60 FPS target
- Close other applications
- Update graphics drivers
- Try debug vs release build
- Check if double buffering is enabled

---

## 🤝 Contributing

### How to Report Issues

When filing a bug report, include:

1. **Description**: Clear bug description
2. **Steps to Reproduce**: Exact reproduction steps
3. **Expected Behavior**: What should happen
4. **Actual Behavior**: What actually happens
5. **Environment**: OS, compiler, graphics driver
6. **Screenshots/Logs**: Visual proof or error messages

### How to Suggest Improvements

1. **Title**: Feature description
2. **Motivation**: Why would this be useful?
3. **Proposal**: How should it work?
4. **Examples**: Code examples or mockups

### Pull Request Process

1. Fork the repository
2. Create feature branch: `git checkout -b feature/your-feature`
3. Make changes following code style guidelines
4. Test thoroughly on your platform
5. Commit: `git commit -m "feat: description"`
6. Push: `git push origin feature/your-feature`
7. Submit pull request with clear description

### Coding Style

**Naming Conventions**:
```cpp
// Variables: snake_case
float movement_speed = 0.025f;
bool is_raining = false;

// Functions: snake_case
void update_vehicle_position(int value);
void render_scene();

// Constants: UPPERCASE_SNAKE_CASE
const float MAX_SPEED = 1.0f;
const int WINDOW_WIDTH = 1366;

// Classes: PascalCase
class Vehicle {};
```

**Formatting**:
- Indentation: 4 spaces (no tabs)
- Line length: Max 120 characters
- Braces: Opening brace on same line
- Comments: Explain WHY, not WHAT

### Contribution Types

**Easy** (Good for beginners):
- Add comments to functions
- Fix minor bugs
- Create build guides
- Add documentation

**Medium** (Some graphics knowledge):
- Optimize rendering
- Add new objects
- Improve controls
- Create utilities

**Advanced** (Deep graphics knowledge):
- Port to modern OpenGL
- Implement complex effects
- Refactor architecture
- Optimize performance

---

## 📚 Learning Value

This project teaches:

✅ **Graphics Fundamentals**
- 3D coordinate transformations
- Projection matrices
- Depth testing and z-buffering

✅ **OpenGL Concepts**
- Vertex and triangle rendering
- Color and material properties
- Lighting models
- Matrix operations

✅ **Animation Techniques**
- Timer-based updates
- Movement interpolation
- Cyclic animations

✅ **Software Design**
- Modular function design
- State management
- Event handling
- Performance optimization

---

## 🔄 System Requirements

| Requirement | Minimum | Recommended |
|-----------|---------|-------------|
| **RAM** | 512 MB | 2 GB |
| **GPU** | OpenGL 1.2 | OpenGL 2.0+ |
| **Resolution** | 1024x768 | 1366x768+ |
| **Processor** | Any modern CPU | Multi-core |
| **Disk Space** | 50 MB | 100 MB |

---

## 🎯 Known Issues & Limitations

- **Platform-Specific**: Originally for Windows, adapted for macOS/Linux
- **Deprecated APIs**: Uses older OpenGL/GLUT (still functional)
- **Audio**: Windows-only PlaySound API
- **Resolution**: Hard-coded to 1366x768
- **Single-threaded**: All on main thread

## 🔧 Potential Improvements

- [ ] Port to modern OpenGL (3.3+)
- [ ] Cross-platform audio (SFML/SDL2)
- [ ] Resizable window support
- [ ] Frame rate independent movement
- [ ] Configuration file support
- [ ] Scene editor
- [ ] Advanced particle system
- [ ] Shadows and post-processing

---

## 📖 References & Resources

**Graphics Learning**:
- OpenGL Tutorials: https://learnopengl.com/
- GLUT Documentation: http://www.opengl.org/resources/libraries/glut/
- Computer Graphics: https://www.cs.unm.edu/~angel/

**Tools**:
- Visual Studio: https://visualstudio.microsoft.com/
- Xcode: https://developer.apple.com/xcode/
- Code::Blocks: http://www.codeblocks.org/

---

## 📄 License

This project is licensed under the **MIT License** - see LICENSE file for details.

**For Academic Use**: Please follow your institution's academic integrity policies when using this code.

---

## 👥 Authors & Project Info

**CityFlow - A Day Night Cycle Animation**  
Group 9 - Computer Graphics Course Final Project  
Fall 2021-22 Academic Year

This project showcases real-time graphics rendering with dynamic environmental effects, interactive vehicle control, and a complete day-night cycle system.

---

## 📞 Support

**Have questions?**
1. Check this README's troubleshooting section
2. Review the code comments in main.cpp
3. Check the project's GitHub issues
4. Open a new GitHub issue for help

---

**Last Updated**: March 18, 2026  
**Status**: ✅ Fully Functional  
**Platforms**: Windows, macOS, Linux

🎨 **Enjoy the graphics project!** 🎉
