cmake_minimum_required(VERSION 2.6 FATAL_ERROR)

project(mygl)

find_package(OpenGL REQUIRED)
include_directories(C:/Packages/glfw-3.1.2/include)
link_directories(C:/Packages/glfw-3.1.2/lib/Win32)

include_directories(C:/Packages/soil/src)
link_directories(C:/Packages/soil/lib/Win32)
include_directories(C:/Packages/glew-1.13.0/include)
link_directories(C:/Packages/glew-1.13.0/lib/Release/Win32)

include_directories(library ${OPENGL_INCLUDE_DIRS})

include_directories(C:/Packages/glm-0.9.7.1)
#include_directories(glm/)

set(MYGL_SRCS main.cpp shader.h ${CMAKE_SOURCE_DIR}/Shaders/shader.vertex ${CMAKE_SOURCE_DIR}/Shaders/shader.fragment)
add_executable(mygl ${MYGL_SRCS})


target_link_libraries(mygl glfw3 glew32s ${OPENGL_LIBRARIES} SOIL)