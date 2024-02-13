cmake_minimum_required(VERSION 3.16)
project(Main)

# setting c++ settings
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

file(GLOB SOURCES ${CMAKE_SOURCE_DIR}/src/*.cpp)

# add utility subdirectory
add_subdirectory(util)

# add vendor libraries
set(DEPENDENT_LIBRARIES
	glfw
	GLEW::GLEW)

set(DEPENDENT_INCLUDES
	glfw
	${CMAKE_SOURCE_DIR}/dependencies/glm
	${CMAKE_SOURCE_DIR}/src/util)

add_executable(${PROJECT_NAME} ${SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC ${DEPENDENT_INCLUDES})
target_link_libraries(${PROJECT_NAME} PUBLIC ${DEPENDENT_LIBRARIES})
