cmake_minimum_required(VERSION 4.0...4.2)
project(MyProj VERSION 0.0.1 DESCRIPTION "Gonna use this as boilerplate :)" LANGUAGES CXX)

option(BUILD_TESTING "Build the tests" ON)

add_library(myproj STATIC
    src/greeter.cpp
    include/myproj/greeter.h
)

target_include_directories(myproj
    PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:include>
    PRIVATE
        src
)

target_compile_features(myproj PUBLIC cxx_std_20)
add_library(myproj::myproj ALIAS myproj)


add_executable(myapp src/main.cpp)
target_link_libraries(myapp PRIVATE myproj::myproj)

include(${CMAKE_CURRENT_SOURCE_DIR}/cmake/GoogleTest.cmake)

if(BUILD_TESTING)
    enable_testing()
	
    add_executable(test_greeter tests/test_greeter.cpp)
    target_link_libraries(test_greeter PRIVATE myproj::myproj GTest::gtest_main)
    include(GoogleTest)
    gtest_discover_tests(test_greeter)
endif()
