cmake_minimum_required(VERSION 3.1...3.29)

project(
    plox
    VERSION 1.0
    LANGUAGES CXX
)

set(CMAKE_CXX_FLAGS -std=c++20)
set(CMAKE_CXX_STANDARD 20)

file(GLOB_RECURSE SOURCES
    src/*.cpp
)

add_executable(plox ${SOURCES})

add_custom_target(run
    COMMAND plox
    DEPENDS plox
    WORKING_DIRECTORY ${CMAKE_PROJECT_DIR})

add_custom_target(test
    COMMAND plox $(TEST)
    DEPENDS plox
    WORKING_DIRECTORY ${CMAKE_PROJECT_DIR})