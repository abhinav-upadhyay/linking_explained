# minimum CMake version required to build our project
cmake_minimum_required(VERSION 3.10)
# Set the project name as linking_explained
project(linking_explained)
# add an executable with name "main", which depends on main.c and add.c
add_executable(main main.c add.c)
