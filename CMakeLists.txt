cmake_minimum_required(VERSION 3.10)


include(CMakePrintHelpers)

project(OpenGLPlaytest)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(App 
./src/main.cpp
./src/glad.c
)

target_include_directories(App 
    PRIVATE 
    ${CMAKE_SOURCE_DIR}/include/
    )

cmake_print_variables(CMAKE_SOURCE_DIR)

find_package(OpenGL REQUIRED)
find_package(glfw3 3.4 REQUIRED)

target_link_libraries(
    App
    PRIVATE
    glfw
    )

target_link_libraries(App 
    PRIVATE
    OpenGL::GL)



target_link_libraries(App
    
    )

# target_link_libraries(App
#     PRIVATE
#     ${CMAKE_SOURCE_DIR}/glfw-3.4/build/src/libglfw3.a
#     )
#
#
