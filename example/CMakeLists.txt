cmake_minimum_required(VERSION 3.27)
project(examplelog VERSION 0.0.1 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

message(STATUS "Installing logger")
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../ ${CMAKE_CURRENT_BINARY_DIR}/logger)

add_executable(examplelog main.cpp)

target_link_libraries(examplelog logger)

add_compile_definitions($<$<CONFIG:DEBUG>:DEBUG>)

