# Why
I wanted to learn OpenGL so @ChibiDenDen advised me that I should Start with a triangle... 
Little did I know lots of boilerplate is needed just to print something onto the screen :smile:

This Project is basicly a playground for OpenGL without having to deal with all the overhead of buidling an environment.
(It uses [CMake][1] to get everything up and ready)
Currently it's based on 2 subprojects:
1. [GLEW][2]
2. [GLFW][3]

## Howto Run
    cd build
    cmake .. -Wno-dev && msbuild gl_env.sln

Big Thanks to @Verose for the CMake guidance.

Some nice projects you may want to cover (that helped me):
- https://github.com/stevenlovegrove/Pangolin
- https://github.com/ArthurSonzogni/OpenGL_CMake_Skeleton

[1]: https://sourceforge.net/projects/glew "GLEW"
[2]: https://www.glfw.org/ "GLFW"
[3]: https://cmake.org "CMake"
