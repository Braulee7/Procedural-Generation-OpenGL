cmake_minimum_required(VERSION 3.16)
project(Procedural_Generation VERSION 1.0 LANGUAGES CXX)

list(APPEND CMAKE_PREFIX_PATH "dependencies/glew")
find_package(GLEW REQUIRED)

add_subdirectory(dependencies/glm)
add_subdirectory(dependencies/glfw)
add_subdirectory(src)
