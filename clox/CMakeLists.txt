cmake_minimum_required(VERSION 3.1...3.29)

project(
    clox
    VERSION 1.0
    LANGUAGES C
)

add_subdirectory(src)

add_custom_target(run
    COMMAND clox
    DEPENDS clox
    WORKING_DIRECTORY ${CMAKE_PROJECT_DIR})