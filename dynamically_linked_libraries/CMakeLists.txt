# The minimum CMake version required to build this project
cmake_minimum_required(VERSION 3.10)

# Project name
project(linking_demo)

# Create a shared library from the source files
add_library(libint SHARED add.c sub.c)

# Set the library output name as libint
set_target_properties(libint PROPERTIES OUTPUT_NAME int)

# Set the library output directory
set_target_properties(libint PROPERTIES LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/lib)

# Add the library include directory
target_include_directories(libint PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
# Create an executable using main.c and link it against the library

add_executable(main main.c)
target_link_libraries(main PRIVATE libint)
