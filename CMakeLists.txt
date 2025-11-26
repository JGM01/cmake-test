cmake_minimum_required(VERSION 3.19...4.2)
project(CMakeTest VERSION 0.0.1 DESCRIPTION "Gonna use this as boilerplate :)" LANGUAGES CXX)

add_library(lib lib.cpp lib.hpp)

add_executable(exec main.cpp)

target_link_libraries(exec PRIVATE lib)
