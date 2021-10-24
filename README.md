# Building with GLFW3 and GLAD

This is my own annotations for running a build with OpenGL, GLFW and GLAD depedencies on linux.

## Installation
Paste the following set of steps to set up GLFW in your environment. (in my case I'm using arch linux)
```bash
version="3.2.1" && \
wget "https://github.com/glfw/glfw/releases/download/${version}/glfw-${version}.zip" && \
unzip glfw-${version}.zip && \
cd glfw-${version} && \
sudo pacman -S cmake xorg-dev libglu1-mesa-dev && \
sudo cmake -G "Unix Makefiles" && \
sudo make && \
sudo make install
```
###### (although running sudo make install isn't appropriate, will do it for now until I find something that works better)

### Setting up GLAD:

Download binaries and dependencies on their website: [GLAD](http://glad.dav1d.de/#profile=core&specification=gl&api=gl%3D3.3&api=gles1%3Dnone&api=gles2%3Dnone&api=glsc2%3Dnone&language=c&loader=on)



## Usage

```bash
g++ -std=c++11 -c main.cpp -Iglad/include && \
g++ main.o glad.c -o main.exec -lGL -lGLU -lglfw3 -lX11 -lXxf86vm -lXrandr -lpthread -lXi -ldl -lXinerama -lXcursor
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
